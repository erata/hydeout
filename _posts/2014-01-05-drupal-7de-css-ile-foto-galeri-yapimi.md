---
layout: post
published: true
excerpt_separator: <!--more-->
title: Drupal 7’de CSS İle Foto-Galeri Yapımı
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
redirect_from:
  - /2018/01/01/drupal-7de-css-ile-foto-galeri-yapimi/  
---
Merhaba arkadaşlar. Bugün sizlere drupalde ekstradan bir modül kullanmaksızın basit bir galeri yapımını göstereceğim. Olay ise temel olarak herhangi içerik türünde galeri şeklinde görünmesini istediğiniz resim alanına biraz sitil vermekten ibaret.

<!--more-->

Biz verdiğimiz örnekte Resim Galeri adında bir içerik türü oluşturarak Manage Fields (Alanların Yönetimi) kısmınsda Galeri Resimleri isimli bir resim alanı ekledik ve bu alanın Number of values (eklenebilecek resim sayısı diyebilirsiniz) kısmına unlimitted (yani sınırsız) dedik ve içerik türümüzü kaydettik. Daha sonra ise Manage Display kısmında Galeri Resimleri için Label (etiket) kısmında Hidden (saklı), Format kısmında Image (resim) ve image ayarları kısmında image style (resim sitili) için thumbnail->file seçtik. Ve böylece içerik türü kısımındaki işlemimiz bitmiş oldu. Resim Galeri içerik türünün Manage display kısmı aşağıdaki resimden incelenebilir.

CSS Foto Galeri Manage Display

Daha sonra ise Resim Galeri içerik türündeki Galeri Resimleri alanına sitil verdik. Bunun için tema dosyasındaki style.css dosyasına aşağıdaki kodu ekledik ve dosyamızı kaydettik.

/* Resimlerin soldan sağa doğru dizilmeleri ve diğer ayarlar*/
.field-name-field-galeri-resimleri img{
float: left;
padding: 5px;
margin: 4px;
background-color:#F6F6F6;
border: solid 1px #E5E5E5;
}
/* herhangi bir resmin üzerine gelince arka plan renginin değişmesi*/
.field-name-field-galeri-resimleri img:hover{
background-color:#DDDDDD;
}
Resim Galeri içerik türümüzün yazı kısmına bir satırlık yazı ve resim ekleme kısmına ise 7 adet resim ekledik. Sonuç ise aşağıdaki resimdeki gibi.

CSS Foto Galeri

Umarım yararlı olmuştur.
