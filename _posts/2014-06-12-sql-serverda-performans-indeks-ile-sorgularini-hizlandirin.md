---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'SQL Server’da Performans: İndeks İle Sorgularını Hızlandırın'
categories:
  - veritabani
tags:
  - sqlserver
---
Merhaba arkadaşlar. Bu yazıda küçük çapta bir SQL Server sorgusunu nasıl optimize edebiliriz ona değinmeye çalışacağım.

Bildiğiniz üzere veri yoğunluğunun az olduğu veritabanlarında sorgu performansı pek önemli değildir. Fakat veri yoğunluğunun fazla olduğu veritabanlarında sorgu çekme ve sonuca ulaşmak oldum olası sıkıntılı bir iştir. Sırf zaman aşımından dolayı çalışamaz olan programlarda cabası. Peki yok mu bunun kolay ve hızlı bir çaresi: var – sorgu yapınızı dikkate alarak İndex oluşturma. Peki sorguda geçen birkaç ifadeye göre fazla derinlemesine araştırmadan index ataması yapsak olmaz mı – olur fakat maksimum performans yerine daha azına razı olursunuz.

<!--more-->

### Peki maksimum performans için İndex oluştururken  nelere dikkat etmeli?

**1. “Execution Plan” denilen sorgunan “Çalışma Akış Planı”nı çıkarın.**

SQL Server - Execution Plan SQL Server menüsünde yer alan yandaki ikona tıklayarak Execution Planı aktifleştirin.

**2. İstatistikleri görebilmek için sorgunuzu aşağıdaki gibi yazın** (sorgu istatistiklerini görmek için iyi).

set statistics time on
set statistics io on

//Sorgunuz -> select * from….

set statistics time off
set statistics io off

**3. Sorgunuzu çalıştırın ve “Execution Plan” ile ile ortaya çıkan iş akış diyagramını iyi inceleyin.** 

Sorgunuzun yavaşlığının nereden kaynaklandığına dair size ipucu verecektir. Sorgunun yavaş olmasına neden olan alanları belirledikten sonra artık index atamaya geçebilirsiniz.

İndex Oluşturmak (SQL Server 2008’e Göre)
İndex oluşturma, SQL Server ile ilgili çat pat bilgisi olanlar için başta zor bir şeymiş gibi gözükebilir ama öyle değil. Yapmanız gereken şey Execution Plan belirlediğiniz yavaşlığa neden olan alanları seçip indeksi oluştur demek o kadar. **Bunun için ne yapmalı?**

İlk önce Veritabanında ilgili tablonun Indexes bölümüne gelip sağ tıklamalı,

SQL Server - İndex Oluşturma

Sonra ise aşağıdaki resimdeki gibi işlem yapılarak index tanımlama süreci bitirilmeli. Bir tablo için birçok index tanımlayabilirsiniz. Tanımlayacağınız indeks sayısı, veri yoğunluğu ve sorgu sayınıza göre artabilir veya azalabilir. Örneğin aşağıdaki resimde FirstName ve ModifiedDate alanlarını baz alarak nasıl index oluşturulacağı anlatılıyor. Siz de tablodan indeks oluştururken sorgunuzdaki alanları ve sorgunuzun Execution Planda size zaman kaybettiren noktaları dikkate alın.


İndex ismi verirken “IX_AlanAdı1_AlanAdı2” veya “IDX_AlanAdı1_AlanAdı2” şeklinde bir yol izlemeniz iyi isimlendirme açısından yararlı olacaktır.

Not: İndex oluştururken aktif tabloyu komple kilitlemekten kaçınmak gerekir. Dolayısıyla index oluşturma sürecini kod ile yapılmalı ve ONLINE=ON yapılmalı. Ayrıca Execution Planda sıralama ile ilgili gereksiz zaman kaybettiren alanların olup olmadığına dikkat etmeli. Sorgunuzda hiç sıralama yapısı kullanmadığınız halde sıralamaya ciddi zaman kaybettiğiniz bir durum ortaya çıkabilir. Böyle durumda scripte girip sıralamayla bize zaman kaybettiren alanın sıralama ayarları değiştirilmeli.
