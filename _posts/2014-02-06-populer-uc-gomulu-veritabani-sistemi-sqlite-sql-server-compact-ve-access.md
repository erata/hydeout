---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Popüler Üç Gömülü Veritabanı Sistemi: SQLite, SQL Server Compact ve Access'
categories:
  - veritabani
tags:
  - sqllite
  - ' sql-server-compact '
  - access
redirect_from:
  - article/populer-uc-gomulu-veritabani-sistemi-sqlite-sql-server-compact-ve-access
  - /2018/01/01/populer-uc-gomulu-veritabani-sistemi-sqlite-sql-server-compact-ve-access/    
---
Merhaba arkadaşlar. Bu yazıda, yazılım geliştiricilerin oldukça çok kullandıkları üç gömülü (embeded) veritanı sistemine değineceğiz: SQLite, SQL Server Compact ve Access.

<!--more-->

Gömülü Veritabanı Sistemi Nedir?
Çalışabilmesi için herhangi bir veritabanı sunucusuna ihtiyaç duymayan veritabanı sistemleridir. Örneğin SQLite, Microsoft Access, SQL Server Compact, vb. veritabanları herhangi bir sunucuya ihtiyaç duymadan çalışırlar. Aksine; MySQL, PostgreSQL, Oracle, SQL Server, Sybse, vb. veritabanları ise çalışabilmek için veritabanı sunucusuna ihtiyaç duyarlar. Gömülü veritabanı sistemleri, sunucu gerektiren veritabanı sistmleri kadar fonksiyon ihtiva etmezler ve kısıtlı büyüklükteki (sunucu bazlı veritabanına göre) veriyi destekler. Özellikle cep telefonları, internet tarayıcıları, vb. başlıca gömülü veritabanı kullanım alanı olmakla birlikte gömülü veritabanları birçok alanda kullanılırlar.

Access
Microsoft Ofis uygulamasının bir parçası olan Access, “veritabanı nedir”i öğrenmenin ilk durağıydı. Access’in kullanım kolaylığı ve basitliği onun oldukça popüler olmasını sağladı. Acess, özellikleri bakımından her ne kadar sunucu bazlı veritabanlarıyla kıyaslanamayacak olsa da küçük verilerin depolandığı uygulamalar için oldukça iyiydi.

Access, az veri (en fazla 2GB)  gerektiren, gömülü veritabanı olarak  kullanım için uygundur. Biraz fazla fonksiyon ve veri gerektiren işler Access’i aşar.

SQL Server Compact (SQL CE)
Bir diğer Microsoft ürünü olan SQL Server Compact, SQL Server’in  gömülü versiyonu olarak düşünülmüştür ve ücretsizdir. Gerek web uygulamalarında gerekse masaüstü uygulamalarında kullanılabilir. Web Matrix’in desteklediği veritabanları arasındadır. 4GB’a kadar destekler. Access’e göre daha fazla işlevseldir. Microsoft Studio’nun tam desteğini almıştır. Fakat Access de olduğu gibi sadece windows tabanlı platformlar için uygundur.

SQLite
Bir önceki yazımızda da değindiğimiz SQLite, gömülü açık kaynak bir veritabanı sistemidir. Access ve SQL Server Compact’ın aksine birçok platformu destekler ve daha büyük veri miktarını (32TB) destekler. Birçok platformu desteklemesi ve açık kaynak oluşu ve güvenilir oluşu kullanımını artırmıştır.

SQLite, SQL Server Compact ve Access Karşılaştırması için tıklayınız…

Ayrıca 1, 2, 3, 4 yazılarını kumanız faydalı olabilir.
