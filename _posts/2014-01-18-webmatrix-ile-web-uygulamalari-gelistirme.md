---
layout: post
published: true
excerpt_separator: <!--more-->
title: WebMatrix ile Web Uygulamaları Geliştirme
categories:
  - gelistirme-araclari
tags:
  - webmatrix
redirect_from:
  - /2018/01/01/webmatrix-ile-web-uygulamalari-gelistirme/     
---
Merhaba arkadaşlar. Bugün sizlere web uygulamaları geliştirme sırasında çok faydalı olacağını düşündüğüm bir programdan bahsedeceğim: WebMatrix. Bildiğiniz üzere piyasada bir sürü web uygulaması var ki bunların kimi Windows tabanlı sunucularda çalışıyor kimi ise Linux tabanlı işletim sistemlerinde. Windows işletim sistemli bir bilgisayar kullandığımız düşünürseniz biz Linux tabanlı sunucuda çalışan uygulamar için XAMPP, WAMP Server, Easy PHP tarzı bütünleşik programlar kurarak hallediyoz. Benzer bir şekilde Windows sunucu ihtiyacını ise IIS kurarrak hallediyoruz. Peki hiç düşündünüz mü acaba hem Linux hem de Windows sunucu ihtiyacımızı gideren tek bir uygulama var mıdır diye (Çünkü diğer türlü XAMPP ve IIS olmak üzere en az iki uygulama kurmalıyız).  İşte WebMatrix tam bu anda devreye giriyor ve farklı platformlarlar için bir şemsiye görevi görerek tek bir çatı altında gerek ASP.NET ve  PHP ile yazılımış uygulamaları tek bir arayüzden test etmemize olanak veriyor.

<!--more-->

Nasıl Kurulur?
WebMatrix‘in ana sayfasından indirdiğimiz program vasıtasıyla ya da Web Platformu Yükleyicisi(Microsoft Web Platform Installer) üzerinden WebMatrix seçilerek kurulabilir. Kurulum esnasında ek bir program daha kurmak gerekiyorsa size uyarı vererek bunu da kuralım mı der. Siz de gereken ne varsa kur deyip kurulumu bitirirsiniz.

WebMatrix ile Neler Yapabiliriz
WebMatrix’in bize sunduğu şablon, uygulama galerisi ve boş site seçenekleri yardımıyla yeni bir web uygulaması (site, forum, vb) geliştirebiliriz. Webmatrix SQL Server, MySql, vb. veritabanları ile ASP.NET, PHP, HTML, CSS, JS, CSHTML, vb. dilleri (ayrıntılı bilgi için tıklayınız…) destekler. Dolayısıyla gerek sıfırdan uygulama oluşturmada gerekse hazır uygulama kurup onlar üzerinde değişklikler yapmada WebMatrix gereken esnekliği sağlıyor.

Web Matrix Uygulama Oluşturma

WebMatrix ile gerek Windows tabanlı sunucular üzerinde gerekse de Linux tabanlı sunucular üzerinde çalışabilen birçok web uygulamasını (içerik yönetim sistemleri, Forumlar, Galeriler, vb.) kurup rahatlıkla test edebilirsiniz.

WebMatrix Uygulama Galerisi

WebMatrix ile birçok farklı web uygulamasını kurup rahatlıkla test edebiliyoruz. Ayrıcamenü sisteminin oldukça basit ve anlaşolır olması kullanım kolaylığını oldukça artırmış. Örneğin aşağıdaki resimde Orchard içerik sistemini kurulduktan sonraki karşımıza çıkan ekran. Bu ekran vasıtasıyla kurduğumuz web uygulamasını farklı açılardan (tema, eklenti, dosyalar, veritabanı, rapor, vb.) rahatlıkla kontrol edip yönetebiliyoruz.

WebMatrix ile Orchard CMS

Yukarıda da değindiğim gibi WebMatrix hazır olarak kurduğumuz uygulamar üzerinde değişiklik yapma fırsatını bize veriyor. Aşağıdaki resimde Orchar CMS dosalarının görünümü veriliyor.

Kısacası WebMatrix, farklı platformlar üzerinde çalışabilecek uygulamar için ortak bir altyapı sağlıyor. Basit ve anlaşılır menüleriyle yeni bir şey öğrenmenin sancısından korkan biz kullanıcıların işini oldukça kolaylaştırıyor.

### Konuyla İlgili Tavsiye Kaynaklar:
- http://www.microsoft.com/web/webmatrix/features.aspx
- http://www.microsoft.com/web/post/web-development-101-using-webmatrix
- http://weblogs.asp.net/scottgu/archive/2010/07/06/introducing-webmatrix.aspx
- http://net.tutsplus.com/tutorials/asp-net/the-ins-and-outs-of-webmatrix-an-introduction
- http://www.hanselman.com/blog/WebMatrix2FrontEndWebDevelopersTakeNoteASPNETPHPNodejsAndMore.aspx
- http://www.sitepoint.com/building-dynamic-websites-with-webmatrix

