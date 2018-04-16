---
layout: post
published: true
excerpt_separator: <!--more-->
title: XML Dosyasının Veritabanı Olarak Kullanımı ve CompositeC1 Örneği
categories:
  - icerik-yonetim-sistemleri
tags:
  - composite-c1
redirect_from:
  - /2018/01/01/xml-dosyasinin-veritabani-olarak-kullanimi-ve-compositec1-ornegi/     
---
Merhaba arkadaşlar. Bu yazıda XML dosyalarının farklı bir kullanımından yani veritabanı olarak kullanımından bahsedeceğiz. Sanki XML dosyaları veritabanı olarak kullanılmaz, napıyon? der olduğunuzu duyar gibiyim. Evet, yaptığım araştırmalar ve okuduğum onlarca yazı XML dosyalarının veritabanı olarak kullanılabileceğini ortaya koyuyor. Kanıt mı istiyorsunuz o zaman Composite C1 içerik yönetim sisteminin veritabanı olarak XML dosyalarını kullandığını söyliyeyim. Örneğin aşağıdaki resimde  Composite C1 deki  blog yazılarının XML veritabanında nasıl tutulduğu görünmektedir.

<!--more-->

CompositeC1 ve XML Veritabanı Kullanımı
CompositeC1 içerik yönetim sisteminin verilerini XML dosyalarda tutmasını anlatan örnek resim

Evet arkadaşlar doğru duydunuz, Composite C1 içerik yönetim sisteminde XML dosyaları veritabanı olarak kullanılmakta ve istenildiğinde bir eklenti yardımıyla içerikler SQLServer’a taşınabilmektedir. Malum, XML dili ile değişik platformlar arasında veri taşınması mümkün.

XML dosya ile ile CompositeC1 verilerinin saklanması
CompositeC1 verilerinin XML dosya üzerinde tutulma biçimi – her yazı bir kayda karşılık geliyor

