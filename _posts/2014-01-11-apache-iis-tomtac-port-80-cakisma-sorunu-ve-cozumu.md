---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Apache, IIS, Tomtac Port 80 Çakışma Sorunu ve Çözümü'
tags:
  - port-80-cakismasi
  - apache
  - iis
  - tomtac
redirect_from:
  - /2018/01/01/apache-iis-tomtac-port-80-cakisma-sorunu-ve-cozumu/ 
---
Merhaba arkadaşlar. Bugün sizlerle web uygulamaları geliştirme sürecinde sıklıkla karşılaştığımız sorunlardan birinden bahsedeceğim: port 80 çakışması.

Port 80 açkışması, 80 nolu port bir uygulama (sunucu) tarafından kullanırken bizim bu portu kullanacak başka bir uygulamayı (sunucu) çalıştırmak istediğimizde karşılaştığımız bir sorundur. Günümüzdeki sunucuların ekseri 80 portunu kullanacak şekilde ayarlanmıştır.Örneğin PHP ile web uygulamaları geliştiriken sıklıkla kullandığımız easyphp, wampserver, xampp gibi bütünleşik uygulamalar (Mysql, PHP, PhpMyAdmin ve Apache Server, vb. içeriyor) içerisindeki Apache ya da Tomtac Sunucuları 80 portunu kullanacak şekilde ayarlıdır. Aynı şekilde  windows tabanlı uygulamalar için kullandığımız IIS yine 80 portunu kullacanak şekilde gelmektedir.

<!--more-->

### Aynı Anda Farklı Sunucuları Bir Arada Çalıştırırsak Ne Olur?

80 portu üzerinde bir çakışma yaşanacağı için portu elde tutan sunucu çalışmaya devam ederken diğer talepte bulunan sunucu (lar) port 80 çakışması hatası vereceklerdir. Dolayısıyla aynı anda birden çok sunucu ile çalışmak durumunda iseniz sizlere üç temel yaklaşım öneriyoruz:

Sunucuların çalıştığı (hizmet verdiği) port numaraları birbirinden farklı yapmak
Sunucuları birçok farklı port dinleyecek şekilde ayarlamak
Aynı anda tek bir sunucunun çalışyor olması sağlamak, çalışmasını istediğimiz sunucu hariç diğerlerini kapamak

### 1. Sunucuların çalıştığı port numaraları birbirinden farklı yapmak

Diğer seçenekler göz önüne alındığında en mantıklısının bu olduğunu söyleyebilirim. Aynı anda Apache ya da Tomtac içeren Uygulamalar ile (easyphp, wampserver, xampp) IIS  kullanımı port çakışmasına neden olacağından gerek Apache, Tomtac Sunucuları için gerekse de IIS için farklı port numaraları tanımlamak çakışmayı önleyecektir. Örneğin aşağıdaki XAMPP kontrol Paneli mesajında 80 nolu portun dolu olduğunu, sorunu çözmek için ya 80 portunu işgal eden uygulamayı kapatmak gerektiğini ya da 80 nolu port dışında farklı bir port kullanmak gerektiğini ifade ediyor. Uygulamamızın çalışması için faklı bir port nasıl dinleniri xampp ve IIS üzerinde örnekleyelim.

XAMPP Üzerindeki Apache Sunucusunun Hizmet Verdiği (Dinlediği) Portu Değiştirme (Örneğin 81 olarak)
XAMPP üzerinde Port Çakışması Mesajı

XAMPP’de port değiştirmek için C:\xampp\apache\conf\httpd.conf yolunu izleyerek httpd.conf dosyasındaki listen 80 yazan yeri bulmalı ve 80 sayısını faklı bir sayı ile (örneğin 81) değiştirmeliyiz. Örnek bir resim aşağıda verilmiştir.
 
