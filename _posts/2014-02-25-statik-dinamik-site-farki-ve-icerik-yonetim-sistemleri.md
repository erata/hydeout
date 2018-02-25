## A New Post

Statik-Dinamik Site Farkı ve İçerik Yönetim Sistemleri
BY ERATA	26 OCAK 2018  LEAVE A COMMENT
Merhaba arkadaşlar. Bu yazıda statik site ve dinamik site nedir sorusuna cevap aralayacağız ve tabi ki içerik yönetim sistemlerinden bahsedeceğiz.

Statik Site Nedir?
HTML, CSS ve Javascript kullanılarak geliştirilen, kullanıcı etkileşimli olmayan sitelerdir. Bu siteler, güncelleme yok denecek kadar azdır ve bir değişiklik yapıldığında değiştirilen dosya sunucuya yüklenerek değişiklikler yansıtılır. Bu anlamda veritabanı kullanımına ihtiyaç  yoktur. İstemciden gelen istekler sunucuya yüklenmiş dosyalar vasıtasıyla cevaplanır. Statik sitelerdeki işleyiş aşağıdaki resimdeki gibidir.

Statik Site
Kaynak: digett.com

Statik sitelerin Artıları ve Eksileri
 + Sunucu taraflı yazılım dilleri (PHP, ASP.NET, Java, Ruby on Rails vb.) ve veritabanı sorguları statik siteler için söz konusu olmadığı için dinamik sitelere göre oldukça hızlıdır.

 +  Sunucu taraflı yazılım dilleri ve veritabanı kulalnımı olmadığı için bunların kullanımından doğabilecek olumsuzluklardan da (örneğin haklenme) muaftır.

 –  Kullanıcı etkileşimli değildir (mesaj yollama, üye olma, forum, vb.)

 –  Veriler, veritabanında değil de HTML dosyalarda tutulduğundan herhangi bir güncelleme gerektiğinde değişiklik manuel olarak (yönetim paneli yok çünkü) ilgili dosya(lar) üzerinde yapılmak zorundadır. Yapılan değişiklikler ise ancak ilgili dosyanın sunucuya yüklenmesiyle ekrana yansıyacaktır.

Dinamik Site Nedir?
Dinamik siteler, statik sitelerin aksine oldukça kullanıcı etkileşimlidir. Bugün internette etkileşimde bulunabildiğimiz sitelerin hepsi dinamik sitelerdir (haber siteleri, forum siteleri, sosyal medya siteleri, vb). İstemci ile etkileşimde bulunulduğundan veritabanı kullanımı gereklidir. İstemciden gelen istekler sunucu tarafındaki yazılım ile yorumlanarak veritabanından çekilen kayıtlar ile yanıtlanır. Dinamik sitelerdeki işleyiş aşağıdaki resimdeki gibidir.

Dinamik Site
Kaynak: digett.com

Dinamik sitelerin Artıları ve Eksileri
 +  Kullanıcı etkileşimlidir (mesaj yollama, üye olma, forum, vb.)

 +  Veriler, statik dosyalarda değilde veritabanında tutulur. Böylece veritabanına has imkanlardan oldukça yararlanılır.

 +  Yönetim paneli vasıtasıyla site verilerinde ya da ayarlarında değişiklik yapmak oldkça kolaydır.

 –  Sunucu taraflı yazılım dilleri (PHP, ASP.NET, Java, Ruby on Rails vb.) ve veritabanı sorguları statik siteler için söz konusu olduğu için statik sitelere göre yavaştır.

 –  Sunucu tarflı yazılım dilleri ve veritabanı kullanımından dolayı kırılganlık gösterebilir (örneğin heklenme).

Sonuçta, sitedeki hız ve güvenlik sizin için ön planda ise ve siteniz kulanıcı etkileşimli olamayacak ve zaman içinde güncellenmeye pek ihtiyaç duymayacaksa siteyi statik dosyalarla (HTML, CSS ve Javascript) yapmanız sizin için daha uygun olabilir. Ayrıca, dinamik site yapımı için kullandığımız hazır içerik yönetim sistemleri site yapımında nasıl bir kolaylık sağlıyorsa static site yapımı için kullanılabilecek hazır frameworkler (1, 2)  de aynı kolaylığı sağlamaktadır. Eğer şartlar dinamik site yapmanızı zorunlu kılıyorsa (kullanıcı etkileşimi, veritabanı kullanımı, yönetim paneli, sık sık içerik ekleme/silme/güncelleme) o zaman dinamik site yapmanız daha mantıklı olabilir.

İçerik Yönetim Sistemleri
Dinamik site yapmak için kullanabileceğimiz yazılımlardır (ya da frameworklerdir). Sunucu taraflı diller (PHP, ASP.NET, Java, Ruby on Rails vb.) kullanılarak geliştirilir ve verilerin depolanması için veritabanı kullanır. Site içeriklerinin yönetimi ve değişik farklı ayarlamalar için oldukça başarılıdırlar. Günümüzde onlarcası, ücretli ya da ücretsiz olarak internet ortamında sunulmaktadır. Günümüzün ençok kullanılan içerik yönetim sistemlerinden ilk üçü WordPress, Joomla ve Drupal’dır. İçerik yönetim sistemlerinde yönetim paneli ile:

İçerik ekleme/değiştirme/silme
Kategori ekleme/değiştirme/silme
Yorum ekleme/değiştirme/silme
Kullanıcı yönetimi ve yetkilendirme
URL ayarlamaları
vb.
birçok şey rahatlıkla yapılabilir.

Günümüzde hazır içerik yönetim sistemlerine talep hiç olmadığı kadar artmışıtır. Fakat oldukça yaldızlı gözüken bu yazılımları kullanmak gerçekte o kadar da ışıltılı değildir. Yapılması gereklen ayarlamaların gereğince yapılamaması güvenlik ve hız sorunlarına davetiye çıkaracak ve başımızı ağrıtacaktır. Ayrıca hazır içerik yönetim sistemlerinin değişik açılardan avantajlılık ve dezavantajlılık gibi hususlarının olması, karar verme aşamasında düşünmeye sevketmektedir. Günümüzde hazır yönetim sistemlerinin ileride nereye doğru götüreceğini kestiremeyen birçoğu kendi içerik yönetim sistemini yazmaktadır. Diğer açıdan ise kendi yazdığımız içerik yönetim sistemlerinin, onlarca yüzlerce geliştirici ile desteklenmiş ve birçok açıdan güvenirliliği test edilmiş hazır içerik yönetimleri karşısında ne kadar başarılı olabileceği ayrı bir muamma olarak karşımızda durmaktadır. Bu aşamada şu soruya doğru cevap vermek gerekiyor: Tekerliği yeniden icat etmeye değer mi? Çünkü kendi yazdığımız içerik yönetim sistemi maliyeti artırıcı yönde etki yapacak.

Kaynaklar:
http://www.digett.com/blog/01/16/2014/pairing-static-websites-cms
http://en.wikipedia.org/wiki/List_of_content_management_systems
http://mashable.com/2013/04/26/css-boilerplates-frameworks
http://speckyboy.com/2011/11/17/15-responsive-css-frameworks-worth-considering
http://tr.wikipedia.org/wiki/Web_sitesi