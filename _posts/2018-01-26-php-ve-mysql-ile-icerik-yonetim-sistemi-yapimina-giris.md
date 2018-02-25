## A New Post

PHP ve MySQL ile İçerik Yönetim Sistemi Yapımına Giriş
BY ERATA	26 OCAK 2018  LEAVE A COMMENT
Merhaba arkadaşlar. Web sitesi yapımı ile ilgilenen birçoğumuz genelde içerik yönetim sistemlerini tercih etmekteyiz. Tabi bunun için geçerli bir çok sebebimiz var kendimize göre (örneğin şu yazıma bakabilirsiniz).  Ayrıca dünya geneli yapılan sitelerin genelinde içerik yönetim sistemleri kullanılmakta ve yeni içerik yönetim sistemleri gün be gün piyasaya sürülmekte. Birçoğumuz kod düzeyinde olmasa da Blogger gibi platformlar vasıtasıyla içerik yönetim sistemlerini kullanmakta. Birçoğumuz ise farklı birçok içerik yönetim sistemlerini kurup evirip çevirmekte ve bin takla atabilmekte. Ben bunu kullanarak site yapıyorum, o şunu kullanarak site yapıyor lafları etrafta uçuşmakta. Her neyse esas mevzu bu değildi çok dalmışım:D

Konumuz içerik yönetim sisteminin gerçekte ne olduğuna anlayabilmek. Aşağıdaki sorular ise muhtemel sorulabilecek sorular:

Günlük hayatta sıklıkla karşılaştığımız WordPress, Joomla, Drupal, Blogger, vb. yapıların esasında yani yapısal kökeninde ne var?
Karmaşık işlemlerin gerçekleştirildiği içerik yönetim sistemlerini basite indirirsek neyi görürüz?
İçerik yönetim sistemi özetle ne?
dikak ettiyseniz bu sorular bir nevi birbirinin eşleniği sorular.

Her neyse konuya giriş yapalım artık.

Basit Anlamda İçerik Yönetim Sistemi
Bana göre içerik yönetim sistemi, POST metodu ile formdan gönderilen verilerin veritabanına kaydedilmesi ve veritabanından alınan verilerin ekranda gösterilmesinden ibaret. Yani çok karmaşık gibi görünen WordPress, Joomla, Drupal, vb. içerik yönetim sistemlerinin temelinde esasında bu yapılar var. Ama birçok yapı bindirildiği için bu basit hali görmekte zorlanıyor insan. Çünkü piyasaki içerik yönetim sistemlerinde tema, sayfa,  blog, yorum, kullanıcı yönetimi, forum, reklam, istatistik, anket, vb. değişik yapılar var. Hal böyle olunca içerik yönetim sisteminin özeti olan yapı arada kaynayıveriyor.

Şimdi ise farklı kaynaklardan derlediğim içerik yönetim sisteminin özet halini paylaşayım.

Basit anlamda içerik yönetim sistemi
Kaynak: digett.com

http://css-tricks.com/php-for-beginners-building-your-first-simple-cms sayfasında geçtiği haliyle içerik yönetim sistemi:

Veritabanı oluştur
Veritabanına bağlan
İki alandan oluşan bir form göster
Form ile aldığın verileri veritabanına kaydet
Kaydettiğin verileri ekranda göster
adımlarıyla yapılabilir. Yukarıdaki resim basitçe bu yapıyı sağlıyor.

http://www.elated.com/articles/cms-in-an-afternoon-php-mysql sayfası ise işi biraz daha detaylı ele almış ve nesneye yönelik programlamanın kullanıldığı bir yaklaşımla PHP dili kullanılmış:

Veritabanı oluştur
Makale tablosu oluştur
Konfigürasyon dosyası oluştur
Makale sınıfı oluştur
index.php dosyası oluştur (ön yüz)
admin.php dosyası oluştur (yönetim paneli)
Sitenin ön yüzü içi tema oluştur
Sitenin admin paneli için tema oluştur
Sitil ve logo oluştur.
Aşağıdaki resimde bir içerik yönetim sisteminin nasıl çalıştığı, katmanlı mimari de dikkate alınarak güzel bir şekilde özetlemiş.

İçerik Yönetim Sistemi Nasıl Çalışır
Kaynak: http://www.inqbation.com/how-cms-works

http://daveismyname.com/building-a-content-management-system-from-scratch-bp sayfasında ise kullanıcı girişli yapılar ile biraz daha derine dalınmış.

Ayrıca, add-list-edit-delete-record-in-database-using-php yazısındaki veritabanı yapısını kendi istediğiniz yapıya göre düzenlerseniz yine basit anlamda bir içerik yönetim sistemi elde etmiş oluruz.

Nihaide, php-mysql-temelleri-icerik-yonetim-sistemi-yapisi-planlama sayfasındaki videodan da anlayabileceğiniz üzere temel anlamda  içerik yönetim sistemi biraz MySQL, biraz PHP, biraz da HTML bilgisiyle rahatlıkla yapılabir.

Özetle, MySQL ile dört işlemi (Ekle, Sil, Güncelle, Göster) yapabiliyorsanız, form ile içerik yönetim sistemini de çok rahat yapabiliriz. Önemli olan veritabanı yapısını belirlemek ve form ile  Ekle, Sil, Güncelle işlemlerini yapmak ve akabinde veritabanı verilerini  ekranda göstermek. Gerisi teferruat!

Dikkat: MySQL ile yaptığınız veritabanı işlemlerinde Türkçe karakter sorunu yaşamanız kuvvetle muhtemel. Ondan dolayı çözüm adına şu yazıyı okumanızı tavsiye ederim.

Kaynaklar:
http://css-tricks.com/php-for-beginners-building-your-first-simple-cms/
http://www.elated.com/articles/cms-in-an-afternoon-php-mysql/
http://baylorrae.com/blog/2012/03/14/the-basics-of-creating-a-cms-with-php/
https://gist.github.com/BaylorRae/3850401#file-index-preview-php
https://www.udemy.com/make-a-cms/
http://www.icms.info/
http://www.freezecoders.com/2012/11/add-list-edit-delete-record-in-database-using-php.html
http://www.seyretogren.com/ders/mysql-veri-tabani-ve-php-temelleri-5-icerik-yonetim-sistemi-cms-yapisi-tasarlama.html
http://www.seyretogren.com/ders/mysql-veri-tabani-ve-php-temelleri-6-crud-uygulamari-create-read-update-delete.html
http://www.seyretogren.com/video/php-mysql-temelleri-icerik-yonetim-sistemi-yapisi-planlama.html
http://daveismyname.com/building-a-content-management-system-from-scratch-bp
http://www.turkceteknik.com/goster.php?kid=284&k=php_mysql_-_veri_taban%C4%B1nda_t%C3%BCrk%C3%A7e_karakter_problemi_tam_%C3%83
