---
layout: post
published: true
excerpt_separator: <!--more-->
title: PHP ve MySQL ile İçerik Yönetim Sistemi Yapımı – Öneriler
categories:
  - php
  - icerik-yonetim-sistemleri
  - veritabani
---
Merhaba arkadaşlar. PHP ve MySQL ile İçerik Yönetim Sistemi Yapımına Giriş yazımızda içerik yönetim sistemi nasıl yapılıra dair kavramsal çerçevede birkaç noktaya değinmiştik. Bu yazıda ise içerik yönetim sistemi yapımında işinize yarayabilcek bazı noktalara değineceğim.

Konuyla ilgili önceki yazımda basit bir içerik yönetim sistemi yapımı için PHP de form ile ekleme, silme, güncelleme, listeleme ile biraz da HTML bilginizin yeterli olacağından bahsetmiştim. Şimdi ise içerik yönetim sistemi yapımı ve daha da geliştirilmesi açısından araştırma notlarımdan size tavsiye edebileceğim bazı noktaları sizinle paylaşacağım.

<!--more-->

### 1. Hazır Kodlardan (Snippets) Yararlanmayı Bilin

Tekerleği tekrar tekrar keşfetmek hiç kimseye fayda sağlamaz. Var olanı kullanabilmek daha hızlı ve etkili çözümler elde etmenizde yardım sağlayabilecektir. Tabi sıfırdan kendim yazacam, inat ettim dersen o başka:D. Her neyse, yukarıda da değindiğim gibi madem basit bir içerik yönetim sistemi form aracılığıyla verileri veritabanına ekleme, silme, güncelleme ve veritabanındaki verilerin ekranda gösterilmesinden ibaret o zaman bunlar ile ilgili kodları hazır bulabilir, hemen uygulamanızı geliştirip test edebilirsiniz.

**Örneğin:**

- http://css-tricks.com/php-for-beginners-building-your-first-simple-cms
- http://www.elated.com/articles/cms-in-an-afternoon-php-mysql
- http://www.pixel2life.com/publish/tutorials/890/news_script_using_oop_add_edit_delete_mysql_driven //Gayet güzel
- http://www.rstandley.co.uk/2013/03/05/extending-mysql-connection-oop
- https://github.com/rorystandley/MySQL-CRUD-PHP-OOP
- http://www.codeofaninja.com/2014/06/php-object-oriented-crud-example-oop.html
- http://code.tutsplus.com/tutorials/real-world-oop-with-php-and-mysql–net-1918
- http://www.startutorial.com/articles/view/php-crud-tutorial-part-1  //İlk Kısım
- http://www.startutorial.com/articles/view/php-crud-tutorial-part-2  //İkinci Kısım
- http://www.startutorial.com/articles/view/php-crud-tutorial-part-3  //Üçüncü Kısım
- http://www.phpro.org/tutorials/Creating-A-PHP-Application.html  //Baştan sona bir uygulama
- http://www.codeofaninja.com/2011/12/php-and-mysql-crud-tutorial.html
- http://www.codeofaninja.com/2013/05/crud-with-php-jquery.html
- http://www.killersites.com/community/index.php?/topic/1969-basic-php-system-vieweditdeleteadd-records
- http://www.sourcecodester.com/php/3877/add-edit-and-delete-record-using-phpmysql.html
- http://www.w3cyberlearnings.com/PHP_MySQL_mysqli_for_Book_Record_Management_System_Example // Farklı bir sistemi anlatıyor fakat özünde dört işlem var: ekle, sil, güncelle, göster
- http://www.w3cyberlearnings.com/PHP_MySQL_mysqli_for_Book_Record_Management_System_using_Object-Oriented_Concept  //Yukarıdaki örneğin nesneye yönelik yaklaşımlı hali
- http://www.w3cyberlearnings.com/Php_oop_product_management_product_list //Temelde içerik yönetim sistemiyle aynı
- http://www.sanwebe.com/2013/03/basic-php-mysqli-usage

Yukarıdaki örneklerde bazen dört işlem (ekleme, silme, güncelleme, listeleme) direk verilmiş, bazen bir uygulama içinde verilmiş. Bir kısmında klasik mantıkta PHP kullanılmış fakat çoğunda nesneye yönelik yaklaşımda PHP tercih edilmiş. Özetle, piyasada basit bir içerik yönetim sistemi yapmanıza zemin oluşturabilecek onlarca kaynak var. Önemli olan kullanmasını bilmek.

