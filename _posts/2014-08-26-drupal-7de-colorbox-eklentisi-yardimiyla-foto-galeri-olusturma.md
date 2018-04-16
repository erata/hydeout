---
layout: post
published: true
excerpt_separator: <!--more-->
title: Drupal 7'de Colorbox Eklentisi Yardımıyla Foto-Galeri Oluşturma
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
redirect_from:
  - /2018/01/01/drupal-7de-colorbox-eklentisi-yardimiyla-foto-galeri-olusturma/    
---
Merhaba arkadaşlar. Bir önceki yazımda birkaç satır CSS kodla drupalde nasıl  resim galerisi yapılabileceğinden bahsetmiştik. Fakat bu galeri tam anlamıyla bir galeri değildi. Çünkü bir thumbnail resme tıkladığımızda otomatik olarak orjinal resim görünüyordu ama diğer resimlere geçiş açılan bu resim üzerinden sağlanamıyordu. Dolayısıyla bu yazıyı bu soruna çözüm sağlayan, lightbox eklentilerinden biri olan Colorbox eklentisiyle ile resim galerisi yapımına değineceğiz. Örnek uygulamamızı ise Bir önceki yazı ile inşa ettiğim Resim Galeri içerik türünün Galeri Resimleri resim alanı üzerinde anlatacağım.

<!--more-->

İlk önce Colorbox eklentisinin kurulması gerekiyor ki bunun için 3 şey gerekiyor.

Colorbox eklentisi (Örneğin 7x-2.5)
Colorbox kütüphanesi adresinde indirilip dosya içeriği sites/all/libraries altına colorbox adlı kılasör olarak ekelenecek. Sonuçta sites/all/libraries/colorbox yapısı elde edilecek.
Libraries eklentisi (Örneğin 7x-2.1)
Colorbox eklentisini düzgün bir şekilde kurduktan sonra ilgili İçerik Türünün Manage Display (Görünümü Yönet) kısmında Galeri Resimleri alanın Format kısmını colorbox seçmeliyiz. Daha sonra sağ tarafta yer alan simgeye tıklayarak colorbox ile ilgili ayarlamalara geçelim ve resmin içerikte görünen halini, tıklanıncaki halini, galeri ve başlık kısımlarındaki ayarlamaları kendi isteğimize göre dolduralım. Örnek bir colorbox ayarı aşağıdaki resimde yer almaktadır.

Colorbox Manage Display

Resimdeki gibi bir ayar yapınca daha önce CSS ile yaptığımız galeri örneğinde herhangi bir resme tıklayınca (örneğin ilk resim) aşağıdaki gibi bir görünüm ile açılacaktır.

Colorbox Galeri

Colorbox Caption TokenResmin altında yer alan yazıları istediğniz gibi ayarlayabilirsiniz bir önceki resimdeki colorbox ayar kısmındaki Caption (Başlık) ayarı ile. Eğer caption kısmında verilen başlıklar ihtiyacınızı karşılamıyor ise Custom (with tokens) ile ifade edildiği gibi token eklentisiyle gelen değişkenleri kullanmak suretiyle istediğiniz özelleştirmeyi rahatlıkla yapabilirsiniz.

Bunun dışında colorbox ile açılan ekran görünümünü özelleştirmek için admin/config/media/colorbox ile veya admin/modules sayfasında colorbox eklentisini bulup configure seçeneği ile ayar yapacağınız yere ulaşarak size sunulan seçenekler ile istediğiniz görünüme kavuşabilirsiniz. Örneğin biz style kısmında Defaulttan Example 2‘ye geçiş yaptık.

Colorbox Settings

Colorboxun style kısmında Example 2’yi seçtikten sonra yeni görünüm ise aşağıdaki gibidir.

Colorbox Style Example 2

Görüldüğü üzere colorbox eklentisi ile farklı görünümlü, farklı altyazılı resim geçişleri yapmak için çok esnek. Yeni yazılarda görüşmek üzere.
