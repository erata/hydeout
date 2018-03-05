---
layout: post
published: true
excerpt_separator: <!--more-->
title: Zebkit ile Canvas Uzerine HTML5 Cizimler Yapma
categories:
  - javascript
tags:
  - zebkit
---
## A New Post

<div class='pull-left style="border: 1px solid black; padding: 15px;">
![zebkit]({{site.baseurl}}/assets/media/zebkit.PNG)
</div>

Designer modunda HTML5 öğleri istediğiniz konuma yerleştirme şansına sahipsiniz. Ayrıca tek sayfa ve mobil uygulama yapmaya destek vermektedir.

.left[![zebkit]({{site.baseurl}}/assets/media/zebkit.PNG)]

Merhaba arkadaşlar. Bu yazımda [zebkit](http://www.zebkit.org) javascript kütüphanesini tanıtacağım. Zebkit, Canvas üzerine HTML5 öğeler çizmenizi sağlayan MVC bir javascript kütüphanesidir. Adı çok duyulmamış olmasına rağmen HTML5 öğeler çiziminde oldukça güçlü ve maharetlidir. Designer modunda HTML5 öğleri istediğiniz konuma yerleştirme şansına sahipsiniz. Ayrıca tek sayfa ve mobil uygulama yapmaya destek vermektedir.



 

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
<!--more-->

Zebkit bir [Fabric.js](http://fabricjs.com/) kadar bilinir değildir. Fakat konu HTML5 şekilleri çizimi noktasına geldiğinde birçok anlamda ihtiyacınızı Fabric.js'den daha fazla karşılayacaktır. Belki   
