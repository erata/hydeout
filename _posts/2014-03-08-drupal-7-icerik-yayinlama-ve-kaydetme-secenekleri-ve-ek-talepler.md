## A New Post

Drupal 7 İçerik Yayınlama ve Kaydetme Seçenekleri ve Ek Talepler
BY ERATA	26 OCAK 2018  LEAVE A COMMENT
Merhaba arkadaşlar. Drupalin çekirdek sürümünde temel ihtiyaçlarımızı karşılayacak içerik kaydetme ve yayınlama seçenekleri mevcuttur. Fakat bazı durumlar bu seçenekleri yetersiz kılmaktadır. Dolayısıyla biz ilk önce çekirdek sürümyle sunulan kaydetme ve yayınlama seçeneklerini ele alacağız. Sonra bu seçeneklerin hangi durumlarda yetersiz kaldığına değinerek ve çözümler sunmaya çalışacağız.

Temel Yayınlama ve Kaydetme Seçenekleri
Yayın Seçenekleri
Drupal Temel Yayın Seçenekleri

Published: içeriğin yayınlanmasını sağlar.
Promoted to front page: İçeriğin ön sayfada gözükmesini sağlar
Sticky at top of lists: içeriğin en üst sıralamada gözükmesini sağlar. Dikkat çekmek istediğiniz içeriklerde kullanabilirsiniz.

İçerik Kaydetme Seçenekleri
İçerik Kaydetme ve Görüntüleme Seçenekleri

Save: içeriği kaydeder. Eğer yayınlama seçeneklerinde “Published” de seçili ise içerik yayınlanmış olur. Diğer türlü kaydedilmiş fakat yayınlanmamış bir içerik olur.
Preview: içeriğin yayına sokulduğunda nasıl bir görünüme sahip olduğunu görebilirsiniz.

…/admin/content adresini izleyip içerikler ve içeriklere ait yayınlama ve diğer özellikleri görebilirsiniz. Aşağıdaki resmi inceleyebilirsiniz

İçerik Listesi ve Özellikleri
İçerik Listesi ve içeriğe ait özellikler

Şimdi ise temel yayınlama ve kaydetme seçeneklerinin yetersiz kaldığı bazı durumları listeleyecek olursak:

İçeriği taslak olarak kaydetme – mevcut durumda sadece kaydetme (save) seçeneği var
Otomatik kaydetme seçeneğinin olmaması – herhangi bir arıza sonucu içeriği kaybetmemek ve kalınan yerden devam etmek için
Kullanıcı gruplarına göre yayınlama seçenekleri sunma
Yayınlama konumu olarak yayınlama seçenekleri
Zamana bağlı olarak içerikleri otomatik yayınlama seçeneği
Editör-moderatör-yazar ilişkisi içinde kapsamlı bir yayın politikası sunma
Yukarıda belli başlı ihtiyaçları saydığımıza göre şimdi bu ihtiyaçları gidermenin yollarını arayalım.

1- İçeriği taslak olarak kaydetme
İçeriği kaydetmenin (save) yanı sıra içeriği taslak olarak da kaydederek (Blogger’daki gbi) sonradan içeriği tamamlayarak yayınlamak isteyebilirsiniz. Bunun için drupalde birçok seçeneğiniz olduğunu söyliyeyim. Ama save_draft ya da save_edit eklentilerinden birini kullanmanız çözüm için yeterli olacaktır. Ben sorunu çözüm için save_draft eklentisini kullandım ve kaydetme seçeneklerine ek bir düğme eklendi. Aşağıdaki resmi inceleyiniz.

Taslak Olarak Kaydetme
save_draft eklentisiyle İçeriği Taslak Olarak Kaydetme seçeneği

Şunu hemen belirtmekte fayda var: eğer save_draft eklentisini kullanısanız , admin olmayan yazarlarınız varsa ve “Save as draft” seçeneği ile taslak olarak içerik kaydederlerse bu içeriğe yönetim panelinden ulaşamayacaktır. Bu sorunu çözmek için views ile bir görünüm (blok, sayfa, vb) oluşturarak çözüm sağlamalısınız. Tabi o an sisteme giriş yapmış (login) kişinin kendi taslak yazılarını görmesini istiyorsanız bunun için Contextual Filter kullanmanız gerekecektir. Örnek bir views görüntüsü aşağıdaki resimde.

views ile Taslak Yazıları Görüntüleme
Views İle Taslak Yazıları Görüntüleme

Yaınlanmamış içerikleri view_unpublished eklentisini kullanarak yapabilirsiniz. Tabi kullanıcılara gerekli atamanız gerekiyor görebilmeleri için.

İçerik taslak olarak kaydedildiğinde yayın zamanı sanki taslak olarak oluşturulduğu zamanmış gibi atanmakta ve bazı durumlarda bu problem oluşturabilmektedir. İçeriğin oluşturulduğu zamanı değilde esas yayınlandığı zamanı yayınlama zamanı olarak atamak istiyorsanız publish_date ya da Published Time (published) eklentilerinden birini kullanın.

2- İçeriği Otomatik Kaydetme Seçeneği
Bu işlem için autosave eklentisini kullanabilirsiniz.

3- Kullanıcı Gruplarına Göre Yayınlama Seçenekleri
B iş için biçilmiş kaftan override_node_options eklentisidir. Bu eklentiyle kullanıcı rollerine ve içerik türlerine göre istediğiniz gibi yayınlama seçeneklerini ayarlayabilirsiniz. Fakat yayınlanmamış içeriklerin görünmesi problem olacaktır. Bu sorunu da view_unpublished eklentisiyle rahatlıkla çözebilirsiniz.

4- Yayınlama Konumu Olarak Yayınlama Seçenekleri
Yayınlama seçeneklerinde temel olarak Published, Promoted to front page, Sticky at top of lists seçenekleri var. Diyelim ki biz bir slidershow ve farklı yayın alanları oluşturduk ve yayınladığımız içeriklerden kiminin bu alan(lar) içinde görünmesini istiyoruz. Drupalde bunu nasıl sağlayacağız diye kara kara düşünüyorsanız işte cevabı: Custom Publishing Options (custom_pub) eklentisi ile.

Custom Publishing Options
Custom Publishing Options Eklentisi İle Özel Yayın Alanı Ekleme

Resimde de gördüğünüz üzere Featured ve Editor’s pick seçenekleri Custom Publishing Options eklentisi ile eklenen seçeneklerdir.

5- Zamana Bağlı Olarak İçerikleri Otomatik Yayınlama Seçeneği
Scheduler eklentisiyle bu sorunu çözebilir ve yayın zamanını baştan belirleyebilirsiniz. Bu şekilde yayın zamanı gelen içerik otomatik olarak yayınlanır.

6- Editör-Moderatör-Yazar İlişkisi İçinde Kapsamlı Bir Yayın Politikası Sunma
Bu iş için workflow  ve onunla entegre çalışan workflow_extensions tarzı eklentileri incelemeniz gerekiyor. Bu eklentiler ile gazete veya başka yayın politikasının gerektiği yerler için bir çözüm sunabilirsiniz.

Tavsiye Kaynaklar:
https://groups.drupal.org/node/214898