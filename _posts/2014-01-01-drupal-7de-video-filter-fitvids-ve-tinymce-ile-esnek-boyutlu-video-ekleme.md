---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Drupal 7’de Video Filter, FitVids ve Tinymce ile Esnek Boyutlu Video Ekleme'
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
---
Merhaba arkadaşlar. Bugün sizlerle drupalde nasıl esnek bir şekilde değişik internet ortamlarındaki videoları (youtube, vimeo, dailymotion, flickr, vb.) esnek bir şekilde (responsive) sitemize eklemesini göstermiş olacağım. İlgili eklentileri ekledikten sonra ve gerekli ayarları yaptıktan sonra siz de benim gibi internet ortamındaki farklı video kaynaklarını boyut duyarlı yani responsive bir şekilde ve sadece ilgili videonun url’sini ve istediğiniz boyut ölçüsünü girerek elde edeceksiniz. Lafı fazla uzatmadan bu iş için gerekli eklentilerden ve ayarlamalardan bahsedeyim.

<!--more-->

Not: Ben Wysiwyg eklentisi üzerine Tinymce yazı editörünü kurdum. Ve bu yazıda ona göre anlatacağım.

Gerekli Eklentiler: 

https://drupal.org/project/wysiwyg (7x-2.2)  sites/all/modules altına.

http://www.tinymce.com adresinde  (3.5.10) sürümünü  indirip  sites/all/libraries altına indirdiğiniz zipli dosyanın içindeki kılasörü çıkarmanız gerekecek.  Oluşacak yapı sites/all/libraries/tinymce şeklinde olacacak. Tinymce’nin  3.5.10 sürümünü özellikle verdim çünkü şuanki son sürüm olan 4.0.12’yi  Wysiwyg‘de tanıtamıyoruz.

https://drupal.org/project/video_filter   sites/all/modules altına.

https://drupal.org/project/fitvids sites/all/modules altına,  jquery.fitvids.js dosyasını ise sites/all/libraries altına fitvids adlı bir kılasör oluşturarak bu kılasörün içine atmalıyız.

Kısa Bir Açıklama:

Normalde biz fitvids eklentisini kurmadan da değişik internet video kaynaklarından sitemize videolar ekleyebiliyoruz. Fakat eklediğimiz videoların boyutları ekran boyutlarını dikkate almaksızın hep aynı kalıyor. bu ise örneğin cep telefon kullanan ziyaretçiler açısından problem oluşturabilir. Dolayısıyla video boyutu belirlediğiniz sabit bir boyda kalsın diyorsanız fitvids eklentisini kurmanıza gerek yok. Yoksa esnek boyutlarına duyarlı videolar için fitvids eklentisini kurmanız şart. Şunu baştan belitmeliyim ki  fitvids eklentisi videoları esnek boyutlu (responsive)  yapmada çok çok çok önemli iş görüyor. Hakkını vermeden geçmeyelim. Çünkü ben bu eklentinin henüz video_filter ile uyumlu çalıştığını bilmeden önce css elastic videos, responsive design with css3 media queries, responsive embeds, creating intrinsic ratios for video yazılarında geçtiği gibi <frame>… video sorce…</frame> şeklindeki videolara kapsayıcı bir css sınıf eklemeye çalıştım video_filter eklentisinde. Biraz uğraştıktan sonra video filter’ı responsive şekle sokmanın bayağı bir zor olduğunu anladım ve başka bir yolu yok mu dediğim sırada imdadıma Responsive Media, Responsive Embeds yazılarının yol gösterdiği  https://drupal.org/project/fitvids yetişti.

Ve Eklenti Kurulumlarına ve Eklentilerin Ayarları Yapmaya Başlıyoz… Kemerinizi Takın:D

İlk önce video_filter eklentisini kuralım (çünkü ayarlanması gereken bir şey yok)

