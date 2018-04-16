---
layout: post
published: true
excerpt_separator: <!--more-->
title: >-
  Drupalde Bir Views Üzerine Çoklu Görüntü Ekleme ve Görüntü Kapsamlarını
  Belirleme (override block or page in multiple displays)
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
redirect_from:
  - /2018/01/01/drupalde-bir-views-uzerine-coklu-goruntu-ekleme-ve-goruntu-kapsamlarini-belirleme-override-block-or-page-in-multiple-displays/    
---
Merhaba arkadaşlar. Bugün sizlerle bir views oluştururken dikkat etmemiz gereken hususlardan birine değineceğiz. Özetle konu, views kapsamını belirlemekle ilgili. Yani yapacağımız değişikliklerin sadece o an üzerinde çalıştığımız öğede (blok, sayfa, ek, vb.) mi etkili olacağı ya da aynı views içerisindeki diğer öğeleri etkileyip etkilemeyeceği, işte esas konumuz bu.

<!--more-->

bir views ile çoklu görüntü oluşturma

Views ile benzer yapıda görüntüler elde ederken her seferinde “add new views” demenize gerek yoktur. Bunun yerine bir “Master” görüntü oluşturduktan sonra (bu arada Mater sayfayı görebilmek için views->settings->Always show the master display yolunu izleyin) aynı views örneği içerisinde bu Master görüntüyü miras alan, benzer ama farklı birçok görüntü oluşturabilirsiniz.  Bunu ise +Add seçeneği ile Attachment, Block, Eva Fields, vb.   öğelerden istediğinizi Master görüntüdeki ayarları miras alacak şekilde yapabilirsiniz.

Aynı Master Görüntüyü Miras Alan Diğer Görüntüler Nasıl Birbirinden Farklı Olacak?
views override for multiple displays

Cevap ise ayarları yaparken For ile başlayan kapsam belirleme kısmında gizlidir. Yani adam diyor ki sen bu ayarı yapıyon ama kapsamın ne olacak? ilgili menülerde ise All display – except override (tüm views üzerindeki görüntülerde etkili olsun overriden olanlar hariç), this block/page/attahment – override (o anki üzerinde çalıştığın görüntüde etkili olsun), revert to default (galiba Master ayarını kullan demek istiyor)  seçenekleri var.

Eğer siz oluşturduğunuz görüntünün diğerlerinden faklı ve yaptığınız değişikliklerin o görüntü kapsamında kalmasını istiyorsanız this block/page/… vb (override) seçeneğini seçmelisiniz. Aksi takdirde All display seçeneği işleme konacağı için diğer tüm görüntüler (Mater da dahil) hepsi bundan etkilenecektir.

Kapsamı, üzerinde çalışılan görüntü olarak belirlemek için override seçeneğinin kullanımına yönelik örnek senaryolar ile durumu somutlaştıracak olursak:

Master’ı miras alıp görüntü oluşturuyor iken Master’da olmayan faklı bir field eklemek istiyorsanız ya da Master’da olanı çıkarmak istiyorsanız  fakat aynı views içerisindeki diğer görüntülerin bu durumdan etkilenmesini istemiyorsanız…
Filtreleme yaparken aynı views içindeki her blok görüntüsü için farklı bir kategori eklemek istiyorsanız…
Kısacası, Master görüntüyü miras alıp her görüntü için özelleştirmek istiyorsanız
override yapmanız gerekiyor…
