---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'En Popüler Üç Açık Kaynak Veritabanı Sistemi: MySql, PostgreSQL ve SQLite'
categories:
  - veritabani
tags:
  - postgresql
  - sqlite
  - mysql
---
Merhaba arkadaşlar. Bu yazıda sizlerle açık kaynak veritabanı sistemlerinden en popüler üçünü ele alacağız. Her ne kadar biz burada üç tanesini ele alacak olsak da piyasada onlarca veritabanı sistemi olduğunu, bunlar içinde de hatırı sayılır sayıda açık kaynak veritabanı sistemi olduğunu baştan belirtelim.

<!--more-->

MySQL
Genel bir bilgi için MySQL’in Wiki Sayfası‘nı inceleyebilirsiniz. MySQL, açık kaynak veritabanı sistemlerinde en popüler olanıdır ve web uygulamaları için çok iyi olanaklar sağladığı için web sunucularında oldukça yaygın olarak kullanılmaktadır. Açık kaynak bir veritabanı sistemine ihtiyaç duyanlar genelde MySQL’i tercih ederler.

MySQL, web uygulamaları için gerekli tüm fonksiyonelliği sağlasa da bazı eksikleri de yok değildir. Çözülemeyen bazı kritik hatalar ve veri ambarı kullanımı için yeterli performansta olmaması MySQL’in eksileri olarak sayılabilir.

MySQL küçükten büyüğe yüzlerce site tarafından aktif olarak kullanılmaktadır.

Büyük Kullanıcıları (daha detaylı olarak):
Youtube
Twitter
Facebook
Wikipedia
Drupal, Joomla, WordPress, vb
Slashdot
PostgreSQL
Genel bir bilgi için PostgreSQL’in Wiki Sayfası‘nı inceleyebilirsiniz. PostgreSQL, MySQL’e göre daha karmaşık işlemleri rahatlıkla yapabilecek şekilde tasarlanmıştır. PostgreSQL ile büyük miktardaki verilerle çalışmak MySQL’e göre daha kolaydır. Gerek büyük verileri ele alabilmesi ve gerekse de karmaşık fonksiyonları rahatlıkla gerçekleştirebilmesi açısından PostgreSQL, teknik anlamda MYSQL’den daha üstündür denebilir. Bu açıdanbakıldığında PostgreSQL, bir üst ligin oyuncusudur.

MySQL ve PostgreSQL’i performans olarak karşılaştırmak biraz karmaşık meseledir. Fakat bir yorumda geçtiği üzere veritabanları performansının %80’lik aslan payı onun düzgün kullanımından (veritabanı sorgularını, tasarımını, vb. düzgün yapmaktan) geçiyor. Yani performanta veritabanı sistemi markası değil veritabanının düzgün kullanımı daha önemli.

Ama bu iki veritabanının genel bir karşılaştırmalarını merak ediyorsanız 1, 2, 3, 4 okuyabilirsiniz.

 Büyük Kullanıcıları (daha detaylı olarak):
Yahoo
Cisco
Reddit
Disqus
SourceForge
Sun Microsystems
Skype
SQLite
Genel bir bilgi için SQLite’ın Wiki Sayfası‘nı inceleyebilirsiniz. SQLite’ın en büyük özelliği, herhangi bir veritabanı sunucusuna ihtiyaç duymaksızın çalışabilmesidir. Bu özelliğinden dolayı kurulum ve konfigürasyon gerektirmez. SQLite, tek kullanıcılı sistemler için uygundur (sifir kurulum, embedded, el terminalleri, web sitesi veya browser kayitlari vs). Boyutu oldukça küçüktür (~250kb) ve embeded platformlar için (örneğin şu yazıyı okuyunuz) kullanılabilir. Bu açıdan MySQL ve PostgreSQL gibi karmaşık fonksiyonlar ihtiva etmez ama bu onun çok yetenekli bir veritabanı sistemi olmasına gölge düşürmez. Sade ve anlaşılır yapısıyla kullanımı kolaydır. Güvenlidir. SQLite, birçok büyük firma tarafından tercih edilmektedir.

 Büyük Kullanıcıları (daha detaylı olarak):
Apple
Adobe
Dropbox
Google
Microsoft
Skype

MySQL-PostgreSQL ve SQLite’ın;

Genel bir karşılaştırılması için:  (1, 2 ) birini seçiniz.
Genel bir kullanımına yönelik bilgi için tıklayınız.
Veritabanı Yönetim Ekranı Seçenekleri
Veritabanı sistemlerin kullanımını kolaylaştıran önemli bir mevzu, yönetim ekranlarıdır. Özellikle MySQL’de daha fazla yönetim ekranı seçenekleri mevcut olmakla birlikte bahsedilen üç veritabanı sistemini de destekleyen yönetim ekranları mevcuttur.

phpMyAdmin
MySQL için tasarlanmış yönetim ekranıdır. MySQL’e yönelik birçok işlevi ekran üzerinden yapmamıza imkan verir. Özellikle web uygulamaları geliştirilirken MySQL’in ayrılmaz bir parçası gibidir. Basit ve sade ekran yapısı ile kullanımı kolaydır.

PHP Mini SQL Admin
phpMyAdmin’e alternatif, daha hafif (oldukça küçük boyutlu ~30kb) bir yönetim ekranıdır. PHP dili ile yazılımış tek sayfalık yönetim ekranıdır. phpMyAdmin’de olduğu gibi MySQL için geliştirilmiştir. MySQL’e yönelik temel işlemler rahatlıkla gerçekleştirilebilir.

SIDU admin GUI
PHP ile yazılımış bu yönetim ekranı MySQL, PostgreSQL ve SQLite veritabanı sistemlerinin üçünü de destekler. Bir veritabanı yönetimi ve web uygulamalarına yönelik tüm ihtiyaçlarınızı karşılayacak yetkinliktedir. Kuruluma gerekmez.

Admirer
PHP ile yazılmış tek sayfalık yönetim ekranı olmasına karşın MySQL, PostgreSQL ve SQLite veritabanı sistemlerinin üçünü de destekleyecek şekilde tasarlanmıştır.

SQlite Designer
Yazılımcılara yönelik geliştirilmiş SQLite veritabanı yönetim ekranıdır.  Linq to SQLite ile C# ile kullanımı mevcuttur.

Ayrıca Mozilla Firefox eklentilerinden SQLite Manager ve SQLite Expert SQLite yönetim ekranı olarak kullanılabilir.
