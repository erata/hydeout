## A New Post

Drupal 7’de Syntax Highlighter Kullanarak Kodları Renklendirme
BY ERATA	26 OCAK 2018  LEAVE A COMMENT
Merhaba arkadaşlar. Bugün drupal 7’de kodların daha göz alımlı gösterilmesi konusunu ele alacağız. Tabi ki bu işlev için biçilmiş kaftan olan syntaxhighlighter eklentisinin nasıl kurulacağından ve wysiwyg ile entegre tinymce editörü ile nasıl kullanılacağından bahsedeceğiz.

Öncelikle syntaxhighlighter eklentisi ve wysiwyg ile entegre çalışabilmesi için gerekli bileşenleri listeleyelim.

https://drupal.org/project/syntaxhighlighter (7x-2x-dev ile beraber tag olarak pre kullanılmaya başlandı)
https://github.com/alexgorbatchev/SyntaxHighlighter (syntaxhighlighter kütüphanesinin github sayfası ki buradan indirebilirsiniz eklentinin kütüphanesini)
http://alexgorbatchev.com/SyntaxHighlighter/ (syntaxhighlighter kütüphanesinin anasayfası)
https://drupal.org/project/syntaxhighlighter_insert (syntaxhighlighter eklentisinin wysiwyg ile entegre tinymce editörü ile kullanılabilmesini sağlıyor)
Eklentilerin Kurulması ve Gerekli Ayarlamaların Yapılması

Sisteminizde wysiwyg üzerinde kurulu tinymce (ya da ckeditör) olduğunu kabul ederek anlatım yapıyorum. Öncelikle ilgili eklentileri (syntaxhighlighter, syntaxhighlighter_insert) sites/all/modules kılasörüne, eklenti kütüphanesini ise sites/all/libraries kılasörüne adı syntaxhighlighter olacak şekilde çıkarıyoruz. Eklentileri aktifleştiriyoruz.

Syntax Highligter Eklenti Kurma Sonrasi

Sonra ya admin/config/content/syntaxhighlighter yolunu izleyerek ya da admin/modules/syntaxhighlighter yolunu izleyere ilgili eklentinin konfigürasyonunu yapıyoruz. Gelen konfigürasyon ekranında Enabled languages, Theme, Tag name tarzında seçenekler gelecek ve siz hangi programlama dilini seçeceğinizi, hangi temayı seçeceğinizi ve kod renklendirmek için hangi HTML tag’i kullanacağınızı buradan ayarlayacaksınız. Örneğin ben tema için default, tag name için pre‘yi sabit bıraktım, sadece programlama dili noktasında ekstardan seçimde bulundum. Eğer PHP dilinde de kodlar eklerim diyorsanız eklentiler kısmından PHP filter eklentisini aktif etmeniz gerekmektedir.

syntax highligter buttonBir sonraki aşama ise syntaxhighlighter‘ın wysiwyg‘e tanıtılması. Bunun için ilk önce kullandığımız yazı formatından (admin/config/content/formats yoluyla Filteren HTML yada Full HTML ) syntaxhigligter’i seçmeliyiz. Yazı formatı kısmında tanıttığımız syntaxhigligter’ı tinymce’de kullanabilmek için Wysiwyg profiles (admin/config/content/wysiwyg) bölümünden kullandığımız yazı formatındaki editörü seçerek değiştir(edit) diyeceğiz ve gelen ekrandaki Buttons and Plugin menüsünden Insert syntaxhighlighter tag seçeneğini işaretleyip kaydedeceğiz.

Artık Kullanmaya Başlayalım…

Editöre bir kod ekleyip renklendirerek göstermek için yukarıda verdiğimiz düğmeye tıkladıktan sonra gelen ekranda Brush ile verilen başlık altında hangi programlama dili ile ilgili kod ekleyeceğinizi ve First line kısmına ise sol taraftaki kod satır numarasının hangi sayı ile başlayacağını belirtir. İmleci hangi satırda bırakırsanız o satıra kodu ekler. Ayrıca kodlarınızın bir başlık adı altında tıklanınca görünen bir şekilde olamsını istiyorsanız Title (başlık) kısmına istediğiniz başlığı yazıp hemen aşağıda yer alan collapse seçeneğini seçmeniz gerekiyor.

Örneğin aşağıdaki CSS kodunu syntaxhighlighter ile göstercek olursak:

.node-teaser {
  border-bottom: 1px solid #d3d7d9;
  margin-bottom: 30px;
  padding-bottom: 15px;
}
.node-sticky {
  background: #f9f9f9;
  background: rgba(0, 0, 0, 0.024);
  border: 1px solid #d3d7d9;
  padding: 0 15px 15px;
}
.node-full {
  background: none;
  border: none;
  padding: 0;
}
.node-teaser .content {
  clear: none;
  line-height: 1.6;
}
.node-teaser {
 border-bottom: 1px solid #d3d7d9;
 margin-bottom: 30px;
 padding-bottom: 15px;
}
.node-sticky {
 background: #f9f9f9;
 background: rgba(0, 0, 0, 0.024);
 border: 1px solid #d3d7d9;
 padding: 0 15px 15px;
}
.node-full {
 background: none;
 border: none;
 padding: 0;
}
.node-teaser .content {
 clear: none;
 line-height: 1.6;
}
şeklinde bir görünüm elde ederiz.

Ayrıca Şu Kaynaklardan da Yararlanabilirsiniz:
http://jordanjr.com/articles/drupal-7-syntax-highlighting-using-wysiwyg-ckeditor-and-syntax-highlighter
http://stuartmcgoldrick.com/drupalwysiwyg
http://zugec.com/2011/03/how-use-syntax-highlighter-module-drupal-7
Umarım yararlı olmuştur.