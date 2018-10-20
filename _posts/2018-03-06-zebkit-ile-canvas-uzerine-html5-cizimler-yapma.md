---
layout: post
published: true
excerpt_separator: <!--more-->
title: Zebkit ile Canvas Uzerine HTML5 Çizimler Yapma
categories:
  - javascript
tags:
  - zebkit
---
Merhaba arkadaşlar. Bu yazımda [zebkit](http://www.zebkit.org) javascript kütüphanesini tanıtacağım. 

Zebkit, canvas üzerine HTML5 öğeleri çizmenizi sağlayan MVC tabanlı bir javascript kütüphanesidir. Adı çok duyulmamış olmasına karşın HTML5 elemanlarının çizimi ve sunumunda oldukça güçlü ve maharetlidir. HTML5 elemanlarını çizimini yapmanın yanı sıra designer moduyla bu elemanların canvas üzerinde sürükle bırak ile yeniden konumlandırabiliyorsunuz. Tek sayfa uygulamalara ve mobil uygulamalara da destek veren Zebkit hiyerarşik kullanımı ile nesneye yönelik yazılımın tadını almanızı sağlıyor.  

```js
 zebkit.require("ui", "layout", function(ui, layout) {
        ...
        // create panel with border layout manager
        var panel = new ui.Panel(new layout.BorderLayout());
        // add button component at the top part of the container
        panel.add("top", new ui.Button("Button"));
        // add text area component to occupy central part of the 
        // container
        panel.add("center", new ui.TextArea("Text area"));
        ...
    });
```

![zebkit-component]({{site.baseurl}}/assets/media/zebkit-component.PNG)

Zebkit bir [Fabric.js](http://fabricjs.com/) kadar bilinir değildir. Fakat konu HTML5 şekilleri çizimi noktasına geldiğinde birçok anlamda ihtiyacınızı Fabric.js'den daha fazla karşılayacaktır. Oldukça gelişmiş dokümantasyona sahip olan Zebkit dokümantasyonu da oldukça gelişmiştir. Siyah ve beyaz teması ve özelleştirmeye açık yapısı Zebkit'in tercih edilebilirliğini artırmaktadır.

![zebkit dokümantasyon](http://www.zebkit.org/light/public/images/api-light.png?400x400)

Eğer canvas kullanrak bir proje geliştirecekseniz ve HTML5 elemanlarının oldukça sık kullanıldığı, icabında designer ekranında bu HTML5 öğelerini konumlandırabileceğiniz bir yapı geliştirmek istiyorsanız Zebkit sizin için çok uygun bir seçim olabilir. 

Zebkit büyük bir proje olmasına karşın geliştirici/destek veren kitle biraz sınırlı kalmış gibi gözükmekte (şuan [Andrei Vishneuski](https://github.com/barmalei/zebkit) öncülüğünde proje ilerliyor) fakat kütüphaneyi kullanırken karşılaştığınız sorunlarınızı açtığınız hata raporları ile bildirmeniz durumunda kısa sürede cevap almaktasınız. 

Umarım yararlı olmuştur.
