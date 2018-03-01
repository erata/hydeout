---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Drupalde Başlıca CSS, JS Ekleme ve Kullanma Yolları'
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
---
Merhaba arkadaşlar. Bu yazıda, başlıca CSS ve JS ekleme yollarından bahsedeceğiz. Drupal’i biraz kurcalayanlar Drupal’de birçok CSS ve JS ekleme seçeneğinin olduğunu görecektir. Haliyle bu durum sitede performansı önceleyenler için oldukça büyük bir soru işaretine dönüşerek “Hangisini Kullanmalıyım?” sorusunu sıklıkla gündeme getirecektir. Şimdi sözü uzatmadan başlıca CSS ve JS kullanım yollarından ve neye göre tercih edilmesi gerektiğinden bahsedelim. Bu yazıyı yazarken kaynak olarak özellikle bu yazıdan yararlandığımı belirteyim.

<!--more-->

### DRUPALDE CSS/JS EKLEME YOLLARI

#### 1. drupal_add_css(), drupal_add_js() ile CSS/JS Ekleme

Genel CSS/JS ekleme yoludur. Çoğu geliştirici bu yol ile CSS/JS ekler.

**Avantajları:**

Kullanımı kolaydır ve istediğimiz zaman CSS/JS ekleme,
Satıriçi (inline) CSS/JS ekleme,
Konu ile ilgili geniş kaynak/döküman bulabilme,
Eklenen dosyaların ön belleğe (cache) alınmasına imkan tanıma,
Koşullu durumlar için kullanabilme (tarayıcı,vb)

**Dezavantajları**:

Herhangi bir yerde kullanılabilir olmasının getirdiği karmaşa,
Birçok dosya ekleme durumunda ortaya çıkan dağınık görüntü,
Kod bağımlılığından dolayı CSS/JS dosya isimleri değiştiğinde kodda yer olan dosya isimlerini de değiştirmek gerekmesi

#### 2. “.info” Dosyası ile CSS/JS Ekleme

**Avantajları:**

Kullanılan CSS/JS dosyalarını  anlamanın çok kolay olması,
Daha iyi dosya birleştirmeye (aggregation) imkan vermesi,
preprocess() tarzı fonksiyonlara gerek kalmaksızın tüm sayfalarda kullanılabiliyor olması,
Temalar içim standart olması

**Dezavantajları:**

İstenilmeyen sayfalara da ekleniliyor olması,
CSS/JS eklemenin oldukça kontrolsüz yapılıyor olması,
 

#### 3. [‘#attached’] ile CSS/JS Ekleme

**Avantajları:**

CSS ve JS eklemek için en iyi yol olarak belirtiliyor,
CSS/JS kütüphaneleriyle çok uyumlu çalışır,
Eklenmiş (attached) her hangi bir veri ile çalışabilir,
Çoklu dosya eklemek kolay,
Formlar için en iyi seçenek

**Dezavantajları:**

CSS/JS eklemek için çoklu ekleme yapmaya (multiple attachment) gerek duyulması,
Dsoya yolu ve adına bağımlılık

#### 4. drupal_add_library() ile CSS/JS Ekleme
 
**Avantajları:**

CSS/JS’nin farklı sayfalardaki tekrar kullanımı için oldukça iyi,
Dosya yolu ve adı fonksiyon içinde saklanır,
Diğer projelerdeki kütüphaneleri kullanmanıza olanak tanıması,
Çoklu dosya eklemenin kolay olması
Kütüphane içinde farklı kütüphanelerin kullanılabilmesi
Dezavantajları:

Daha fazla kod yazımının gerekmesi,
kütüphanedeki tüm dosyalarının ekleniyor olması

#### 5. hook_css_alter(&$css), hook_js_alter(&$js)

**Avantajları:**

Elemanları ağırlıklarına göre yeniden yapılandırılabilmesi,
Dosyaları birleştirmeye gerek kalmaksızın (aggregation) silebilme,
Dosya yolunu değiştirmenin kolay olması (Örneğin JS dosya yolu olarak CDN kullanma)
Dosya birleşimini (aggregation)

**Dezavantajları:**

Bu yolla dosya eklemenin kötü bir seçenek olması,
Dosyalar arasında karmaşaya düşebilme ihtimalinin fazla olması

#### 6. drupal_add_html_head()

Avantajları:
Dezavantajları:

7. Including as html in .tpl.php or printing it
Avantajları:
Dezavantajları:
 
### Kaynaklar:
- https://drupal.org/project/cpn  (Süper Eklenti)
- https://drupal.org/project/css_injector
- https://drupal.org/project/js_injector
- http://wearepropeople.com/blog/7-ways-to-add-custom-js-and-css-to-a-page-in-drupal
- [‘#attached’] ile CSS/JS Ekleme
- http://www.metaltoad.com/blog/what-i-learned-today-drupal-attached-awesomeness
- http://www.webtipblog.com/include-javascript-css-drupal-form-using-attached/
- https://api.drupal.org/api/drupal/includes!common.inc/function/drupal_add_js/7
- https://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_add_css/7
- https://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_add_library/7
- https://drupal.org/node/304255
- http://adaptivethemes.com/how-to-add-css-files-in-drupal-7
- http://www.samwirch.com/blog/adding-javascript-drupal-7
- http://zerotodrupal.com/content/better-way-add-javascript-and-css-hooklibrary
- http://buildamodule.com/video/drupal-6-development-and-tools-essential-concepts-how-to-add-javascript-and-css (Video)
- https://www.jnorton.co.uk/blog/drupal-tutorial-remove-system-css-js-files (system dosyalarını silerek bandwith düşürme)
