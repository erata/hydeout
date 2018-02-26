---
layout: post
published: true
excerpt_separator: <!--more-->
title: >-
  Composite C1: Açık Kaynak Microsoft Tabanlı İçerik Yönetim Sistemi ve Tercih
  Sebepleri
categories:
  - icerik-yonetim-sistemleri
tags:
  - composite-c1
---
Merhaba arkadaşlar. Bu yazıda sizlere Windows tabanlı bir içerik yönetimi olan Composite C1‘den bahsedeceğim. Bildiğiniz üzere şuan piyasada irili ufaklı onlarca içerik yönetim sistemi var gerek ücretli gerekse ücretsiz. Peki o kadar içerik yönetim sistemi arasından [Composite C1](https://c1.orckestra.com/)’in dikkatimi çekmesindeki sebepler ne? İşte bu yazıda Composite C1’i tercih sebebi yapabilecek özelliklere değineceğim

<!--more-->

### 1. Açık Kaynak (Open Source)

Composite C1, 2010 yılına kadar parayla satılmaktaydı. Sonradan açık kaynak şeklinde piyasaya sürülmeye başladı.

### 2. En Son Microsoft Teknolojilerini Desteklemesi ve Yeni Teknolojileri Barındırması

Composite C1, Microsoft’un teknoloji laboratuvarı desek yanlış olmaz herhalde:D. https://compositec1.codeplex.com/releases/view/114480 sayfasından da görebileceğiniz üzere Composite C1;

- NET 4 and .NET 4.5 desteklemekte
- ASP.NET Razor, Web Formları, Master pages
- HTML, XML, XHTML, XSLT vb.
- Bootstrap, CSS/LESS
- SQL Server (Eğerki XML Flat File veritabanından geçiş yaparsanız)

gibi bir çok teknodesteklemekte. Dolayısıyla bu durum geliştiricilerin elini oldukça rahatlatacağı gibi farklı tercik imkanı da verecektir. Composite C1 kurulumu sırasında farklı birçok kurulum modu ile gelmesi (ASP.NET Master Page, Razor, Bare Bones vb.) bu açıdan oldukça geniş bir platform sağlamaktadır.

Demo modu ile kurulum ise taslak bir site için gerekli yapıları içermesi ve örnek yapıları içermesi açısından yeni başlayanlar için oldukça yol göstericidir.

### 3. Gerek Editör Gerekse de Admin Olarak Yönetilmesi Kolay

Sade ve basit yönetim paneli vasıtasıyla hangi kullanıcının hangi haklara sahip olabileceği, hangi eklentilerin ekleme/kaldırırma, veritabanı işlemleri, vb. rahatlıkla yapılabilmekte. Bu açıdan Admin kullanıcı çok rahat edecektir.

Diğer açıdan ise basit ve kullanışlı yazı editörü sayesinde editör/yazar kullanıcılar hiç zorlanmadan içeriklerini rahatça girebileceklerdir. http://users.composite.net/User-Guide/User-Guide/How-to-use-Composite-C1 sayfasından editör olarak nasıl kolayca içerik eklenendiğini görebilirsiniz.

### 4. XML Dosyası ve SQL Server Veritabanı Alternatifleri

Composite C1, kurulumunda veritabanı olarak XML dosyasını kabul etmekte. Yani site içerisindeki tüm veriler XML dosyalarını kaydedilip ordan servis edilmekte. Bu ise küçük ve orta ölçekli sitelere hız ve performan olarak dönecektir. Çünkü XML dosyaları bellekte tutulduğu için oldukça hızlı bir okuma hızı sağlamaktadır. Dolaysıyla XML dosyasının veritabanı olarak kullanılması 10.000 kayda kadar verisi olabilecek küçük ve orta ölçekli siteler için oldukça iyidir (Bu bilgiyi  Composite C1‘e sorduğum bir soru ile öğrendim). Ayrıca XML veritabanına bağımlı değilsiniz. İstediğiniz an XML dosyalarına kaydetmiş olduğunuz verileri SQL Server’a taşıyabilir, SQL Server’dan devam edebilirsiniz. Bu anlamda da oldukça geniş bir manevra alanı sağlamaktadır.

### 5. İhtiyacı Karşılayacak Yetkinlikte Eklenti (Addons) Barındırma

Composite C1, http://www.composite.net/Add-on-Market sayfasından da göreceğiniz üzere sitenizi farklı amaçlar doğrultusunda geliştirebileceğiniz onlarca eklenti içermektedir.  Eklentilerden bazıları ücretle olmakla birlikte genel ihtiyac diyebileceğimiz eklentilerin okdukça büyük bir kısmı ücretsiz sunulmaktadır. Daha çok özel durumlar için hazırlanmış ücretli eklentileri de parasını ödeyerek rahatlıkla temin edebilirsiniz. Ayrıca Composite C1’de eklenti kuma/kaldırma nerdeyse çocuk oyuncağı kadar kolay bir işlemdir.

### 6. Sitenin Yedeğini Alma

http://www.composite.net/Add-on-Market/Packages/Composite.Tools.XmlBasedSiteBackup sayfasından da görüleceği üzere 2-3 tıklamyla rahatlıkla tüm sitenin yedeğini alabiliyorsunuz.

### 7.Çoklu Site Desteği

Composite C1 ile tek bir yönetim panelinden birçok site açıp yönetebilirsiniz. Bu ise site yönetimi açısından oldukça rahatlık sağlamaktadır.

### 8. İyi bir Dökümantasyona Sahip Olması

Gerek http://docs.composite.net/ sayfasında gerekse http://users.composite.net/ sayfasında Composite C1 ile ilgili oldukça geniş, güzel hazırlanmış dökümantasyona ulaşabilirsiniz. Gerek kullanıcılar gerekse de uygulama geliştiriciler bu dökümanlar yardımıyla başka ek bir kaynağa gereksinim duymadan istediklerini yapabilecek seviyeye gelebilir. 

Özetle Composite C1 beni en çok yönetim panelindeki o inanılmaz derecedeki sadelik ve kullanım kolaylığı ile cezbetti, İçerdiği değişik son moda Microsoft teknolojileri ile bir aşama daha etkiledi ve etkilemeye devam ediyor. Eğer bir Microft kulalnıcısı iseniz bu içerik yönetim sitemini gözardı etmemenizi önenirim.

umarım yararlı olmuştur.
