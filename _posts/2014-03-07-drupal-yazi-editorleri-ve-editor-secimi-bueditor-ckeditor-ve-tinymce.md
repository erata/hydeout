---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Drupal: Yazı Editörleri ve Editör Seçimi (Bueditor, CKEditor ve Tinymce)'
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
redirect_from:
  - /2018/01/01/drupal-yazi-editorleri-ve-editor-secimi-bueditor-ckeditor-ve-tinymce/   
---
Merhaba arkadaşlar. Bu yazıda drupalin en can sıkıcı konularından biri olan yazı editörlerinden bahsedeceğiz. Bildiğiniz üzere drupal 8 e kadar yazı editörleri için İngilizcesi “out of box” denilen bir çözüm mevcut değildi. Dolayısıyla çözüm adına iki seçenek çıkmaktaydı. Bunlar: Yeterli düzeyde HTML ve CSS bilerek içeriğe kod üzerinden müdahale edebilmek ya da 3. parti yazı editörleri kullanmak (yani “out of box” çözüm İngilizcesi). [Drupalde kullanılan editöler ile ilgili genel bilgili için]

<!--more-->

drupal.org sitesinde yukarıda bahsettiğimiz çözümlerden ikincisi tercih edilerek bueditor kullanmıştır. Peki bueditor neden tercih edilmiştir dediğinizi duyar gibiyim.

### Neden Bueditor Kullanmalı?

bueditor,  wysiwyg editörlerinden biri değil yani gerçek manada bir editör de değil. Çünkü bueditör ile yapılan değişiklik görünüm olarak değilde HTML kodu (<b>, <i>, <img>, vb.) şeklinde görünüyor . Fakat, basit ama kullanışlı bir arayüzü var ve sisteme neredeyse hiç yük getirmiyor, birçok eklentiyle uyumlu bir şekilde çalışabiliyor. Bir editörden beklenilen temel gereksinimleri rahatlıkla karşılayabilecek button (düğme) setine sahip olmanın yanı sıra ek button setleri de rahatlıkla eklenebiliyor. markdowneditor eklentisiyle daha okunaklı bir görünüm elde edilebiliyor (HTML’in okunurluğu biraz zor). Ayrıca gelişmiş bir kullanıcı izin ayar kısmı var ve değişik yetkinlikte kullanıcılar tanımlayarak o haklar doğrultusunda editörü kullanabilmelerini sağlayabiliyoruz. [Bueditor’e dair detaylı bilgi için]

### Neden Wysiwyg Editörleri Kullanmalı?

Wysiwyg editöler, yazılara hem kod üzerinden hem de görünüm üzerinden müdahale edebileceğimiz editörlerdir. Yazı üzerine verdiğimiz sitiller hem görünüm olarak belirir (Bueditorde kod şeklinde idi) ve son kullanıcıların çok rahatlıkla içerik girmelerine imkan verir.

Bugün drupalde birçok wysiwyg editörü seçeneği mevcut ve seçim bayağı sancılı olabilir sizin için. Özellikle kalitesini tüm dünyada isbatlamış iki editör (Bakınız) olan CKEditör ve Tinymce arasında kalabilirsiniz. Normalde wysiwyg editörü olarak bunlar dışında birçok editör seçeneği mevcutsa da genel temayül bunlar üzerine. Ayrıca özellikle bu iki editör üzerine ciddi bir eklenti desteği var.

CKEditor ve TinyMCE İçin Hangi Eklentiler Kullanmalı?
Zor karar verilen ve sancılı olan bir mevzu da editör kullanımı için eklenti seçimi meselesi. Öyle ki karşımızda temel olarak iki eklenti çıkıyor bunun için: wysiwyg ve ckeditor.

Wysiwyg eklentisi genel bir editör ekleme api’si gibi iş görüyor. Wysiwyg eklentisiyle CKEditor, TinyMCE,  WYMeditor, YUIeditor, openWYSIWYG, jWYSIWYG, markItUp, FCKeditor, NicEdit, Whizzywig, EpicEditor seçeneklerinden istediğimizi kullanabiliriz.

Ckeditor eklentisi, CKEditor editörüne özgü bir editör ekleme eklentidir ve bu editör ile CKEditor’üne özgü detaylı ayarlamalar yapabiliriz eklenti ayar arayüzünden. Aynı imkanı  wysiwyg eklentisi CKEditor’üne sunmamaktadır. Örneğin CKEditor’ün birçok tema seçeneği var biz wysiwyg eklentisiyle tema seçiminde bulunamıyoruz.

Sonuçta, wysiwyg eklentisiyle birçok editörü tekbir arayüz ile ekleme şansına sahip iken Ckeditor eklentisiyle  CKEditor için daha detaylı ayarlamalar yapma şansına sahipsiniz.

Wysiwyg ve CKEditor Kullanımında Dikkat!
Aynı anda hem wysiwyg hem de ckeditor eklentilerini aktif etmeyin. Sonra çakışmalar yaşanıyor ve eklenilen editör düzgün çalışmıyor.

**Özetle:**
Eğer CKEditor‘e karar kılmışsanız baştan Ckeditor eklentisiyle yola devam edin bu editöre özgü gelişmiş ayarlamalara izin verdiği için.  Yok ben her yazı formatında farklı bir editor kullanacağı diyorsanız Wysiwyg eklentisini kullanın. Fakat wysiwyg eklentisinin Ckeditor eklentisi kadar CKEditor‘e destek vermediğini baştan hatırlatayım. Eğer derseniz ki benim için önemli olan sistemin en az yükle en hızlı çalışması, yapılan değişikliğin anında görünüm olarak yansıması pek de önemli değil o zaman bueditor iyi bir seçenek olarak karşınızdadır. Kaldı ki bueditordeki HTML’in oluşturduğu okunurlulukla ilgili zorluğun markdowneditor ile çözülebileceğine yukarda değinmiştik.

Drupal 8: CKEditor ve Satır İçi Editör Kullanımı (İnline Editing)
Drupal 8 ile beraber CKEditor, temel sürümün içerisine dahil edildi. Fakat tek yenilik bu değil: inline editing denen yaklaşım da uygulamaya sokuldu ve böylece seçilen kısmi alanlar üzerindeki değişiklik yapılabilecek. Aşağıdaki örnek videoyu inceleyiniz.

{% include youtube.html id="Dlh602DcW-A" %}

### Kaynaklar:
- http://drupal.cocomore.com/blog/better-than-wysiwyg_bueditor-drupal-7_use-and-configuration
- http://brighternet.com/articles/review-of-drupal-rich-text-editors/
- http://drupalize.me/blog/201310/drupal-8-wysiwyg-and-line-editing
- https://drupal.org/node/208456
- http://www.youtube.com/watch?v=Dlh602DcW-A

