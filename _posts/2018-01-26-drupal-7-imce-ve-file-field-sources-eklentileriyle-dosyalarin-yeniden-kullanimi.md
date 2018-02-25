## A New Post

Drupal 7: Imce ve File Field Sources Eklentileriyle Dosyaların Yeniden Kullanımı
BY ERATA	26 OCAK 2018  LEAVE A COMMENT
Merhaba arkadaşlar. Bu yazıda, Drupal 7’de mevcut kaynakların nasıl yeniden kullanılabileceğine değineceğim. Bu iş için biçilmiş kaftan ise imce ve file field sourcess eklentileri. Imce eklentisine bir yazımızda değinmiştik. Bu eklentiler vasıtasıyla daha önceden yüklemiş olduğumuz (upload) dosyalara standart dosya/resim yükleme  bölümünden ulaşıp dosyaya referans vererek aynı dosyanın tekrar yüklenmesinin önüne geçmiş oluyoruz ve yeniden kullanımı sağlamış oluyoruz. Böylece kaynaktan tasarruf sağladığımız gibi dosya yönetimini de kolaylaştırmış oluyoruz.

Kaynakların (resim, text, pdf, vb. dosyalar) yeniden kullanımına olan ihtiyaç, yoğun dosya yüklenme işleminin yapıldığı sitelerde daha çok hissedilmektedir. Özellikle yoğun olarak resim galerisi yapıyorsanız ve önceden yüklemiş olduğunuz resimleri tekrar kullanmak durumunda iseniz bu yazıyı dikkatlice okuyun derim. Ayrıca drupal‘deki birçok resim galerisi eklentisi standart resim yükleme mekanizmasına göre çalışmakta ve resim galerisi oluştururken mevcut resimleri kullanmamıza izin vermemekte dolayısıyla aynı resimleri tekrar yüklemek durumunda kalmaktayız. O zaman ne yapmalı? İşte cevabı:

Dosyaların Yeniden Kullanılması İçin Yapılması Gerekenler
Dosyaların yeniden kullanmı artırmak için olmazsa olmazımız file field sourcess eklentisidir. Bu eklentiyi kurduktan sonra ilgili içerik türüne gidip (örneğin article) ilgili alandaki (dosya ya da resim) dosya yükleme kısmınada yer alan file field sourcess ve imce eklentileriyle ilgili gerekli ayarları yapmalısınız. Örneğin benim article içerik türünün resim alanı için kullanmış olduğum file field sourcess ve imce ayarları aşağıdaki resimdeki gibidir.

File Field Sources ile Dosyalarda Yeniden Kullanım

Resimde imce ve file field sourcess eklentilerinin dosyalardaki yeniden kullanımı sağlamadaki seçenekleri yer alıyor. Seçenekleri ele alırsak:

imce ve  imce_filefield Eklentileriyle Dosyaların Yeniden Kullanımı
Resimde “Allow users to select files from IMCE File Browser for this field” seçeneği ile ifade ediliyor. imce ve  imce_filefield eklentileriyle birlikte kullanımı ile ortaya çıkan seçenektir. Bu seçenek ile standart dosya yükleme kısmına imce ile daha önceden yüklemiş olduğumuz dosyalara atıfta bulunarak dosyaların yeniden yeniden kullanımı sağlamış oluyoruz.

file field sourcess eklentisiyle Dosyaların Yeniden Kullanımı
file field sourcess eklentisi dosyaların yeniden kullanımına dair birçok seçeneği barındırır:

Upload (default): standart dosya yükleme mekanizmasıdır

IMCE File Browser: file field sourcess eklentisinin imce ve file field sourcess ile beraber kullanımı ile ortaya çıkan seçenektir.

Advenced upload widget (Plupload): plupload eklentisini kullanarak aynı anda birçok dosya (çoklu) yüklemenize izin verir. Çünkü standart dosya yükleme mekanizması ile tek tek dosya yükleyebiliyoruz. Biz burada tek resim kulandığımızdan aktif etmedik.

Remote URL textfield: internetteki bir resmin URL adresini girerek resmi o adresten kendi hostumuza yüklememize izin veren seçenektir.

Autocomplete reference textfield (with Visual Select File): file field sourcess ile visual_select_file eklentisinin beraber kullanımından doğan seçenektir. visual_select_file eklentisi media eklentisine göre daha az fonksiyon ihtiva eden kullanışlı bir eklentidir. Daha önceden yüklemiş olduğumuz resimleri görsel bir ekran vasıtasıyla seçmemizi ve seçilen resmin referansını vererek yeniden kullanmamızı sağlar.

File attach from server director: daha önceden yüklemiş olduğumuz resimleri combobox ile bize sunar ve seçtiğimiz resmin referansını alır ve resmi yeniden kullanmamazı sağlıyor. Bu seçenek pratiklik kazandırması bakımından çok iyi.

Aşağıdaki resim, yukarıdaki resim ile belirttiğimiz ayarların yapılması sonucu ortaya çıkan yeni resim yükleme mekanizmasını gösteriyor.

File Field Sources ile Resimlerin Yeniden Kullanımı

file field sourcess ve  imce ile dosyaların yeniden kullanımı için en azından “Open File Bowser” (IMCE File Browser) ve “File attach” seçenekleri işaretleyin derim. Biri pratiklik sağladığı için, diğeri ise daha detaylı dosyaya ulaşmayı sağladığı için.

“Upload” seçeneğini ise standart dosya yükleme yapmaya devam etmek istiyorsanız (tek tek) seçin. Çoklu dosya yükleme yapmak isterseniz plupload ile ortaya çıkan “Advanced upload widget” seçeneğiniz seçebilirsiniz standart “Upload” seçeneği yerine.

Umarım faydalı bir yazı olmuştur.