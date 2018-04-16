---
layout: post
published: true
excerpt_separator: <!--more-->
title: Drupalde Eklenti Kurulumu ve Dikkat Edilecek Hususlar
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
redirect_from:
  - /2018/01/01/drupalde-eklenti-kurulumu-ve-dikkat-edilecek-hususlar/    
---
Merhaba arkadaşlar. Bu yazıda temel olarak drupaldeki eklenti kurulumuna ve eklenti kurarken nelere dikkat etmemiz gerektiği hususlarına değineceğim.

<!--more-->

**Drupalde eklentiler** https://drupal.org/project/project_module sayfasında yayınlanır ve hepsi ücretsiz ve açık kaynaktır. Bu eklentilerden istediğiniz birini seçerek indirebilirsiniz. Eklenti sayfasında sizlerden ilgilendiğiniz eklentiyi bulmak için belli başlı kıstaslar verilir ve bu kıstasları girerek size uygun eklentiyi bulursunuz. Bulduğunuz eklenti sayfasında ise tavsiye edilen versiyonlar (Recommended releases) şeklinde bir başlıkla ilgili eklentinin farklı indirme seçenekleri karşınıza çıkar. Burdaki farklı sürümler yeşil, sarı ve pembe renkleriyle sunulur. Bu renkler ise ilgili sürümlerin kararlılık düzeyi (stability) hakkında bilgi verir. Örneğin yeşil renk ile verilenler en kararlı, sarı renk ile verilenler daha az, pembe ile verilenler ise geliştirme sürecinde olduğu için en az kararlı sürümleridir. Tabi bu pembe renkli geliştirme sürecindeki eklentileri kurmayacağınız anlamına gelmesin. Fakat geliştirme sürecindeki bir eklentiyi kurmak sistem sağlığı açısından daha fazla risk oluşturur ve bu eklentilerin bir çoğunun sürüm bilgisinde (Note) geliştirme aşamasındaki bu sürümü kullanmanın sadece tets amaçlı olarak tavsiye edildiğine dair yazılar geçilir. Farklı sürüm kategorilerindeki bu seçimi size bıraktıktan sonra geçeli eklentiyi kurmak için önceden kurulu olması gereken eklentilere (Requirement modules). Drupalde eklenti sayfalarında eklenti için başka bir eklentiye ihtiyaç duyulup duyulmayacağı gerekli eklentiler (Requirement modules) başlığı altında verilir. Bu eklentileri de indirip ayrıca kurmanız gerekmektedir. Gerekli eklentilerin yanı sıra bir de 3. parti kütüphaneler şeklinde kütüphaneler de ilgili eklenti sayfasında gereklidir diye bir ifade geçebilir. Örneğin ColorBox,  lightbox2, shadowbox, plus_gallery vb. eklentiler tam bir kurulum için 3. parti kütüphanenin olmasını zorunlu tutan eklentielrdir.

### Eklenti Kurulumu

Temel olarak eklentiler indirildikten sonra sıkıştırılmış dosya içerisindeki kılasör sitesl/all/modules kılasörünü içerisine çıkarılırken eklenti ile ilgili kütüphaneler ise sites/all/libraries kılasörünün içerisine çıkarılır. Eğer localhostta XAMPP’yi kullanıyorsanız drupal kurulumunuzu htdocs içine yapacağınız için htdocs içindeki bir drupal kılasörü için bu yol C:\xampp\htdocs\drupal\sites\all\modules ve C:\xampp\htdocs\drupal\sites\all\libraries şeklinde olacaktır. Bazen libraries kılasörü oluşturulmamış olabilir (özellikle drupalin ilk kurulumunda). Dolayısıyla sizin bu kılasörü oluşturmanız gerekir. İndirdiğiniz eklenti kütüphanelerini libraries kılasörü içine çıkarmalısınız. Çıkardığınız kılasör ismi ise eklentinin tanıyabileceği isim olmalıdır ki bu isim genelde eklenti sayfalarında notlar düşülerek belirtilir. Diyelim ki sitesl/all/modules altına eklediğiniz colorbox eklentisi sites/all/libraries altına ekleyeceğiniz kütüphaneyi ancak kılasör ismi colorbox olursa görüyor, siz gidip colorbox-master.zip dosyasını sites/all/libraries altına colorbox-master şekliyle açarsanız eklenti bu 3. parti kütüphaneyi tanımayacağı için eklentiniz işlevsiz olur yani çalışmaz. Dolayısıyla kütüphane eklentinin çalışabilmesi için düzgün konumlandırılmalı ve isimlendirme düngün yapılandırılmalı. Gerisi ise yönetim sayfasında eklentiler (modules) başlığına tıklayıp ilgili eklentiyi aktif etmekte.  İlgili eklentiyi aktif et düğmesine tıkladığınızda bu eklenti için gerekli başka eklenti(ler) gerekiyorsa çıkan bir uyarı mesajında bu eklentilerin de kurulması gerekiyor/ kurulsun mu der eğerki sis gerekli eklentileri yukarıda belirttiğimiz ilgili dizine çıkarmışsanız. Eklenti kurulmu başarılı bir şekilde tamamlanırsa eklentinin sağ alt tarafında yardım, ayarlar ve izinler (help, configure, permission) seçeneklerinin bir veya bir kaçı genelde görünür. bu seçenekler ile eklenti hakkında bilgi alabilir ya da eklenti ile ilgili temel ayarları ve bu eklentinin hangi roldeki kullanıcılar tarafından kullanılıp kullanılmayacağı husunu ayarlayabilirsiniz.

### Dikkat Edilecek Hususlar

Drupale eklenti kurulmadan önce oluşabilecek yan etkileri sonradan giderebilmek açısından veritabanı yedeğinin alınması tavsiye edilir. Bunu ise backup_migrate eklentisiyle rahatlıkla yapabilir, oluşacak bir  yan etki durumunda sistemi eski haline getirebilirsiniz.

Kuracağınız eklentinin kütüphanesinin yolunu düzgün veremiyor iseniz ve sites/all/libraries altına koyacağınız kütüphane kılasörünün ismi konusunda tereddütünüz varsa admin paneldeki reports başlığı altındaki status report seçeneğini tıklamanız ve bu raporları incelemeniz tavsiye edilir. Eğer kütüphane yolu yanlışsa buradaki raporlarda bu durum ifade edilir ve kütüphane ismi konusunda gerekli yönlendirmeler burada yapılır.

### Eklenti Kurulumu İle İlgili Tavsiye Yazılar

- https://drupal.org/documentation/install/modules-themes
- http://www.serdartokcan.com/content/drupal-eklentileri
- http://turkcedrupal.org/ders/eklenti-kurulumu-65

### Eklenti Kurulumu İle İlgili Tavsiye Videolar

{% include youtube.html id="e7C_pbhO_ts#t=47" %} 

Umarım yararlı olmuştur.
