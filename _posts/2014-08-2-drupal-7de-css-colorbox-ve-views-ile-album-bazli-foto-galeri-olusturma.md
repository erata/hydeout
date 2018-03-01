---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Drupal 7’de CSS, Colorbox ve Views ile Album Bazlı Foto-Galeri Oluşturma'
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
---
Merhaba arkadaşlar. Bu yazıda views ile nasıl album bazlı foto galeri yapılır onu göstereceğiz.  Bu yazıyı hazırlarken şu kaynaktan esinlendiği belirteyim ki isteyenler bir de oradan incelesin. Bu arada konuya başlamadan önce Drupal 7’de CSS İle Foto-Galeri Yapımı ve Drupal 7’de Colorbox Eklentisi Yardımıyla Foto-Galeri Oluşturma yazılarını okumanızda fayda var çünkü bu yazı önceki iki yazı ile ortaya çıkan yapının üzerine kurulu.

<!--more-->

Yukarıda da değindiğim gibi CSS ve Colorbox ile ilgili yazılarımı okuyup galeri yapma aşamasını halletti iseniz sırada tek tek oluşturduğunuz galerileri views yardımıyla nasıl album şeklinde gösterebileceğimiz. Bunu ise özetle şu şekilde oluşturuyoruz:

1- Views ve Ctools eklentileri yüklü değilse yüklüyoruz.
2 – Views’da add new view diyoruz.
3 – Gelen sayfada View name olarak Galeri, Show kısmında sırası ile Content, Resim Galeri, Newest first
Create a page diyerek Page title olarak Galeri, Diplay format olarak Grid ve field seçiyoruz.
Item to display olarak 12 seçiyoruz.
4 – 12’den fazla galerinizin olacağını düşünüyorsanız ve saylayıcı ile gösterilmesini istiyorsanız Use a pager‘i işaterleyin.

5 – Şimdi sırada daha önceki yazılardaki galeri yapımızdaki Resim Galeri adlı içerik türündeki Galeri Resimleri adlı resim alanını kullanmakta.  Bunun için FIELD menüsünde add diyerek Content: Galeri Resimleri alanını bulup seçiyoruz. Gelen ekranda Create a label tikini kaldırıyoruz. Sonra Formatter olarak Image, Image style olarak Thumbnail, Link image to olarak da Content seçiyoruz. Böylece Thumbnail bir resme tıklandığında bizi içik sayfasına götürmesini halletmiş oluyoruz.

6 – Sırada ise işin püf noktası yani içeriğin ilk resmini galerinin kapak resmi olarak belirleme. Bunun için MULTIPLE FIELD SETTINGS menüsünde simple seperator kısmında yer alan Seperator alanın boşaltıyoruz yani virgülü siliyoruz. Sonra Display‘daki all ifadesini 1 olarak düzeltyoruz.

Album bazlı galeri oluşturma: Son durumda Galeri views’inin görünümü

Album bazlı galeri oluşturma: resim_galeri fotoğraf alanımızdaki işlemler

Özetle 6. adımda Resim Galeri içirl türüyle eklediğimiz bir içerikteki resimlerden ilkinin albumde görünmesini sağlıyoruz. 5. adımda ise tıklanan bu album fotoğrafı ile ilgili galerinin tüm fotoğraflarının görünmesini sağlamış oluyoruz.

Son durumda ise aşağıdaki yapı geliyor. Yani Galeri 1, Galeri 2, Galeri 3, Galeri 4, Galeri 5 olarak eklediğimiz galeri içerikleri anasayfada (eğerki Promoted to front page tiki işaretliyse yayınlama seçeneklerinde) aşağıdaki gibi görünür

Galeri sayfasında ise bu içeriklerdeki (Galeri 1,2,3,4,5) ilk resimler galeriyi temsil eden resimler yer alır. Galerileri temsil eden bu resimlerden herhangi birine tıkladığımızda bizi doğrudan ilgili içerikteki tüm resimlere ve yazıya götürecektir.

Eğer galeriyi temsil eden fotoğrafı değiştirmek istiyorsanız ilgili içerikteki yüklemiş olduğunuz resimlerden istediğinizi  1. resim (en üst sıraya taşıyarak) yaparak dileğiniz gerçekleştirebilirsiniz.

Eğer Galerilerin anasayfada değilde sadece Galeri sayfasında görünmesini istiyorsanız Drupal 7 İçerik Yayınlama ve Kaydetme Seçenekleri ve Ek Talepler yazısını okumanızı öneriyorum. Kısaca içeriği yayınlarken Promotion settings‘deki (yayınlama ayarları) Promoted to front page (ön sayfada görünsün) tikini kaldırmanız yeterli.

Umarım yararlı olmuştur.

### Kaynaklar:
- http://jamestombs.co.uk/2011-05-26/create-album-based-image-gallery-drupal-7-using-fields-and-views
