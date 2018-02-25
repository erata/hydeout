---
layout: post
published: true
excerpt_separator: <!--more-->
title: Drupal Views Eklentisi ve Önemi
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
---
Merhaba arkadaşlar. Bugün sizlere drupaldeki Views eklentisinden ve neden drupal için çok önemli bir eklenti olduğundan bahsedeceğim.

Views eklentisi drupal ile geliştirilen büyük projelerin olmazsa olmazlarından biridir. Drupali drupal yapan, onu anlamlı yapan sac ayaklarından biridir.

<!--more-->

Peki Ne İş Yapar Views, Nedir Views’i Bu Kadar Önemli Yapan?
Views, veritabanındaki kayıtları sizin belirtilediğiniz kıstaslar doğrultusunda çeker ve yine sizin belirlediğiniz görüntü formatı içerisinde ekrana getirir. Bu anlamda Views hakkıda bilmemiz gereken en öncelikli şey onun sorgu oluşturucu olmasıdır (Views is a query builder).

Views Giriş Ekranı
(Kaynak:acquia.com Views Giriş Ekranı)

Veritabanından çekilip ekrana getirilen bu kayıtlar views ile bir cck alanı içerisinde (içerik türü alanı – entity views attachment eklentisiyle), bir blok içerisinde, bir sayfa içerisinde, vb. değişik yerlerde ekrana yansıtılabilir. Karmaşık ve bir o kadar da zor veritabanı sorguları views ile hiç kod yazmadan bir ekran vasıtasıyla dile getirilir ve sorgu sonucu da yine tanımlı formatlar vasıtasıyla ya da bizim belirleyeceğimiz formatla ekranın görünmesini istediğimiz yerinde ekrana yansıtılır. Kısacası views ile, yazdığımız sorguların (views ekranından bikaç ayar yaparak dile getiriyoruz – kod yazmak yok) belirlediğimiz alan(lar)da, belirlediğimiz formatlar doğrultusunda görüntülenmesini sağlıyoruz.

Views Kullanıcı Paneli Ekranı
(Kaynak:acquia.com Views Kullanıcı Paneli Ekranı)

Views, token eklentisi ile beraber site dahilinde kullanılabilecek tüm parametrelere nüfuz eder ve size veriler üzerinde tam denetim yapmaya, onlarla farklı açılardan yapboz yapmaya olanak sağlar. Views, ayrıca ekrana yansıtacağınız verilere CSS sınıflar tanımlamaya, verileri HTML taglar arasına almaya, verileri gösterbileceğiniz formatlar sunma ya da kendi özel sunum formatınızı oluşturma vb. birçok farklı şeye izin verir ve görsel olarak da size tam denetim sağlar.

Drupal.org’da yer alan Views basics (Views Temelleri) ile views kurulumu, yeni bir views oluşturma, panel ayarı, filtreleme ayarı, içerik alanı (field) ekleme, sıralama, vb. birçok konuyu irdeleyebilirsiniz. Ayrıca özenle seçtiğimiz aşağıdaki kaynaklardan da istifade edbilirsiniz.

[video:http://www.youtube.com/watch?v=3WVm0RiH0GE#t=311]
Views İle İlgili Tavsiye Kaynaklar:
http://www.acquia.com/blog/drupal-views-sql-analogy-easier-way-explain-views
http://www.acquia.com/blog/totally-beginner-tutorial-views-drupal-7
http://turkcedrupal.org/ders/views-eklentisine-giris-74 (Türkçe)
http://drupalize.me/videos/overview-views
http://drupalize.me/videos/overview-views-user-interface
http://www.drupalgardens.com/content/new-views-tutorials-4-part-intro
Drupal 6’da Views Kullanımına Dair Kapsamlı Bir Vidyo (Türkçe)
Drupal 7 views 3x kullanımı (Türkçe altyazılı)
Drupal 7 Views Module Tutorial Series (10 Bölümlük Vidyo Serisi)
Nodeone Views and Page Manager (Views Vidyo Serisi)
