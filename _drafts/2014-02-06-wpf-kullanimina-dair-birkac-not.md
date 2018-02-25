---
layout: post
published: true
excerpt_separator: <!--more-->
title: WPF Kullanımına Dair Birkaç Not
categories:
  - yazilim-gelistime
tags:
  - WPF
---
Merhaba arkadaşlar. Bu yazıyı, WPF kullanırken takılabileceğimiz bazı noktalarda yardımcı olabiliceği düşüncesiyle ele alıyorum.

<!--more-->

WPF (Windows Presentation Framework), yeni nesil kullanıcı arayüzü geliştirme ve görüntüleme platformudur. Windows Form gibi bir işlevi olmakla birlikte Windows Form’a göre birçok açıdan esnek kullanım sağlar. Özellikle grafik çizimlerinde çok başarılıdır. WPF’i daha iyi anlamak ve Windows Form ile ne gibi farklılıklarının olduğunu öğrenmek için 1, 2, 3, 4, 5, 6 ve 7 nolu yazıları okuyabilirsiniz)

WPF, Windows Form’a göre gerek kullandığı dil (XAML) ve gerek diğer özellikleriyle bayağı farklılıklar arzediyor. Dolayısıyla bu, Windows Form’a göre kullanım alışkanlıklarımızı biraz değiştirmemizi gerektiriyor. Biz burada WPF ile ilgili genel bilgilerden bahsetmeyeceğiz, daha çok detay kısımlarda takılabileceğimiz noktalardan bahsedeceğiz.  Lafı uzatmadan WPF ile ilgili notlarımızı (zamanla yenilerini de eklemeyi düşünüyorum) sizinle paylaşalım.

Name – x:Name Özellikleri Arasındaki Fark
Bu konu hakkında stackoverflow.com‘da birçok soru sorulmuş ve cevap verilmiş (1, 2, 3, 4, vb), yani bayağı merak edilen bir konu. Name özelliğini zaten biliyoruz ki nesneleri (kontrolleri) işaret etmeye yarıyor. x:Name de Name gibi nesneleri işaret etmeye yarıyor.  Peki neden X:Name özelliği var diyesi geliyor insanın. Sebep ise Name özelliğinin tüm kontrolleri işaret edemediği durumların olması. İşte bu açığı kapama amacıyla ayrıca x:Name özelliği konulmuş. Örneğin kullanıcı kontrolleri, vb durumlarda Name özelliği olmayan kontrolleri işaret edebilmek için x:Name özelliği büyük bir boşluğu doldurmuş oluyor. Name ile x:Name bir kontrolün içinde aynı anda kullanamıyor çünkü aynı işi görüyor ama x:Name daha geniş kapsamda iş görüyor. Kısacası yaptıkları işler aynı fakat x:Name, Name’in işaret edemediği kontrollere de işaret ediyor ve böylece onları Name özelliği ile yapabildiklerimizden mahrum etmemiş oluyoruz. Bu yazıya göre sınıf tanımlamada Name ve x:Name arasında bir fark yoktur fakat nesne tanımlama vardır ve nesne tanımlanacağı zaman, nesne Name ile niteliği ise x:Name ile tanımlanmalıdır.

x:Name – x:Key Özellikleri Arasındaki Fark
Bu iki kavram da bayağı merak edilenler arasında (1, 2). x:Name, daha önce de değindiğimiz gibi Name özelliği ile aynı işlevi gören bir özellikte (bazı farklılıklarıyla) ve hem ön tarafta (XAML) ve hem de kod tarafında (.xaml.cs /.xaml.vb) etkin fakat x:Key sadece ön tarafta aktif. x:Key sitil ve tema tanımlamada <Style></Style> kullanılıyor. Daha fazla bilgi için bu yazıyı ve şu yazıyı okuyunuz.