![XAMPP üzerinde Apache Portunu Değiştirme](http://2.bp.blogspot.com/-awBVExnnN8c/UR00ekCaqkI/AAAAAAAAALU/nstSwagIlvw/s1600/port.JPG)

XAMPP üzerindeki Apache Server’in portunu nasıl değiştirebileceğimiz ve sonraki durumda uygulamamıza nasıl ulaşabileceğimiz aşağıdaki vidyoda gayet basit ve güzel bir şekilde anlatılmış.

IIS (İnternet İnformation  Services) Portunu Değiştirme (Örneğin 82 olarak)
IIS’de port değiştirmek için ilk önce Başlat»Çalıştır»inetmgr  yoluyla IIS Yöneticisini çalıştırmalıyız. Daha sonra Siteler altındaki Default Web Siteye sağ tıklıyoruz ve Bağlamaları Düzenleyi seçiyoruz. Örnek Resim aşağıda.

![IIS Port Değiştirme - 1 ](http://1.bp.blogspot.com/-sV7OZO4dvQE/UR02keQTdAI/AAAAAAAAALc/FfOlKoNAyLQ/s1600/iis+1.+a%C5%9Fama.JPG)

Gelen ekranda http ile başlayan satırı seçtikten sonra sağ taraftaki Düzenleyi seçiyoruz. Gelen ekranda ise Bağ Nok ile ifade edilen yerdeki 80 sayısını 82 ile değiştiryoruz, Tamam diyerek çıkıyoruz. Örnek resim aşağıda.

![IIS Port Değiştirme - 2](http://3.bp.blogspot.com/-1-jfI4GoVQA/UR06DkiHEUI/AAAAAAAAALk/ZkghEYCY9oI/s1600/iis+2.+a%C5%9Fama.JPG)

### 2. Sunucuları birçok farklı port dinleyecek şekilde ayarlamak 

80 nolu port çakışmasın önlemenin diğer yolu, 80 nolu porttan başka portlar dinleyecek şekilde sunucuyu yapılandırmaktır. Apache, Tomtac ve IIS temel ayarlarında (default) 80 portunu kullandığından çakışma ihtimaline karşı Listen 80 ile hizmet verilen (ya da dinlenilen) porttan başka portlar da eklemeliyiz sunucunun hizmet verdiği. Baştan belirtelim ki Sunucuların dinlediği portu ya da ip adresini yapılandırmak bizim elimizde. Bunu XAMPP üzerndeki Apache Server üzerinde örnekleyecek olursak C:\xampp\apache\conf\httpd.conf yolunu izleyerek httpd.conf dosyası içerisinde rahatlıkla yapabiliriz. Örneğin ekstradan 8000 nolu portu dinleyeceksek Listen 8000 şeklinde ek bir satır eklemeliyiz sunucu port ayarında. Benzer bir şekilde IP adresi dinlemek için yine Listen IP Adresi şekilde ek satır eklemeliyiz. Apache Sunucusu üzerindeki port ve ip adresleri dinleme noktasında apache.org/docs/2.2/tr/bind.html, apache.org/docs/2.2/tr/mod/mpm_common.html#listen ve configure-apache-web-site-to-use-multiple-ports yazılarından daha fazla bilgi alabilirsiniz. Sonuç olarak ekstradan port ve ip adresi dinlerken:

**Port Adresi Dinleme Ayarı için**

Listen 80
Listen 8000

**IP Adresi Dinleme Ayarı için** 

Listen 192.0.2.1:80
Listen 192.0.2.5:8000

şeklinde ayarlamalar yapabiliriz ilgili sunucu ayarında. Aşağıdaki resimden inceleyebilirsiniz Port ve IP adresi dinleme örneklerini.

![Birçok Farklı Portu Dinlemek](http://3.bp.blogspot.com/-SJCawTBpVnQ/UR1ABHc0ZHI/AAAAAAAAALs/fO0XIU0pYkU/s1600/listen.JPG) 

### 3. Aynı anda tek bir sunucunun çalışyor olması sağlamak

80 nolu port çakışmasın önlemenin bir diğer yolu, 80 portunu işgal eden uygulamayı kapamaktır. Örneğin Web Deployment Agent adlı iş parçacı 80 nolu port üzerinde çalışmakta, Apache ya da Tomtac Sunucusuna geçit vermemekte, port meşgul hatası verdirmektedir. Dolayısıyla port sorununu çözmenin bir diğer yolu olarak da o an için o portu kullanan uygulamayı sonlandırmaktır.

Hangi uygulamanın port 80’i kapattığını ise aşağıdaki resimdeki gibi XAMPP programındaki Netstat hizmeti yardımıyla ulaşabiliriz. Örnek resimde 80 portunun PID=4 olan bir Sistem uygulaması tarafından kapatıldığı görülmektedir. Eğer Apache server’iniz port 80’e ayarlı ise port 80 dolu olduğundan Apache server resimdeki gibi çalışmayacaktır.


Resim: Port 80’nin başka bir uygulama ile kapalı olup olmadığını Netstat ile bulma

Eğer port 80 başka bir uygulama tarafından kapatılmamış olsaydı örnek resim aşağıdaki gibi olurdu:


Resim: Port 80 boş iken Apache server çalışacaktır. Netstat ile bunu görebiliyoruz.

Yukarıda XAMPP’de hangi portun kimler tarafınafından kullanıldığı gördük. Bir de bunun komut satırı vasıtasıyla yapılması var. Bu konuya şimdilik girmeyerek hangi portu kimin kullandığı, PID’i ne olduğunu ve ilgili uygulayı uygulama yöneticisinden (task manager) bulup nasıl sonlandıracağımızı ilgili yazılara (port-80-in-use, pid4-using-port-80, find-pid-of-process-that-use-a-port-on-windows) bırakıyorum.

Şimdi ise port 80 kapayan örnek bir uygulama Web Deployment Ağent iş parçacığı üzerinde ilgili portu açmak için bu iş parçacığını nasıl sonlandıracağımıza bakalım:

Windows Görev Yöneticisinden -> İşlemler ve buradan ilgili iş parçacığını bulup sonladırıyoruz. Windows Görev Yöneticine ise CTRL+ALT+DELETE’den ulaşabilirsiniz. 80 portunu meşgul eden örnek iş parçacığı ağağıdaki resimde verilmiştir.

80 Portunu Kullanan Diğer Uygulamaları Kapatmak

Port çakışmasıyla ilgili hazırlanmış örnek bir vidyo, XAMPP üzerindeki apache serverın çalışmama sorunu ele alınıyor. Sunucunun çalışmasını engelleyen program bulunarak kapatılıyor ve çalışması sağlanıyor. Bu şekilde port 80’i işgal eden uygulamalara SQL Server Reporting Services (MSSQLSERVER), **Web Deployment Agent Service**  (MsDepSvc) ya da **World Wide Web Publishing Service** verilebilir (Bkz.).  

![Web Deployment Agent Service](http://2.bp.blogspot.com/-9oHuzJAMHlM/Un_g8kK-90I/AAAAAAAAAUA/xHVLpHP6a3o/s640/web+development+agent.PNG)

Dinlenilen Portu Değiştirdikten Sonra Uygulamayı Nasıl Çalıştıracağız – Yeni Uygulama URL’si Ne Olacak?
Portla ilgili ilk iki işlemde temel portu değiştirmeyi ve dinlenecek yeni portlar eklemeyi anlattık. Fakat bu işlemler sizin uygulamanızın çalıştığı URL adresini de değiştirecektir. Dolayısıyla çalıştığınız portu belirtir bir şekilde uygulamanıza ulaşabilirsiniz yeni durumda. Örneğin localhostta çalışıyorsanız:

![80 portu kapalı olduğu için apache sever çalışmıyor](/http://2.bp.blogspot.com/-kwapSlgh_1Q/Un_o19COhkI/AAAAAAAAAUQ/Wo4_wuiSmdY/s640/apache+server.PNG)

Önceden 80 nolu kullanırken localhost/drupal  şeklinde eriştiğiniz uygulamanıza portu 81 olarak değiştirirseniz artık localhost:81/drupal şeklinde erişmeye başlayacaksınız. Kısacası önceden yazdığınız uygulama adresindeki localhost ifadesinin önüne ekstradan kullanacağınız yeni portun adresini :port_no şeklinde yazarak localhost:port_no/uygulama ifadeisndeki gibi bir yapı elde edeceksiniz.

Benzer bir şekilde eğer biz sunucunun 80 portunun yanında 8000 portunu da dinlemesini istemişsek ve 80 portu meşgul diyorsa 80 portu ile localhost/drupal/7.24 şeklinde ulaşacağımız bir uygulamaya 8000 portu ile localhost:8000/drupal/7.24 ile ulaşarak uygulamamızı yine çalıştırabiliriz.

### Kaynak:
- http://stackoverflow.com/questions/15952663/find-pid-of-process-that-use-a-port-on-windows
- https://sites.google.com/site/anashkb/port-80-in-use
- http://superuser.com/questions/352017/pid4-using-port-80https://openguider.wordpress.com/2014/01/31/how-to-solve-port-80-problems-on-windows