### 2. Nesneye Yönelik PHP’yi Öğrenmeye Gayret Edin

PHP; WordPress, Joomla, Drupal vb. tanınmış onlarca içerik yönetiminde ve diğer web yazılımlarının dili olması sebebiyle çok hızlı gelişmekte. Son zamanlardaki en büyük açılım ise nesneye yönelik yaklaşıma geçmesiyle oldu. Nesneye yönelik yaklaşım ile beraber PHP’nin yıldızının daha da parlayacağı aşikar. Nesneye yönelik yaklaşım ile PHP’de daha sade, anlaşılır ve yönetmesi kolay yazılımlar yapılması mümkün. PHP’yi biliyorsanız hemen nesneye yönelik PHP’yi de öğrenin ve yazılımlarınızı onunla yapın derim. Hızlı tren varken normal trene razı olmayın:D. İçerik yönetim sistemi ile ilgili karşılaştığım örneklerin büyük bir bölümünde PHP’nin nesneye yönelik yaklaşımı kullanılmıştı.

**Örneğin:**

- http://css-tricks.com/php-for-beginners-building-your-first-simple-cms
- http://www.elated.com/articles/cms-in-an-afternoon-php-mysql

Yukarıda bahsettiğim örnekler nesneye yönelik PHP ile nasıl basit anlamda bir içerik yönetim sistemi hazırlanır onu anlatıyor. Ayrıca hazır kod kullanımına dair verdiğim liklerdeki sayfaların çoğunda da nesneye yönelik PHP kullanımı var.

### 3. Hazır Temalardan Yararlanın

Basit anlamda yazı ekleyip silen ve bunu sade renksiz bir ekranda gösteren bir içerik yönetim sistemi yapmış olabilirsiniz. Peki olayı bir adım daha öteye götürüp örneğin CSS temalarından kullanmayı neden deneyip güzel bir görüntü oluşturmayalım. Piyasada güzel denilebilecek hazır bir çok CSS tema bulmanız içten bile değil.

**Örneğin:**

- http://www.cssportal.com/layout-generator  //İsteğinize göre bir tema şablonu oluşturabilirsiniz
- http://www.free-css.com/free-css-layouts/page1  //ilk aşamada bu tam size göre. Uzmanlaştıkça CSS temaları ve diğerlerini de kullanabilirsiniz.
- http://www.maxdesign.com.au/articles/css-layouts
- http://www.free-css.com/free-css-templates/page1
- http://www.free-css-templates.com
- http://all-free-download.com/free-website-templates/free-css-templates.html
- http://www.csstemplatesfree.org
- http://www.smashingmagazine.com/2008/12/01/100-free-high-quality-xhtmlcss-templates
- http://csstemplatesmarket.com/freecsstemplates/
- http://www.freecsstemplates.com/templates.html
- http://matthewjamestaylor.com/blog/perfect-multi-column-liquid-layouts  //Gayet güzel

### 4. Yazıları Editör İle Yazın

Herhangi bir içerik girerken içeriği bir editör kullanarak yazmak size içerikle ilgili birçok alternatif sunum imkanı verecektir. Hem bir yazı editörünü veri giriş alanına tanımlayıp otomatik çıkmasını sağlamak çok zor bir iş değil. Dolayısıyla alternatif editörlerden birini seçerek yola devam edin.

**Örneğin:**

- http://www.webdesignerdepot.com/2008/12/20-excellent-free-rich-text-editors/
- http://en.wikipedia.org/wiki/Online_rich-text_editor

İlgili linklerde değişik yazı editörleri mevcut. Günümüzde ençok tinymce, ckeditor editörleri yaygın.

### 5. İçerik Yönetim Sistemi ile İlgili Diğer Yapıları Eklemeye Başlayın

Basit bir içerik yönetim sistemini yaptıktan sonra yavaştan yavaşa onu geliştirmek gerek. Dolayısıyla içeriği sadece yetkili kullanıcılar girebileceği için sizin kullanıcılar bölümünüz olmalı ve içerik girerken kullanıcılar içerik girecekleri sayfaya kullanıcı adı ve şifre ile girebilmeli. Dolyısıyla session kısmını da  ekliyor olmanız gerek.

<iframe width="640" height="360" src="http://www.youtube.com/embed/p-uH9c828R8?controls=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

{% include youtubePlayer.html id=bi_U04ZGFD4 %}
{% include youtubePlayer.html id=WLp3Ig4Khnw %} 
{% include vimeoPlayer.html id=254174356 %}


