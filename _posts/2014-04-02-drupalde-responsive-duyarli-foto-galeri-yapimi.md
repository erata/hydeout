## A New Post

Drupalde Responsive (Duyarlı) Foto – Video Galeri Yapımı
BY ERATA	26 OCAK 2018  LEAVE A COMMENT
Merhaba arkadaşlar. Günümüz tasarım yaklaşımlarında responsive (duyarlı) tasarım oldukça önemli bir yer tutuyor. Hal böyle olunca responsive yapılarında bu yaklaşım çerçevesinde önemi daha da bir artıyor. Tasarımı responsive (duyarlı) olan bir sitenin içeriklerinin de bu çerçevede duyarlı olması gerekiyor ki güzel bir sonuç ortaya çıksın. İşte bu yaklaşım içerisinde kritik önem arzeden önemli bir husus foto/video galeri yapımı hususu. Gerek resimlerin gerekse de videoların boyutlarının ekran çözünürlüğüne bağlı olarak yeniden ayarlanması özellikle günümüz mobil teknolojisindeki artan kullanım ivmesi düşünüldüğünde oldukça önemli olduğu anlaşılır diye düşünüyorum.

Responsive (Duyarlı) Foto Galeri Yapımı
Baştan hatırlatmak gerekirse burada responsive galerinin nasıl yapılacağını adım adım anlatmayacağım. Sadece hangi modülleri ya da yaklaşımları kullanırsanız böyle bir galeriyi yapabileceğinizden bahsedeceğim.

1. Magnific Popup eklentisi ile (tabi ilgili kütüphaneyi indirirmeyi unutmayın) güzel bir foto galeri yapabilmeniz mümkün. Fotoğrafların otomatik olarak ekran boyutuna ayarlanıyor olması ise responsive galeri yapmak için gerekli altyapıyı sağlamış oluyor. Magnific Popup ile ayrıca videolarıda göstermeniz mümkün. Eklenti henüz yeni olduğu için ilgili kütüphane özelliklerini tam yansıtmıyor olabilir. Bunun yanında eklenti kullanmadan da galeri yapım örnekleri var.

Örnek Galeri Yapımları 1, 2

2. Juicebox eklentisi ile responsive foto-galeri yapımı. Bunun için Juicebox kütüphanesini de indirmemiz gerekiyor.

Örnek Galeri Yapımları 3, 4

3. Plus Gallery eklentisi ile responsive foto-galeri yapımı. Bunun için Plus Gallery kütüphanesini de indirmemiz gerekiyor. Bu eklentiyle hem site içi hem de site dışı kaynaklarda (Google, Facebook, Flickr, Instagram) yer alan fotoğraflarınızı responsive bir şekilde gösterebilirsiniz. Kullanışlılığı ve şık görünümü açısından en beğendiğim eklentilerden biridir.

Plus Gallery ile nasıl foto galeri yapılacağı direk eklentinin issue’lerindebelirtilmiş. https://drupal.org/node/2104297 sayfasında Google+ hesabımızda yer alan resimlerle nasıl bir galeri yapılabileceği açıklanırken https://drupal.org/node/2077519 sayfasında ise Plus Gallery eklentisinin site içi (local, yani upload edilen) fotoğraflarla nasıl kullanılacağı “CKK ile Plus Gallery türünde bir alan eklemeli ve fotoğraf yüklemelisiniz” şeklinde açıklanmış.
Responsive (Duyarlı) Video Galeri Yapımı
Video galeri yapımında genelde videoyu temsilen bir ön resim (thumbnail) ve resme tıklanınca da videonun kendinin göründüğü bir yaklaşım izlenir. Konu ile ilgili daha önce şu yazıyı yazdığım için daha detayına girmeyeceğim. İlgili yazıda body alanına nasıl esnek boyutlu video eklenildiğinden bahsedilmiş. Dolayısıyla siz esnek boyutlu video galeri yapmak istiyorsanız:

İçerik türünüzde biri image, biri body türünde olmak üzere en az iki alan olmalı.
Image türündeki alanı teaser’da ön yüz resmi (thumbnail) olarak kullanınız. 100X100, 150X150 veya 220X220, vb. bir boyut kullanabilirsiniz bu resimler için. Resimlerin alt alta tek dize şeklinde değilde bir galeri havasında ızgara sisteminde görünmesini istiyorsanız CSS ile galeri yapımı yazısındakine benzer bir CSS kullanımı yapabilirsiniz ya da Views kullanarak da istediğiniz galeri havasını katabilirsiniz.
Ön yüz resmine tıklandığında ise arkada yani Default görünümde image türündeki alan görünmeyecek, body alanına eklediğimiz  İlgili  yazımızdaki video görünecek.
Kaynaklar:

[1] http://highrockmedia.com/blog/designing-responsive-lightbox-photo-grid-gallery-drupal-7
[2] http://othermachines.com/blog/drupal-lightbox-overlay-views-3-and-magnific-popup
[3] http://webwash.net/tutorials/create-responsive-image-galleries-drupal-7-juicebox
[4] http://easywebdesigningtutorial.blogspot.com.tr/2013/06/drupal-responsive-image-gallery-with-juiceboxgallery.html#.UzunRvl_shs