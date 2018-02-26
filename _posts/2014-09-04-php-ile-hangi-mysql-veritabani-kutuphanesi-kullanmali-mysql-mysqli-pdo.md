---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'PHP ile Hangi MySQL Veritabanı Kütüphanesi Kullanmalı: MySQL, MySQLi, PDO'
categories:
  - veritabani
tags:
  - mysql
  - php
  - pdo
  - mysqli
---
Merhaba arkadaşlar. Bu yazıda PHP ile kullanabileceğimiz MySQL kütüphanelerinden ve kodlama yaparken hangi kütüphaneyi tercih etmemiz gerektiğinden bahsedeğim.

<!--more-->

Bu yazıyı yazarken şu yazıdan esinlendiğimi baştan söyleyeyim. Bildiğiniz üzere PHP ile MySQL veritabanı üzerinde işlem yaparaken MySQL’in bize sağlamış olduğu bağlantı yapıları (fonksiyonları) kullanmaktaydık. Fakat zamanla bu yapı piyasaya sonradan giren MySQLi, PDO yapıları ile gözden düştü. Sonuçta MySQL’in PHP ile kullanılan bu bağlantı yapısı için artık desteklenmeme kararı alındı. Dolayısıyla PHP ile MySQL veritabanı işlemlerini gerçekleştirmek için artık iki seçeneğimiz kalıyor: MySQLi ve PDO. Peki özetle bunlar hangi açıdan birbirinden ayrılıyor ve hangisini seçmeliyiz derseniz anlatmaya başlayayım.

PHP ile MySQL Veritabantı İşlemleri İçin Kütüphaneler:

### MySQL

Bir zamanlar vazgeçilmezlerdendi. Artık demode oldu. Yeni yazılımlar için kullanılmaması en mantıklısı, çünkü desteklenmiyor artık.

### MySQLi

Daha önceden MySQL’in veritabanı fonksiyonları kullananlar için öğrenmesi oldukça kolay.
MySQL veritabanına özel bir yapı olduğu için MySQL veritabanındaki değişikliklere oldukça duyarlı.
Nesneye yönelik desteği var ve hızlı.

### PDO

Aralarında MySQL, PostgreSQL, SQLLit, IBM DB2, Sybase, Oracle Call Interface vb. veritabanlarının da bulunduğu 12 farklı veritabanı için genel bir destek sağlar. Böylece uygulama veritabanını değiştirmek, bağlantı cümleciğini değiştirmek kadar kolay hale geliyor ki en büyük özelliği de bu. Yani veritabanları için ortak bir bağlantı platformu sağlıyor.
Hem nesneye hem de prosedüre yönelik desteği var ve hızlı.
MySQLi ve PDO’dan hangisini seçeyim sorusu size kalmış.

**Ama eğer:**

Farklı veritabanları arası hızlı geçiy yapabilmek sizin için önemli ise;
Farklı veritabanlarında çalışan ürün sürümleri almanız gerekiyorsa
hiç düşünmeden PDO’yu seçin derim.

**Fakat:**

Yukarıda belirtilen gereksinimler ortada yokken sırf ileride bir gün işime yarar diye PDO’yu seçmeyi düşünüyorsanız
MySQLi’yi öğrenmenin PDO’ya göre daha kolay olduğunu;
MySQLi’nin MySQL veritabanındaki değişimlere daha hasas
olduğunu aklınızda bulundurmanızda fayda var.

### Kaynaklar:
http://www.rudivisser.com/Development/Resource/when-to-use-mysql-vs-mysqli-vs-pdo-in-php
http://code.tutsplus.com/tutorials/pdo-vs-mysqli-which-should-you-use–net-24059