Bundan sonra ise diğer önemli parçaları sırasıyla ekler, ziyaretçiye gösterdiğiniz ekran ile yönetimsel (içerik girişi ve diğer işler) ekranı birbirinden tam ayırarak farklı temalar kullanır ve yola devam…

### 6.  Bootstrap Tarzı CSS Framework Kullanın

Web geliştiricilerin en büyük sıkıntısı farklı ekranlarda çalışabilecek (cross platform) uygulama geliştirebilmektir. Hangi CSS kodunun hangi tarayıcıda çalışıp çalışmadığını bilmek bu anlamda çok önemlidir. Ayrıca ziyaretçilerin beğenebileceği bir görsellik de oldukça önemlidir. Bu anlamda elinizi rahatlatacak ve sizi tüm dertlerinizden kurtaracak bir framework kullanmanız çok iyi olacaktır.

Örneğin:

- http://modernweb.com/2014/02/17/8-bootstrap-alternatives/
- http://www.sitepoint.com/beyond-bootstrap-foundation-frameworks-never-heard/
- http://alternativeto.net/software/bootstrap/
- http://www.tonylea.com/2013/top-5-alternatives-to-twitter-bootstrap/

İlgili linklerde de gördüğünüz üzere birçok alternatif framework sizi bekliyor.

### 7.  jQuery Tarzı Javascript Framework Kullanın

İçerik yönetim sistemlerinde içeriklerin daha güzel sunulmasında javascript kullanımı olmazsa olmazlardan. İstediğimiz bir şeyle ilgili javascript kodu sıfırdan yazmak oldukça zahmetli olduğundan olayı çok daha hızlandıran, bir javascript framework ile gerçekleştirmek çok daha efektif bir çözüm. Dolayısıyla günümüzde en çok kullanılan javascript frameworkü  olan JQuery’i kullanabileceğiniz gibi birçok alternatif frameworkü de ihtiyacınız doğrulturunda kullanabilirsiniz.

**Örneğin:**

- http://www.w3schools.com/js/js_libraries.asp
- http://wearepropeople.com/blog/a-list-of-top-javascript-frameworks
- http://www.ssiddique.info/10-best-javascript-framwork-2013.html
- http://jonathanmh.com/best-javascript-mvc-frameworks-2013-2014/
- http://en.wikipedia.org/wiki/List_of_JavaScript_libraries


Şunu da hatırlatma da fayda var. Birçok javascript framework JQuery bağımlı çalışıyor. Yani Jquery gerekli.

### 8. İçerik Yönetim Sistemini Bir PHP Framework Kullanarak Yapın

Şu ana dek hep nesneye yönelik yaklaşımlı PHP ile içerik yönetim sistemini tavsiye ettim. Şimdi ise PHP frameworklerinden birini seçerek nesneye yönelik PHP kullanarak içerik yönetim sistemi yapmanızı tavsiye ediyorum. Framework kullanmak, içerisindeki hazır yapılar sayesinde işinizi hızlandıracağı gibi güvenlik ve performans anlamında da elinizi oldukça rahatlatacaktır. Şuan mevcut frameworklerde belki kullanım olrak değil ama geleecek vaat eden anlamında laravel oldukça ışıltılı görünmekte. Tabi birçok alternatifini var istediğinizi kullanabilirsiniz.

**Örneğin:**

- http://www.sitepoint.com/best-php-frameworks-2014/
- http://mashable.com/2014/04/04/php-frameworks-build-applications/

### 9. İçerik Yönetim Sistemi Kullanın

Sıfırdan başlayıp ekleme yapa yapa kocaman bir içerik yönetim sistemi yapmak masraflı diyorsanız o zaman bir içerik yönetim sistemi kullanmak tam size göre olabilir. Piyasada farklı birçok platform için çalışabilecek onlarca hazır içerik yönetim sistemi var. Günümüzde bunların en meşurları WordPress, Joomla ve Drupal (hepsi de PHP dili ile geliştirilmiş). Farklı platform ve dillerle geliştirilmiş birçok örneğe aşağıdaki  linkten ulaşabilirsiniz.

-[http://en.wikipedia.org/wiki/List_of_content_management_systems](http://en.wikipedia.org/wiki/List_of_content_management_systems)

Özetle yararlanabileceğiniz o kadar çok kaynak, kullanabileceğiniz o kadar çok yapı var ki anlatmakla bitmez.

Umarım yararlı olmuştur.
