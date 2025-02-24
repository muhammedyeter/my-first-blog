

# Giriş

  

Insider Code Academy'nin fiziksel eğitimine köprü olarak nitelendirilebileceğimiz **Ön eleme Projesi**'nin sonucunda projemi hazırladım ve bugün sizlere bu projede kullandığım kod satırlarından ve bazı seçimlerimi neden yaptığımdan bahsedeceğim.

<br>

# Neden birden fazla CSS belgesi var?

- Sadece bir stil dosyasına sahip bir projenin kod okunabilirliğinde ciddi sorunlar olacağını düşündüm. O yüzden projemde **styles-index.css**, **styles-iletisim.css** gibi birbirinden ayrı css dosyaları kullandım.

<br>


# Neden ``<div>`` dışı etiketlerle kapsama yapıldı?

  

- Aslında her ne kadar ``<div>`` ile aynı işi görseler de "``<section>``, ``<main>``, ``<footer>``, ``<article>``" gibi etiketler yazdığımız kodun okunmasını kolaylaştırıyor.

- Ayrıca bu etiketler **SEO (Arama Motoru Optimizasyonu)** için oldukça yüksek önem taşımakta.

<br>
<br>


# Kod Açıklamaları

**Not** : HTML Kod satırlarının büyük bir çoğunluğu Utility Class dediğimiz sınıflardan oluştuğu için bunların kaynağı olan CSS belgelerindeki bazı kod satırlarını açıklayacağım.

> **Utility Class :** Kodlama kısmında işleri kolaylaştırmak ve kod tekrarını önlemek için kullanılan sınıflardır.

<br>

## reset.css

-  ``box-sizing: border-box;``

	Bu özellik, HTML etiketlerinin boyutlarını hesaplarken padding ve border dahil edilerek hesaba katılmasını sağlar.

	Varsayılan değeri olan ``content-box`` ise, etiketin boyutunu hesaplarken yalnızca **yükseklik** ve **genişlik** değerlerini kullanır. Sonrasında eklenen **padding** veya **border** özellikleri etiketin dışında yer kaplar.
_____
- ```
	margin: 0px;
	padding: 0px;
	```
	
	Bu CSS Bloklarını kullanarak tarayıcıdan gelen varsayılan boşluk ayarlarını sıfırlıyoruz.

	>**Bunu Neden Yapmalıyız?**
		Bu düzeltmelerin yapılmasının sebebi, site içeriğinin tarayıcıdan tarayıcıya değişmesini önlemektir. Çünkü her tarayıcının kendine özgü boşluk değerleri bulunur.
_____
- ```
	input,
	textarea {
		border: initial;
	}
	```
	

	Burada ise  ``<input>`` ve ``<textarea>``   etiketlerine tarayıcıdan **varsayılan** olarak gelen **border** stilinin sıfırlanıp yerine düz bir çizgi hali alması sağlanıyor.
_____
- ```
	p,
	h1,
	h2,
	h3,
	h4,
	h5,
	h6,
	a,
	pre,
	head,
	label,
	input,
	textarea,
	span {
		font-family: inherit;
		font-weight: inherit;
		color: inherit;
		line-height: 1.3;
	}
	```

	Karmaşık gibi duran bu kod bloğunun aslında amacı bazı özellik erişim sorunlarını düzeltmektir.

	Ebeveynlerin altında duran bazı etiketler, onlara atanmış bazı özellik verilerini almazlar. Bu kod bloğu ile ebeveynlerinden onlara atanmış değerleri miras almaları sağlanır.
<br>

## layout.css

- ```
	.navbar {
		z-index: 999;
		...
	```

	Bu özelliğin amacı, bazı **hover animasyonları** ile elemanların navbar üzerine gelmesini engellemektir.

	``z-index: 999;`` özelliği, navbar elementini katman olarak en üste atıyor.

---
- ```
	navbar-shadow-round {
		box-shadow: 0  0  10px  rgba(0, 0, 0, 0.5);
		...
	```
	
	Alıntılanmış bu kod satırında kullanılan ``box-shadow`` değeri, navbar elementinin altına bir gölge bırakmasını sağlıyor.

	Bu değerin parametreleri şu şekildedir :
	``box-shadow: "x"  "y"  "bulanıklaşma"  "renk"``

	**X** ve **Y** parametreleri, gölgenin konumunu belirlemek için kullanılır.

---
- ```
		...
		transition: background-color 2s  ease-out  500ms;
	}
	```
	Buradaki  ``transition`` değeri, atanmış elementin geçişler yapmasına yarıyor. 

	Bu değerin parametreleri şu şekildedir :
	``transition: "özellik"  "geçiş-süresi"  "hız-eğrisi"  "geçiş-gecikmesi"``

	**Özellik** parametresi, elementin hangi özelliğine geçiş yapacağımızı belirtiyor. 
	**Hız Eğrisi** parametresi ise, geçiş hızına bir animasyon eklemek için kullanılır.

	- **ease-in :** Geçiş *yavaş* başlayıp *hızlı* biter.
	- **ease-out :** Geçiş *hızlı* başlayıp *yavaş* biter.

<br>
<br>

# Sonuç
Bu projeyi tamamlarken edindiğim bilgiler ve deneyimler ile birlikte gelecekte yapacağım projelerde daha bilgili olacağıma ve **CC (Crystal Clear)** seviyesinde kodlar yazacağıma inanıyorum. Bunlardan daha fazlasını Insider'da eğitim alarak, belki de orada çalışmaya başlayarak edineceğime eminim. 
