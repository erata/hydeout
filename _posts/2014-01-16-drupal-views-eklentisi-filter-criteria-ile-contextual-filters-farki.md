---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Drupal Views Eklentisi: Filter Criteria ile Contextual Filters Farkı'
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
---
Merhaba arkadaşlar. Bugün sizlerle views’ın sıklıkla karıştırılan iki öğesini ele alacağız: Filter Criteria (Temel Filtreleme Kriteri) ile Contextual Filters (İçeriğe Göre Filtreleme). Fakat bu iki öğenin yaptığı iş, tür açısından benzer nitelikte olduğundan birçoğumuz tarafından karıştırılabiliyor. Özellikle de Contextual Filters konusunda ciddi bir bilgi eksikliği söz konusu olduğundan bu durum içinden çıkılmaz bir hal alabiliyor. Bu yazıyı esasında “Contextual Filters” öğesinin biraz daha anlaşılmasına  katkıda bulunmak amacıyla ele alıyorum.

<!--more-->

Temel Filtreleme Kriteri (Filter Criteria) ile İçeriğe Göre Filtreleme (Contextual Filters)
Yukarıda da değindiğim gibi bu iki filtreleme mekanizması işlev türü olarak benzer işlevlere sahiptir (filtreleme yaparlar) fakat bu yine de aralarında çok ciddi işlev farklılıkları vardır.

Temel filtreleme mekanizmasında (Filter Criteria’da) filtrelenecek koşullar,durumlar, vb. baştan belirlenebilecek türdendir. Örneğin içeriğin yayınlanmış olması, makale türünde olması, kategorisinin drupal olması, vb. baştan belirlenip verilebilen filtrelelere örnektir.

İçeriğe göre filtreleme mekanizmasında (Contextual Filters) filtre baştan belli değildir, filtrenin belirlenmesinde koşullar önem arzeder. Filtre, içeriğin durumuna göre dinamik olarak belirlenir ve oluşacak sonuç da buna göre oluşur. Örneğin okuduğunuz bir yazının yazarının diğer yazılarını görmek isterseniz veya tersten düşünecek olursak bir yazardan onun yazılarına ulaşmaya çalışacak olursak, vb. yani filtrelenecek öğenin içeriğe göre dinamik olarak belirleneceği durumlarda Contextual Filters kullanılır.

(Resim Kaynağı: acquia.com)

Kısacası, temel filtreleme mekanizmasında filtreler baştan el ile atanarak belirlenebilir ve filtrenin belirlenmesi bir koşul sonucu değildir. Fakat içeriğe göre filtreleme mekanizmasında filtre, içerikteki değişkenlerin durumuna göre dinamik olarak belirlenir. “Yazarın diğer yazıları” örneğinde olduğu gibi yazarın kim olduğu baştan belli değildir. Dolayısıyla ortaya çıkacak sonuç (diğer yazıları) ancak yazar ilgili içerikten tespit edildikten sonra listelenebilecektir.

Örnekler vererek açıklamaya çalıştığım gibi baştan belli (statik) filtreler için temel filtreleme mekanizması (Filter Criteria) kullanılırken filtrenin içerik değişkenlerine bağlı olarak belirleneceği (dinamik) durumlarda (Contextual Filters) kulalnılır.

Konuyla ilgili daha fazla bilgili almak için özellikle bu yazıdan ve aşağıda verdiğim diğer yazılardan yararlanabilirsiniz.

### Konuyla İlgili Tavsiye Kaynaklar:
https://drupal.org/node/1578558 (*** Contextual Filters)
http://marcdrummond.com/drupal/2011/05/20/new-views-interface-david-rothstein-drupal-camp-twin-cities-2011
Drupal 7 Advanced Views Tip: Contextual Filters (her iki filtreleme yönetemini konu alan bir video)
