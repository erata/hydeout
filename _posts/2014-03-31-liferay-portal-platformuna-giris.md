---
layout: post
published: true
excerpt_separator: <!--more-->
title: Liferay Portal Platformuna Giriş
categories:
  - icerik-yonetim-sistemleri
tags:
  - liferay
---
Merhaba arkadaşlar. Bu yazıda j2ee ile geliştirilmiş açık kaynak web portal platformu olan Liferay‘i konu alacağız.

Liferay, bir portal platformudur ve Ücretsiz (Community Edition) ve Ücretli (Enterprise Edition) olmak üzere iki şekilde sunulmaktadır . Liferay’i anlamak portalın ve portletin ne olduğunu anlamakla başlar.

<!--more-->

Not: Portal’a, e-kapı; portlet’e ise e-odacık diyen var bknz)

Portal Nedir?
Portal, farklı birçok içeriği bir arada bulunduran internet siteleri için kullanılır. İçerik ya da bilgi sağlama amacıyla oluşturulan portallar sayesinde farklı kapsamdaki içerikler tek bir merkezde buluşturularak daha etkileşimli ve performanslı bir hizmet ortaya imkanı ortaya çıkar. Portaller ile birlikte son kullanıcı, farklı adresleri dolaşarak elde edebileceği bir hizmeti tek bir yerden çok kısa bir süre içinde ve daha etkin bir şekilde edebilir (Kapsamlı bilgi için bknz).

Portallar farklı yaklaşımlarla (konu, amaç, sektör, hedef, kapsam, vb.) değişik kategorilere ayrılabilir. Portal kavramı ilk kez 1996’da MyYahoo ile kişiselleştirilmiş portal hizmetleri şeklinde gündeme gelmiştir. Portaller sağlık, eğitim, müzik turizm, kültür/sanat, eğlence, yatırım/finans, haber, vb. konularda olabilir (Kapsamlı bilgi için bknz).

Portal ve Portlet
Kaynak: http://vforliferay.blogspot.com.tr/2010/11/liferay-overview.html

Porlet Nedir?
Portallardan bahsedipte portletlerden bahsetmek olmaz. Portlet, portalları oluşturan yapılardır. Yani portallar birçok portletin bir araya gelmesye oluşur. Portletleri ayrı içerik sağlayan birer web uygulaması olarak düşünebilirsiniz, örneğin mail, alış-veriş, haber, depo, vb. portleti gibi.

Portletler, deploy edilebilen java standardı uygulamalardır. Bir modül gibi ya da bir widget gibi  tak-çalıştır uygulamalar olarak düşünebilirsiniz. Portletler, kendine ait pencerelerde bağımsız bir şekilde çalışabilirler. Dolayısıyla portlertlerin kendine ait request ve response’leri vardır (Kapsamlı için Liferay Sunumu).

Gerek portallar gerekse de portletler hakkında daha detaylı bilgi için liferay-overview yazısını okumanızı şiddetle tavsiye ederim.
Portal sitelere örnek olarak liferay.com,  turkiye.gov.tr, vaadin.com, Kocaeli BŞ Belediyesi sitelerini örnek verebiliriz. Hepsinde de ortak yön farklı veri kaynaklarını bir çatı altında toplayabilmek ve sunabilmek. Örneğin turkiye.gov.tr  portal sitesinde farklı devlet kurumlarına yönelik onlarca hizmet sunulmaktadır. Tabi verilen her bir hizmetin bir portlet olduğunu varsayabilirsiniz. Örneğin şuan itibarıyla Ulaştırma, Denizcilik ve Haberleşme Bakanlığına ait  140 entegre hizmet, Gümrük ve Haberleşme Bakanlığına ait 9 entegre hizmet sunulmaktadır. Tabi entegre hizmetten kasıt tak-çalıştır mantığınca hazırlanmış portlet uygulamalardır.

[video:http://www.youtube.com/watch?v=48X0-RJ5kBU]
Liferay Kurulumu
Liferay kurulumu için öncelikle indirme sayfasından size uygun olan versiyonu seçmelisiniz. Bu sayfada ücretli ve ücretsiz sürümler sunulmaktadır. Siz ücretsiz olanlardan birini seçip indirmelisiniz. Seçim yaparken hngi sunucu ile liferayin çalışmasını istiyorsanız o sunucu ile bütünleşik liferay paketini seçiniz. Örneğin ben sunucu olarak Tomtac’ı seçiyorum “Bundled with Tomtac” olanı yani.  Sırası ile Liferay kurulumunu ve nasıl çalıştıracağınız anlatacak olursak (Tomtac örneğine göre)

Liferay’i indirin – şuan liferay-portal-tomcat-6.2-ce-ga2-20140319114139101.zip sürümü var mesela.
İndirdiğiniz .zip uzantılı dosyayı açın.
liferay-portal-6.2-ce-ga2\tomcat-7.0.42\bin  içindeki startup.exe dosyasına çift tıklayıp bekleyin
“server start up” mesajını alınca artık http://localhost:8080 adresinden localhosttaki siteyi ziyaret edebilir, önceden atanmış farklı kullanıcı rolleriyle değişik kullanım şekillerini deneyebilirsiniz.
Biz her ne kadar burada indirilen liferay sürümünün basit olarak nasıl çalıştırılacağına değindik. Fakat sizin denemek istediğiniz sunucu Tomtac olmayabilir veya siz Eclipse ile kullanabileceğiniz bir kurma şekli isteyebilirsiniz. Onun için liferayin size sunduğu oldukça detaylı dökümanlardan yararlanabilirsiniz. Örneğin farklı kurulum örnekleri için:

installing-liferay (Farklı birçok kurulum örneği var)
liferay-6.2-portal-installation (Resimli anlatım)
liferay-portal/6.0/development/-/ai/installation (Eclipse)
Liferay Weblogic Kurulumu
sayfalarını ziyaret edebilirsiniz. Dilerseniz kaynaklarda verdiğimiz referanslardan da yararlanma yoluna gidebilirsiniz.

### Kaynaklar
http://portal.nedir.com
www.martisoft.com/download/ceturk_liferay.pps‎
http://vforliferay.blogspot.com.tr/2010/11/liferay-overview.html
http://www.iucoders.com/article_detail.jsp?nid=61
http://www.liferay.com/documentation/liferay-portal/6.2/user-guide
http://belgeler.cs.hacettepe.edu.tr/yayinlar/eski/LiferayJ2EEPortal_20122072_SonRapor.pdf
https://www.liferay.com/community/forums/-/message_boards/category/3159556 (Liferay Türkçe forum sayfası )
http://www.liferay.com/documentation/liferay-portal/6.1/user-guide/-/ai/installing-liferay
http://liferayguru.blogspot.com.tr
https://www.liferay.com/documentation/liferay-portal/6.0/development/-/ai/installation
http://www.liferaysavvy.com/2013/12/liferay-62-portal-installation_11.html
http://howwhywhat.in/liferay-6-1-installation-steps-on-jboss
http://abdulcebar-on.blogspot.com.tr/2013/08/liferay-weblogic-kurulumu.html
