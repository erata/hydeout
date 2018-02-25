## A New Post

Drupal 7’de Views Sayfalama Ayarları ve Sayfalama Çakışması Sorunu
BY ERATA	26 OCAK 2018  LEAVE A COMMENT
Merhaba arkadaşlar. Bu yazıda views sayfalama ayarlarına ve birden çok views kullanım durumunda olası sayfalayıcı çakışmalarına nasıl bir çözüm bulacağımıza değineceğiz. Bu arada anlatım, tam sayfalama (full pager) seçeneğine göre yapılmıştır.

Tam Sayfalama Ayarları
Tam sayfalama (full pager) temel olarak 3 ayar kısmından oluşur.

Üst ayar kısımda;
Gösterilecek içerik sayısı (Items to display) : biz 10 verdik mesela.
Atlanacak -gösterilmeyecek- içerik sayısı (offset) : Eğer 5 yazarsanız baştan 5 kayıt gözükmez.
Sayfalama ID’si (pager ID) ve  Sayfalama Çakışması Sorunu: Views içerisinde kullanılan sayfalama örneğine bir numara verilerek sayfalamaların birbiriyle çakışmasının önlenmesi için çok önemlidir. Baştan sıfır “0” atanmış olarak gelir. Fakat siz her bir views içerisindeki kullandığınız sayfalama örneklerinin ID’sine farklı numaralar vererek olası çakışmanın önüne geçebilirsiniz. Yoksa sayfalamalar çakışabilir ve sayfalamanın çıkması için gerekli içerik sayınız olmadığı halde sayfalama yapıldığını görebilirsiniz (çünkü sayfalama numaralarını başka bir sayfalama örneğinden çekiyordur.)
Sayfalamada en fazla kaç sayfa olacağı (number of pages) : Mesela sonuçlardan en fazla 2 sayfasını sayfalama ile göster, gerisini gösterme diyebilirsiniz.
Sayfalama - Üst Kısım Ayarları

Gösterilecek sayfalama linkleri sayısı (number of pager links visible) : 1,2,3, vb. numaralardan kaç tane gösterilsin anlamında. Buraya sıfır “0” girerseniz gerek rakamla (1,23, vb.) gerekse de yazıyla (ilk, önceki, sonraki, son) görünen linklerin hepsi kaybolur. Amacınız zaten linklerin görünmemesi ise bu alanı sıfır yapıp  linklerin görünmesini engelleyerek Gösterim Filtreleme (exposed filter) seçebilir buradan da listelecek içerik sayısını kullanıcılara bırakmak suretiyle kullanıcı bazlı bir sayfalama elde edebilirsiniz. Veya hem normal sayfalamayı hem de kullanıcı bazlı seçimli sayfalamayı birlikte de kullanabilirsiniz (tabi bu kez gösterilecek link sayısını sıfır “0” vermemeniz gerekiyor…)
Sayfalama Sonucu

Yukarıdaki resimlerde yapılan ayarlar sonucu ortaya çıkan sonuç yandaki resimdeki gibidir. İki sayfa gösteriliyor yaptığımız ayar gereği.

Etiket (Tags) ayar kısmı
Yazı olarak görünecek linklerdeki yazıların ne olacağını ayarlarız.  Örneğin « İlk, ‹ Önceki, Sonraki ›, Son » gibi.
Gösterim Seçenekleri (Exposed Options)
Gösterilecek içerik sayısını yaptığı seçimlerle bizzat kullanıcı belirliyor. Yani, kullanıcı etkileşimli sayfalama yöntemi diyebiliriz.

Sayfada Gösterilecek İçerik Sayısı (Expose items per page) : bu seçeneği seçerseniz altında başlık ve sayfalama opsiyonlarını gireceğiniz iki alan belirecek. Başlık alarak “Kaç Adet Yazı Gösterilsin?”, sayfalama opsiyonları olarak ise 10,15,20, 30, 50 veya başka değerler girebilirsiniz.
Exposed Option Ayarları

Tüm İçerikleri Göster (Include all item option) : Üstte veridiğimiz yapıdaki sayfalama opsiyonlarına tüm içeriklerin gösterilebilmesini sağlayan bir opsiyon katar. Bu seçeneği aktifleştiriseniz altta bulunan boşluk (tüm içerikler etiketi – all items label) duyarlı hale geçer. Buraya saylama opsiyonunda görünmesini istediğiniz metni girebilirsiniz örneğin “Tümü” gibi.
Ötelenen Gösterim (Expose offset): Baştan kaç içeriğin gösterilmeden geçileceğini ayarlıyoruz.
Exposed Options ile Sayfalama

Resimde yukarıdaki resimde verdiğimiz Exposed Options (gösterim opsiyonları) ayarları ile nasıl bir görünüm elde edebileceğimize yer veriliyor.

 

 

 

 

Esnek Sayfalama İçin AJAX Kullanımı
Sayfalar arası geçişin esnek olmasını istiyorsanız en iyi yol AJAX kullanımıdır ve bunun için tek yapmanız gereken şey viewsde Gelişmiş (advanced) -> AJAX kullan (use AJAX) -> Yes seçimini yapmaktır.