Sonra fitvids eklentisini kuralım ve ayarlar (configure) kısmına geçelim. Ayarlar kısmında iki tane ayar yapabileceğimiz yer verilmiş. Üstteki Custom iframe URLs ile videoyu ekleyeceğimiz  yapı/yapıları yazacağız. Default olarak body tanımlı ve bu bizim işimizi görüyor. Eğer sizin videoyu ekleyeceğiniz kısım farklı ise onu (da) buraya yazmanız gerekir. Alttaki ayar kısmı ise Custom iframe URLs. Burada hangi video kaynaklarını (youtube, vimeo, dalymotion, flickr, vb.) kulalcaksak onların adreslerini yazıyoruz. YouTube, Vimeo and Kickstarter default olarak tanımlı olduğu için sizin diğer eksik site adreslerini yazmanız yeterli. Örneğin dailymotion ve flickr eklemek istiyorsak ilk satıra http://www.dailymotion.com ce ikinci satıra da http://www.flickr.com ekleyelim ve kaydedelim. Bu kısım da tamam. Yandaki resim örnek bir fitvits eklenti ayarını göstermektedir. Biz burada birçok farklı video kaynağı ekledik ama sizin ihtiyacınız youtube ve vimeo ile sınırlı ise ve videoları body içerisine ekleyecekseniz bu ayar kısmına hiç girmenize gerek yok.



Üçüncü ve en zor kısmı Tinymce yazı editörünü kurmak. Bunun için wysiwyg eklentisini kurup ayarlar kısmına geçelim. İlk önce wysiwyg‘deki istediğimiz text formatlarından bir tanesinde (muhtemelen Filtered HTML’i) seçelim ve kaydedelim. Sonra yanda Düzenle (edit) linkine tıklayalım.

Wysiwyg ile Yazı Editörü Ekleme

Gelen ekranda Buttons and Plugin kısmında Video Filter ile beraber diğer istediğmiz araçları seçelim.

Tinymce Ayarları

Video Filter ve diğer gerekli araçları seçtikten sonra kaydedip çıkabilirsiniz. bunadan sonraki süreç ise eklediğimiz video filter eklentisinin text formatta tanıtılması.

Video Filter Seçimi

Burada daha önce wysiwyg eklentisinin ayar kısmında tinymce editörünü hangi yazı formatına tanıtmışsanız o yazı formatını seçerek video filter eklentisini ilgili yazı formatında aktif etmeniz gerekiyor. Biz Filtered HTML’i öncesinde wysiwyg ‘e tanıttığımız için şimdi de Filtered HTML ile devam edeceğiz. İlgili yazı editörünün sağ tarafında configure linkine tıklayıp gelen ekranda video filter check box’ını tıklayacağız.

Yazı Formatları

Bundan sonra dilerseniz kaydedip çıkabilir ya da Filter settings kısmında videolar için genel bir ayar yapabilirsiniz örneğin genişliği ve yüksekliği 610×343 olsun ve video otomatik olarak açılmasın gibi. Artık esnek boyutlu (responsive) videolar ekleyebilirsiniz.

video filter ile genel video ayarı

Tinymce Video Filter Düğmesi

Yeni bir yazı eeklerken yazı formatını Filtered HTML seçtikten sonra Tinymce editöründe yandaki video ekleme düğmesi ikonu gözükecek. İlgili düğmeye tıklayınca…

Video Filter Yönetim Paneli

Video Filter Yönetim Paneli gelecek. Bu panel ekleyeceğiniz videonun linkini girmenin yanısıra video boyutunu ayarlama, videonun sağ,sol veya merkezde çıkmasını belirleme ve otomatik çalışmasını sağlama gibi ayarlar yağmanıza imkan veriyor.

Hemen aşağıda yer alan İnstructions başlıklı link ise örnek video linkleriyle ilgili örnekler sunuyor. Biz daha önceki kısımda video boyutunu ve otomatik çalışmasınının genel ayarlarını yapmıştık (width-height: 610×343, autoplay:no). Dolayısıyla burada sadece ilgili video kaynaklarından (youube, vimeo, dailymotion…, vb.) ekleyeceğimiz videounun linkini yazmak yeterli olacak. Fakat ekleyeceğiniz videonun genel ayarlarda yaptığınız şeklinden farklı bir ayarda olmasını istiyorsanız bu aayarlar ile istediğinizi elde edebilirsiniz.

Kaynaklar:

http://webdesignerwall.com/tutorials/css-elastic-videos
http://webdesignerwall.com/tutorials/responsive-design-with-css3-media-queries
https://groups.drupal.org/node/233238
http://daverupert.com/2011/09/responsive-video-embeds-with-fitvids
http://amobil.se/2011/11/responsive-embeds
http://alistapart.com/article/creating-intrinsic-ratios-for-video
https://drupal.org/node/1535954
http://friendlymachine.net/posts/2012/responsive-embedded-video
http://avexdesigns.com/responsive-youtube-embed
https://drupal.org/project/video_filter
https://drupal.org/project/fitvids
https://drupal.org/project/wysiwyg
http://www.tinymce.com
