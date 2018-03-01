---
layout: post
published: true
excerpt_separator: <!--more-->
title: Drupalden Jekyll'ye Geçiş
tags:
  - drupal
  - jekyll
  - statik-site
categories:
  - icerik-yonetim-sistemleri
---
Merhaba arkadaşlar. Uzun süre drupal ile haşır neşir olmuş biri olarak artık ben de [Jekyll](https://jekyllrb.com/) ile yazı yazanlardan biriyim. Drupal benim ilk olmasa da sevdiğim göz ağrılarımdan biriydi:) Ne varki drupal ile site geliştirmek ve daha da iyisini geliştirme çabaları esas amacın yani yazı yazmanın önüne geçti. En son edindiğim tecrübeler ile artık [Github Pages](https://pages.github.com/) üzerinde Jekyll statik site üretici kullanarak sitemi geliştirme konusunda karar kıldım ve iyi de yaptığımı düşünüyorum:) 

<!--more-->

![Jekyll image]({{site.baseurl}}/https://jekyllrb.com/img/logo-2x.png)

İlk site geliştirmeye düz HTML+CSS bilgimle başlamıştım. Zaman geçti Wordpress ile tanıştım ve hayran kaldım localde site geliştirdim. Sonra dedim başkası da vardır, Joomlaya geçtim. Yalnız Joomlaya bir türlü ısınamamıştım. Sonra Drupal'e atladım. At değiştirir gibi içerik yönetim sistemi değiştiriyordum:) Nasıl olduysa Drupal'e hayran kaldım ki önceki yazılarımın büyük bir çoğunluğu da Drupal üzerinedir. Drupal hakikaten çok sağlam bir içerik yönetim sistemi, ama ne yalan söyliyem bu ayarlarıyla uğraşmak bir noktadan sonra kabak tadı vermeye başladı. Belki kullandığım tema açığından, belki bir eklentiden, belki yanlış bir ayardan ya da siteyi  host ettiğim yerden olsa gerek site iki de bir göçüyordu. Virüs bi kere bulaşmaya görsün siteye nefes aldırmadı gitti:) Ben de yakın zamanlarda Github Pages'i araştırmaya başladım. Jekyll'yi duymuştum ama Drupal, Wordpress varken Jekyll de neymiş:) tarzı bir tavır içindeydim. Her neyse insan bilmediğinin düşmanıdır derler ya Jekyll yi öğrendikçe hyranlığım arttı ve zaten Drupal'den dili yanmış biri olarak (ki halen Drupal'i severim) Github Pages'e siteyi taşımaya karar verdim.

### Peki neden böyle bir karar verdim şimdi buna değinelim

1 - Github Pages'i host olarak kullanıp site yayınlamak ücretsiz ki en büyük artılarından biri bu
2 - Artık sitem çökecek, göçecek diye kafa yormanıza gerek kalmayacak, şifrenizi sağlam koyun yeter:)
3 - Github domain adresi ile (username.github.io mesela) ile ya da kendi özel domain adınızla (webritmi.com) siteyi yayınlamanıza imkan veriyor.
4 - Jekyll ve Jekyll muadili birçok statik site oluşturucu var ve bunlarla çok rahat bir şekilde sitenizi oluşturabilirsiniz. 
5 - Jekyll ya da diğer [statik site üretici araçlarla](https://www.staticgen.com/) (ya da içerik yönetim sistemi diyelim) site yapma sürecini anlamak yani öğrenme süresi daha kısa. Eğer Github commit'leme mantığına biraz aşina iseniz işin yarısı hallolmuş demektir. Drupal, Wordpress gibi dinamik içerik site yönetimleri ile yaptığınız siteler için veritabanı oluşturmanız, veritanı ve diğer dosyaları koyacağınız bir host bulmanız ve bulacağını host'un sizin ihtiyaçlarınıza ne ölçüde cevap vereceğine dair bir takım bilgiye hakim olmanız gerektiğini hatırlatalım. 
6 - Github Pages üzerine konumlandırdığını site sizi içeriğe odaklayacak, dinamik sitedeki gibi iki de bir eklenti güncelleme, spamlarla uğraşmak için ek önlem alma, vb. değişik dertlerden br anda soyutlanacaksınız.
7 - Jekyll ile kendi modülünüzü (eklenti) geliştirmek, bir dinamik sitedekine göre çok daha kolay. Bir tane '*.rb' dosyası oluşturarak istediğiniz davranış kodlarını yazıyorsunuz sonra _plugins klasörüne attınız mı olay bitiyor. 
8 - [Prose.io](http://prose.io/) gibi yazı editörü var ve yazı şekillendirme, resim ekleme gibi temel ihtiyacınızı rahatlıkla karşılyor. [Prose.io'nun ayarlarını](https://github.com/prose/prose/wiki/Prose-Configuration) _config.yaml dosyasında düzgün bir şekilde yapılandırısanız yazı yazma işiniz çok kolaylaşacaktır.
9- Github Pages üzerinde 3. parti script kütüphanaelerini ve kendi scriptlerinizi çalıştırabiliyorsunuz. Dolayısıyla Github Pages'te değişik bir takım ihtiyaçlarınızı (örneğin yorum için [Disqus](https://disqus.com/)) 3. parti scriptler ile rahatlıkla yapabiliyorsunuz. Hatta Github Pages üzerinde SPA (Single Page Application )denilen tek sayfa uygulaması geliştirmeniz mümkün. Örneğin [Firebase](https://firebase.google.com/) üzerinde [apinizi](https://firebase.google.com/docs/reference/) ve [veritabanınızı](https://firebase.google.com/docs/database/) tanımlayıp back-end ihtiyacınızı giderebilirsiniz. Diğer taraftan front-end ihtiyacınz için alternatif anaçatılardan (frameworkler) birini kullanabilirsiniz ( [Angular](https://angular.io/), [React](https://reactjs.org/) ya da [Vue.js](https://vuejs.org/)). Yani front-end kodlarınız Github Pages üzerinde konumlanacak. Her ne kadar Github Pages üzerinde statik site konumlanıyor olmasına karşın birçok 3. parti scritpleri çalıştırabiliyor olmanız ile birçok farklı amaçlı uygulama geliştirme, çalıştırma şansınız mümkün.
9 - Birçok büyük uygulama dökümanını Github Pages üzerinde konumlandırıyor örneğin [Bootstrap](https://github.com/twbs/bootstrap), [Angular](https://github.com/angular/angular), [Vue.Js](https://github.com/vuejs/vue), vb. Uygulama dökümanınız için Github Pages biçilmiş kaftan. Uygulama dökümanını güzel bir şekilde sunabileceğiniz birçok tema sizi bekliyor.

Umarım sizin için de yararlı olmuştur. Sakın ola Drupal'i kötülediğimi düşünmeyin. İhtiyaç analizi yaptığımda Github Pages üzerinde site yayınlamak daha mantıklı geldi o kadar:)