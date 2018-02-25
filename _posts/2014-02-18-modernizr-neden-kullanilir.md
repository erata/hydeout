## Modernizr Neden Kullanılır?

Modernizr günümüzün sık kullanılan javascript frameworklerinden biri, Wappalyzer’e göre ise jQuery’den sonra en fazla kullanılanı. Ne işlev yaptığı ise kendi sayfasındaki açıklama ile “Modernizr is a JavaScript library that detects HTML5 and CSS3 features in the user’s browser”  yani kullanıcıların kullandıkları tarayıcıların CSS3 ve HTML5’in hangi özelliklerini desteklediğini tespit eden bir javascript kütüphanesidir.

Modernizr’in tarayıcılardaki CSS3 ve HTML5 özelliklerini tespit etmesi, desteklenmeyen özelliklere yönelik program geliştirmede çok önemlidir. İşte Modernizr tam bu noktada devreye girerek desteklenen özellikler için bunu uygula, desteklenmeyen özellikler için şunu diyerek koşullu bir yaklaşımlara imkan verir ve tarayıcılardan kaynaklanan durumlar için en iyi çözüm yolu ortaya koyabilmenize müsaade eder.

Modernizr’in koşulları ele alış biçimi oldukça basit ve anlaşılırdır. Desteklenen özellikler direk kendi adlarıyla, desteklenmeyen özellikler ise önlerinde “no-” etiketleriyle kendini belli eder. Dolayısıyla biz özelliklerin tarayıcılar tarafından desteklenmesi ve desteklenmemesi durumlarını işte bu etiketler yardımıyla ele alarak tüm tarayıcılar için en iyi sonuç elde edebilme şansına sahip oluruz. Örneğin CSS’imizde x sınıfını destekleyip destekleme durumunu .x{…} ve .no-x{} şeklinde ele alarak olası durumlara yönelik tatminkar çözümler elde etmiş oluruz.

Örneğin bu yazıda İE 7’nin column-count ve box-shadow özelliklerini desteklememesi sorununda ortaya çıkan garip görüntüden ve bunu gidermenin yolundan bahsetmiş. Çözüm ise desteklenmeyen durumları ele almak ve eczanedeki ilaç mantığınca yapılan işin eşleğini yapmaya çalışmak:

```
.no-boxshadow img { /* styles for browsers that don't support box-shadow */ }
.no-csscolumns img { /* styles for browsers that don't support columns count */ }
```
```
.no-boxshadow img {
   border-right: #8A8A8A 2px solid;
   border-bottom: #8A8A8A 2px solid;   
}
```
```
.no-csscolumns img {
   margin: 3px 8px 3px 0;
   float: left;
}
```
Özetle Modernizr, tarayıcıların desteklediği HTML5 ve CSS3 özellikleri hakkında size bilgi sunarak desteklenen ya da desteklenmeyen durumlara göre koşullu ifadeler yazabilmenize ve tüm tarayıcılar için çalışabilen bir sonuç elde edebilmenize imkan tanır.

Umarım yararlı olmuştur.

### Tavsiye Kaynaklar:
- [http://modernizr.com](http://modernizr.com)
- [http://en.wikipedia.org/wiki/Modernizr](http://en.wikipedia.org/wiki/Modernizr)
- http://www.adobe.com/devnet/dreamweaver/articles/using-modernizr.html
- [http://www.stucox.com/blog/using-webp-with-modernizr](http://www.stucox.com/blog/using-webp-with-modernizr)
- http://alistapart.com/article/taking-advantage-of-html5-and-css3-with-modernizr
- http://html5doctor.com/using-modernizr-to-detect-html5-features-and-provide-fallbacks
- http://f5dergi.com/Makale/Modernizr-nedir-Nasil-kullanilir/17 (Türkçe)
- http://www.jurnal.im/s/591/modernizr-nedir-ne-i%C5%9Fe-yarar (Türkçe)