Biz şu ana değin XML dosyalarının değişik yazılım dillerinde (C#, Java, vb.) konfigürasyon tanımlamalarında ve ufak tefek bilgileri tutmada kullanıldığını gördük. Fakat bir veritabanı olarak kullanılabileceğini pek normal görmüyorduk. İnternette yaptığım araştırmalarda çoğunluk XML’in platformlar arasında veri taşımada iyi olduğunu, onun bir dil olduğunu ve veritabanı olarak kullanmanın mantıksızlığından bahsedip duruyordu. Ve bu durumu veritabanları ve XML in değişik özelliklerini karşılaştırarak anlatıyorlardı. Savunulan görüşler bana da mantıklı geliyordu çünkü XML de amaç veritabanı değildi ve veritabanların kendilerine has yapıları ve özellikleri vardı. Fakat Composite C1 de XML dosyalarının site verilerinin depolandığı veritabanı olarak kullanıldığını biliyor olmam “XML’in veritabanı olarak kullanılamaz, düşünme bile” tarzındaki yaklaşıma şüpheyle bakmama yol açtı ve daha derinden araştırmaya başladım.

XML dosyalarının veritabanı olarak kullanılabileceğini Composite C1 örneğinde gördüğüm için bu sefer Composite C1 içerik yönetim sisteminde XML dosyalarının veritabanı olarak kullanılma gerekçelerini öğrenmem gerekiyordu. Çünkü okuduğum yorumlarda hep veritabanı  sistemlerinin hem daha fonksiyonel hem de daha performanslı olduğunu söylüyordu. Heralde dedim kendi kendime XML dosyalarını veritabanı olarak kullandıklarına göre bir bildikleri vardır: Dolayısıyla  iletişim formundan Composite C1 e şu soruyu sordum:

Şu ana değin okuduğum yazılar veritabanlarının XML dosyalarının veritabanı olarak kullanılmasına göre daha performanslı olduğunu söylüyor. Peki siz neden XML’i veritabanı olarak kullanmayı tercih ettiniz.
Firmadan yetkili bir kişi ise bana şöyle dönüş yaptı:

XML temelli veritabanı bir tabloda 10.000 veya daha fazla veri kaydı tutuncaya kadar iyi performans göstermekte ve verileri hafızada tuttuğu için veri okumada oldukça hızlıdır.
Evet, aldığım bu cevapla araştırmalarıma yeni bir yön vermiş oldum (Artık o eski ben değildim:D). Veritabanlarına kuşbakışı bakabilmem ve XML dosyalarının veritabanı olarak kullanımının bu kuşbakışı içindeki konumunu tespit etmem gerekiyordu.

Şu ana değin veritabanı kullanımı olarak SQL (tablo) ve düz dosya (flat file) veritabanlarını biliyordum. Fakat XML dosyaları bunların içerisine pek girmiyordu. O zaman onu nereye konumlandıracaktık. Veee.. derken bir gün “NoSQL” denen bir kavram ile karşılaştım. Bu kavram, veritabanındaki yeni yaklaşıma verilen addı. Bu veritabanı yaklaşımı çok farklı biçimleri olmakla birlikte SQL veritanlarındaki gibi tablo kullanımı yoktu dolayısıyla foreign key ve primary key denilen şeylere ihtiyaç yoktu. Veriler değişik formatlarda (XML, JSON, vb.) saklanabiliyordu.  Evet dedim kendi kendime XML veritabanı bu yeni yaklaşım içerisinde olmalı. Şöyle bir girdim NoSQL içerisine, vayt be arkadaş! bu kadar bilinen ve yaygın bir yaklaşım hakkında benim şu ana kadar neden bilgim olmadı diye öfflledim bir an ve diğer taraftanda sanki bir bulmacayı çözmüşçesine sevinçliydim.

Ayrıca XML veritanı ile ilgili http://en.wikipedia.org/wiki/XML_database sayfasını ziyaret ettiğimde şaşkınlığım bir kat daha arttı. Öyle ki XML veritabanlarında sorgu yapabileceğimiz XQuery adında bir dil bile vardı bildiğimiz veritabanlarında SQL dili olduğu gibi. Dedim kendi kendime: Sen neymişsin be XML!

### Tavsiye Kaynaklar:
- http://tr.wikipedia.org/wiki/XML
- http://en.wikipedia.org/wiki/XML_database
- http://en.wikipedia.org/wiki/Document-oriented_database
- http://en.wikipedia.org/wiki/Database
- http://tr.wikipedia.org/wiki/NoSQL_(kavram)
- http://en.wikipedia.org/wiki/NoSQL
- http://www.btsoru.com/questions/9935/xml-dosyas-veritaban-olarak-kullanlabilir-mi
- http://forum.ceviz.net/genel-programlama/90333-sql-mi-xml-mi.html
- http://www.webmastersitesi.com/web-dersleri/59946-xml-veritabani-islemleri-ders-i.htm
- http://coder.digitaldunyam.net/gunluk-kullanim-icin-mini-not-uygulamasi/
- http://coder.digitaldunyam.net/xml-dosyasini-veritabani-olarak-kullanma/
- http://bilgiteknoloji.net/xml/xml15_internette_xml_kullanmak.asp
- http://www.webmastersitesi.com/web-dersleri/59947-xml-veritabani-islemleri-dersleri-ii.htm
- http://www.mzekiosmancik.com/tag/xml-veritabani/
- http://www.yazilimgunlugu.com/xml-datayi-okuma-listeleme-ve-yeni-kayit-ekleme-islemleri-makalesi/179.aspx
- http://www.mutasyon.net/makaleler.asp?id=26
- http://www.yazgelistir.com/makale/veritabani-yerine-xml-
- http://stackoverflow.com/questions/201568/when-would-i-use-xml-instead-of-sql
- http://www.bilisimakademi.net/yaziOku.asp?yaziID=288

