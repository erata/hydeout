---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Drupalde Nesneye Yönelik Yaklaşım: Node’den Entity’e Geçiş'
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
---
Merhaba arkadaşlar. Bu yazıda son zamanlar drupalde üzerinde çokça durulan bir kavram üzerinde duracağız: Entity.

<!--more-->

Node, drupal 6’ya değin drupalle birlikte anılan onun en önemli bir yapısıydı. Drupal 7’den itibaren “entity” denilen bir kavram “node”nin yerini almaya başladı. Öyleki, drupal 7’ye kadar piyasaya sürülen eklentiler (modules) hep “node” bazlıydı ve bu durum drupal 7’den itibaren değişti.

Drupal 6’ya değin drupal “node” bazlı bir yapı üzerine kuruluydu. Bu yapı, drupalin o zamana kadar atılım yapmasını sağlayan en güçlü yanıydı. Fakat gün geçtikçe “node” bazlı bir yapı drupal’in gelişimini sekteye uğratıcı bir hal almaya başladı. Node’nin temelde birçok gerekli gereksiz alanı içeren bir yapıda olması içerik oluşturup kaydetmede veritabanı üzerinde bir yük oluşturuyordu. Node’nin bu durumu node bazlı eklentilerde de kendini daha fazla iş yükü olarak gösteriyordu. Farklı içerik türleri arasındaki ortak yapılar… Bir içerik içerisinde içerik için gerekli olmayan fakat node ile gelen gereksiz alanlar… Kısacası Drupal node bazlı yapıdan gelişimi açısında daha esnek bir yapıya geçmeliydi. Drupal 7 bu eksen değişimi için çok önemli bir geçiş noktası oluşturdu. Şuan node bazlı eklentilerle birlikte entity bazlı eklentiler oluşturulmakta ve entity bazlı eklentilerin sayısı gün geçtikçe daha da fazlalaşmakta.

Entity bazlı yapı ile beraber drupal daha esnek bir yapıya kavuşacaktı. Artık “her şey bir node” anlaşından “her şey bir entity” anlaşı hakim olacaktı. Bu anlayışa göre “node bir entity”dir. Yani node entity’den oluşmaktadır. Yani entity drupal’in en üst öğesidir.

Entity, drupalin nesneye yönelik yaklaşımıdır. Her şey entity’den türeyecektir. içerik (content), kullanıcılar (user), yorumlar (comments), sınıflandırma (taxonomy) hepsi birer entity türüdür ve entity’den oluşmaktadır.

Aşağıdaki video entity, node ve diğer önemli yapılar üzerinde gayet net anlatımda bulunmuş.

{% include youtube.html id="coephBu07Ks" %}

Özetle entity, drupalin devrimidir. Drupal 6’ya kadar “her şey bir node” idi. Drupal 7’den itibaren bu anlayış değişmeye başladığı gibi drupal 8’de entiy çok daha fazla hissedileceği açık ve net görülmekte. Drupal 8 eklentilerinin entity ağırlıkta oluşturulması bunu kanıtlar nitelikte.

### Kaynaklar:
- https://www.drupal.org/node/1261744
- http://evolvingweb.ca/story/drupal-7-entities-what-are-they-and-what-are-they-good
- http://www.youtube.com/watch?v=coephBu07Ks
