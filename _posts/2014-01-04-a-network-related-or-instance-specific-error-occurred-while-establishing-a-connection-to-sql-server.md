---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'SQL Server: A network-related or instance-specific error'
categories:
  - veritabani
tags:
  - sqlserver
redirect_from:
  - /2018/01/01/a-network-related-or-instance-specific-error-occurred-while-establishing-a-connection-to-sql-server/   
---
> TITLE: Connect to Server
  Cannot connect to xx.xxx.xxx.xx\MSSQLSERVER.
  ADDITIONAL INFORMATION:
  A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: SQL Network Interfaces, error: 25 – Connection string is not valid) (Microsoft SQL Server, Error: 87)
  
  <!--more-->
  
Merhaba arkadaşlar. Sql Server ile uzak masaüstü bağlantısı sırasında meydana gelen yukarıdaki hata durumu eğer ki konuya yabancı iseniz biraz sinir bozucu olabilir. Çünkü hataya neden olabilecek hiç bir şey yok gibidir. Örneğin network ve veritabanı izinleri verilmiştir. Ama nedeni bilinmez bir türlü uzak masaüstündeki veritabanına bağlanılamaz ve yukarıdaki hatayı verir. Hata ise dışarıda değil, içeridedir. Yani SQL Server kurulumu sırasında gözden kaçan küçük bir detayda gizzlidir. Normalde biz SQL Server’i kurarken bir başlarız install> next > next> sonuna kadar next… ve default instance olaraka ise “MSSQLSERVER” kurmuş oluruz, bu durumun ileride bize ne gibi sonuçlarla geleceğini bilmeden.  Çünkü default kurulumlarda atanan MSSQLSERVER instance’si ileride uzak masa üstü bağlantısı (remote desktop connection) sırasında kdv olarak yukarıdaki mesajla geri dönecektir. Eğerki siz Sql Server’ı default instance ile yani MSSQLSERVER ile kurmuş iseniz ve Sql Server ile uzak masaüstü yapmaya çalışıyorsanız bu sorunla karşılaşmanız an meselesi.
Çözüm ise Sql Server’i MSSQLSERVER’dan farklı bir instance ile yeniden kurmak veya default instance dışındaki (MSSQLSERVER) bir instance ile (mesela X, Y, PROJE, AHMET, MEHMET ..) uzak masaüstü bağlantısı yapmaya çalışmak. Sonuçta gerekli ağ (network) ve veritabanı izinleri verilmiş olduğunu farzedersek xx.xxx.xxx.xx\AHMET veya xx.xxx.xxx.xx\MEHMET tazında bir bağlantı şekli bizim için çözüm olacaktır.
Umarım yararlı olmuştur.
