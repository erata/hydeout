---
layout: post
published: true
excerpt_separator: <!--more-->
title: Drupalde Spam Kullanıcı Kayıtları ve Spam Yorumları Önleme
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
---
Spam, ticari ya da diğer amaçlarla isteğimiz dışında gelen mesajlardır. Reklam ve propaganda yapma  amacıyla kullanılabilirler.  Günümüzde kullanıcı etkileşiminin yoğun olduğu sitelerin en büyük sıkıntılarından biridir. Özellikle forum siteleri gibi gerek kullanıcı kayıtlarının çok olduğu gerekse de mesajlaşmanın çok olduğu sitelerin en büyük baş ağrılarından biridir. Peki baş edilemez mi?

<!--more-->

Drupalde  Spam’a Karşı Koyma Yolları
Drupalde spamlara karşı koymanın birçok yolu mevcut. Öyle ki drupalmodules.comde spam diye arattığımızda şuan itibariyle 13 eklenti listelenmekte. Ayrıca bunlar dışında da spamlara karşı hatırı sayılır bir eklentinin olduğunu söylemek mümkün. Önemli olan spamlardan kalıcı bir şekilde en iyi nasıl kurtulabileceğimizi ve bunu hangi eklenti ya da eklenti kombinasyonlarıyla yapabileceğimizi tespit etmek.

Spamdan Kurtulmak İçin Tavsiye Eklentiler
captcha ve captcha + image_captcha_refresh kullanımı spamı engellemek için yeterli olmamaktadır. Ben captcha‘nın hem matematiksel kısmını hem de resimsel kısmını denedim para etmedi. Captcha ile ilgili farklı arayışlar içindeyken recaptcha ve  riddler eklentileriyle spamların engellenebildiğini bariz bir şekilde gördüm.

captcha + recaptcha : Ben recaptcha kullanıyorum ve gayet memnunum (***).

captcha + riddler : Riddler ile özel sorular hazırlanıp buna yanıt isteniyor. Fakat sorduğunuz sorunun kapsamı dış ülkelerden gelen ziyaretçilerin etkileşimde bulunmasını engelleyebileceği gibi aynı ülke içinden gelen ziyaretçileri de engelleyebilir. Örneğin ben riddler ile özel sorular sorulan yabancı bir sitede yorum yapmak istediğimde soruyu bilemediğim için yorum yapamıyorum. Dolayısıyla riddler, spam için kesin çözüm sağlasa da yabancı ülkeden gelen ziyaretçi etkileşimine neşter vurabilmektedir.

captcha + hidden_captcha : Hidden Captcha’yı kullanmasam da çalışma mantığınına göre kesin bir çözüm sağladığı kanısındayım. Olay ise şu: spamlar boş gördüğü her yeri doldurma eğilimindeler. Eğer doldurulmaması gereken ve kullanıcıların görünümünden sakladığımız bir alan olursa formda onu kim doldurabilir: tabi ki spamlar. Bu şekilde basit bir yaklaşımla spamlar engelleniyor.

 !  Ben reklam içerikli spam maillerden kurtulmak için ilk önce captcha eklentisini kurdum sorun çözülmedi. Daha sonra image_captcha_refresh eklentisiyle resimsel captcha ile sorunu çözerim diye düşündüm yine olmadı. Aklıma daha önce kullandığım riddler eklentisi geldi fakat kendi oluşturacağım özel sorulara (Örneğin Türkiye’nin başkenti neresi?) yabancı ülkelerden gelen ziyaretçilerin cevap verememesi durumu aklıma geldi ve vaz geçtim. Sonra bir de recaptcha eklentisini deneyeyim dedim ve gördüm ki spam yorumlar mesajlar artık gelmiyor.

spambot eklentisi, www.stopforumspam.com da kara listeye düşenlere göz atarak ona göre önlem alan bir yaklaşım içeriyor.

mollom eklentisi ile içerik web servisi kullanılarak taranıyor ve spam olup olmamasına göre bir işlem uyguluyor. İçerik analizinin yapıldığı bu yaklaşım oldukça güvenilir bir çözüm sağlıyor. Fakat, belli bir çıtanın üstünde yoğunluğu olan bir siteye sahipseniz biraz para ödemeniz gerekebilir bu hizmetten yararlanmak için.

honeypot, botcha, spamicide  ve antispam eklentilerinin de yine spamdan korunmada başarılı sonuçlar alan eklentiler olduğunu belirteyim.

Elbette ki spam ile ilgili tüm eklentileri burda ele almamız mümkün değil fakat yukarıdaki seçeneklerden herhangi birini tatbik etmeniz büyük bir oranda sorununuzun çözülmesini sağlayacaktır.

### Tavsiye Kaynaklar:
http://www.ostraining.com/blog/drupal/block-spam-registrations-drupal/
http://getlevelten.com/blog/colin/spam-be-gone-10-spam-blocking-drupal-modules
http://raisedbyturtles.org/stopping-spam-comments-in-drupal-7/
http://hygen.net/blog/drupal/prevent-automated-drupal-user-registration-spam
