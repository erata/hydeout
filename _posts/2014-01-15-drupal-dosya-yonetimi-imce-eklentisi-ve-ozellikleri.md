---
layout: post
published: true
excerpt_separator: <!--more-->
title: Drupal Dosya Yönetimi Imce Eklentisi ve Özellikleri
categories:
  - icerik-yonetim-sistemleri
tags:
  - drupal
redirect_from:
  - /2018/01/01/drupal-dosya-yonetimi-imce-eklentisi-ve-ozellikleri/    
---
IMCE eklentisi şuan drupalde en çok kullanılan dosya yönetim aracıdır. Elfinder gibi zorlu rakipleri olsa da IMCE‘nin, farklı platformlar ile rahat çalışılabilmesi ve farklı durumlara yönelik farklı ayarlamaların yapılabilmesi onu IMCE drupalin vazgeçilmezlerinden biri haline getirmiştir.

<!--more-->

imce

IMCE ‘nin Özellikleri ve Alt Eklentileri
Bu soruya cevap en iyi IMCE nin kendi sayfasında verilmiş. IMCE ile:

Dosya işlemleri: dosya yükleme, silme
Resim işlemleri: sıralama, yeniden boyutlandırma, önizleme, “thumbnail” resim oluşturabilma
Gizli dosya sistemini destekleme (private file system)
Farklı yetkilerde kullanıcı rolleri ekleme (*** verilen roller ile yüklenecek (upload) dosya büyüklük limiti, dosya türü, dosyanın kaydedileceği kılasör rahatlıkla ayarlanabilir)
Kılasörlere erişim izinleri
FTP tarzı menü sistemi
Dosya adına, türüne ve tarihine göre sıralama yapabime
Atanmış Kılavye kısayol tuşlarını kullanabilme
“textareas” dediğimiz “body” alanına resim ve dosya ekleyebilme
Çoklu resim seçebilme
Ajax dosya işlemleri
.tpl dosyaları ile temasının özelleştirilebilmesi
bueditor, ckeditor, tinymce (wysiwyg ve imce_wysiwyg eklentileriyle) gibi bilindik farklı editorler ile çalışabilme (***)
Toplam dosya sayısı ile kullanılan disk boyutunu öğrenebilme
rahatlıkla yapılabilir. Ayrıca IMCE ile çalışan eklentilerden:

imce_mkdir ile yeni kılasör oluşturabilme
imce_crop ile belirtilmiş boyutlarda yeni resim oluşturabilme
imce_tools ile dosya/kılasör erişimleri ile ilgili bazı durumları inceleyebilme
imce_watermark ile resimere arkaplan resmi (watermark) ekleyebilme
imce_rename ile dosya ve kılsör isimlerini değiştirebilme
imce_filefield ile drupalin temel dosya yükleme (default upload) kısmında daha önceden yüklenmiş resimleri kullanabilme. (***)
imce_plupload ile çoklu resim yükleyebilme (multi upload)
gibi ekstaradan özellikler de katmanız mümkündür. Gördüğünüz üzere bir dosya yönetim aracı olan IMCE ile çok farklı senaryoları rahatlıkla gerçekleştirebilme fırsatınız var.

