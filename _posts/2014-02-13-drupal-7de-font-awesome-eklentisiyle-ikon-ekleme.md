---
layout: post
published: true
excerpt_separator: <!--more-->
title: Drupal 7’de Font Awesome Eklentisiyle İkon Ekleme
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
redirect_from:
  - /2018/01/01/drupal-7de-font-awesome-eklentisiyle-ikon-ekleme/     
---
Merhaba arkadaşlar. Günümüz web uygulamalarında ikon kullanımı oldukça yaygınlaştı. Şöyle bir araştırayım dediğinizde siteniz için kullanabileceğiniz onlarca bedava ikon paketini bulmanız içten bile değil. İşte bu yazıda drupal ile entegre çalışabilen meşhur ikon paketlerinden birini yani Font Awesome‘u ele alacağız. Font Awesome,  4.0.3 versiyonuyla şuan 369 ikonu barındırmakta ve zamanla da daha yeni ikonlar eklenmekte olan bir ücretsiz ikon paketi. Font Awesome; Web uygulamaları, form kontrolleri, para birimleri, yazı editörleri, yönler, video player, meşhur siteler ve medya gibi değişik kategorilerde tatmin edecek boyutta ikona ev sahipliği yapmaktadır. Kısacası web uygulamalar için gerekli temel ikonları içerdiği rahatlıkla söylenebilir.

<!--more-->

Drupal’de Font Awesome‘u Nasıl Kullanacağız?
Font Awesome‘u kullanabilmek için eklenti sayfasında belirtilen eklentileri ve kütüphaneyi talimatlarına uygun bir şekilde kurmalısınız. Eklenti kurumu hakkında şu yazımızı okuyabilirsiniz. Eklentiyi kurduktan sonra yapmanız gereken şey beğendiğiniz ikonları şu sayfadaki gibi kullanmak. Ama yol gösterici olması açısından ifade edlim: http://fortawesome.github.io/Font-Awesome/examples‘nı inceleyiniz…

<i class=“fa fa-camera-retro”></i> fa-camera-retro   // Örnek bir kullanım

Font Awesome ikonlarını kullanmak için <i></i> taglarine ve fa etiketine alışsanız iyi olur. İkon büyüklüklreini ise  ise fa-lg, fa-2x, fa-3x,fa-4x veya fa-5x etiketleriyle ayarlamanız pekala mümkün. Örnek kullanım aşağıda:

<p><iclass=“fa fa-camera-retro fa-lg”></i> fa-camera-retro</p>
<p><i class="fa fa-camera-retro fa-2x"></i> fa-camera-retro</p>
<p><i class="fa fa-camera-retro fa-3x"></i> fa-camera-retro</p>
<p><i class="fa fa-camera-retro fa-4x"></i> fa-camera-retro</p>
<p><i class="fa fa-camera-retro fa-5x"></i> fa-camera-retro</p>

Kısacası <i class=” … “></i> Görünmesini İstediğiniz Metin böyle bir kullanım var ve class kısmına ihtiyac duyduğunuz etiketleri yazıp istediğiniz görüntüyü elde edebiliyorsunuz. Ayrıca nasıl liste oluşturulacağı, nasıl form oluştrulacağı örnek kullanım sayfasında detaylıca verilmiş.

Örneğin ben “Yazarın Diğer Yazıları” blok başlığında görünen ikonu ekleyebilmek için views başlığını (siz blok başlıklarında da kullanabilirsiniz) şöyle girdim:

<i class=”fa fa-list”></i> YAZARIN DIĞER YAZILARI

ortaya çıkan sonuçta ikonun görünümü…

Umarım katkı sağlar.
