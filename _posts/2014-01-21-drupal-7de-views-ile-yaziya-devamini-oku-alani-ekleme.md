## A New Post

Drupal 7’de Views ile Yazıya “Devamını Oku” Alanı Ekleme
BY ERATA	26 OCAK 2018  LEAVE A COMMENT
Merhaba arkadaşlar. Bugün sizlerle drupalde views kullanarak bir yazıya nasıl “devamını oku” alanı ekleriz onu göreceğiz. Hemen konuya girersek, views ile yazıya “devamını oku” eklemenin temel olarak iki yolu olduğunu baştan söyleyelim. Ve her iki yolda da bir alan ekleme (ya Content:Link ya da Content:Nid) ile bu işi yapıyoruz.

Content:Link ve Content:Nid Alanları ile”Devamını Oku” Yapmanın Farkı Ne?
Content:Link alanını kullanırsanız “devamını oku”, ihtiyaç olup olmadığına bakılmaksızın her halukarda  yazının sonunda görünür. Fakat Content:Nid alanını kullanırsanız “devamını oku”, sadece ihtiyaç duyulduğu zaman yazıya eklenir ve görünür.

İster Content:Link İsterse de Content:Nid Alanı Kullanın
1- Eklediğiniz alan (Conten:Link ya da Content:Nid), yazı alanının yukarısında olacak. Bunu sağlayabilmek için yeniden düzenle’yi (rearrange – field menüsünde yer alıyor)  kullanabilirsiniz. Yeni durumda
ya
Content:Link
Content:Body  
ya da
Content:Nid
Content:Bod
şeklinde bir durum olacak.

2- Eklediğiniz alanda (Conten:Link ya da Content:Nid) girilmesi gereken yazı kısmını girdikten sonra (Content:Nid de herhangi bir yazı girme yok) Exclude from display seçeneği seçerek bu alanın bir altta yer alan Content:Body alanının REWRİTE RESULT kısmında kullanılmasını sağlıyoruz.

3- Geriye, Content:Body ayarlarını yapmak kalıyor. Eğer Content:Nid alanını tercih etmişseniz aşağıdaki resimdeki gibi REWRİTE RESULT menüsünde Trim this field to a maximum length seçeneğini seçtikten Add a read-more link if output is trimmed seçeneğini seçiyoruz, sonra More link text kısmına [DEVAMINI OKU] ve More link path kısmına isenode/[nid] yazıyoruz.

Ayrıca harf olarak yazının en fazla kaç harten oluşacağını (Maximum length), yazının tam kelime ile bitip bitmeyeceğini (Trim only on a word boundary) ve yazı sonunun “…” şeklinde bitip bitmeyeceğini (Add an allipsis) ilgili seçenekler yardımıyla ayarlayabilirsiniz.

views ile yazıya devamını oku alanı ekleme

Eğer Content:Link alanını tercih etmişseniz (yukarıdaki anlatım üzerinden gidecek olursak) Add a read-more link if output is trimmed seçeneğini seçmiyoruz. Onun yerine REPLACEMENT PATTERN yardımıyla REWRİTE RESULT‘un hemen altında yer alan Rewrite the output of this field seçeneğini seçerek Text kısmına [body] [view_node] ifadesini yazıyoruz.

Ve böylece link alanı ekleyerek ya da nid alanı ekleyerek yazı sonuna nasıl “devamını oku” eklenir göstermiş olduk. Konuyla ilgili daha fazla bilgi almak için aşağıda vereceğim yazıları gözden geçirmeyi ihmal etmeyin.

Yararlanılan Kaynaklar:
SHOWREPLACEMENT PATTERNS
how-to-set-the-read-more-link-in-rewrite-rules-for-body-field-to-point-to-th
rewrite-results-read-more-link-death