1.Düzey

#Cadı yakalamaca

Tanıtım:
Bu proje köstebek yakalama oyununa benzer. Ekranda beliren her cadıya vurduğunuzda puan alırsınız. Amacınız 30 saniye içerisinde alabildiğiniz kadar puan almaya calismaktır!

1.Adım: Uçan cadi dizayn etmek

1.Yeni bir Scratch projesine başla. 
2.Kedi karakterini sil ve doga/orman arka planını sec. 
3.Karakter dosyasından cadı karakterini ekrana ekle ( Fantazi/cadı1 kostümünü sec).

Şimdi cadıyı hareket ettirmeniz gerekli

4. Sadece bu karaktere hız değıskeni ekle. Ekranda, sahne bölümünde " Karakter 1 hız" yazılmış olmali. 
Eğer  sadece "hız" diyorsa, değişkeni sil ve yeniden sadece bu karakter için ekle. 
Değişken kısmındaki hız düğmesinin yanındaki seçenek kutusunu boş bırak. 
Hız değişkeni cadı karakterinin hareket hızıni kontrol eder.  
5. Cadının oyun başladığı an hareket etmesi için bu kodlamayı ekleyin:


```scratch

    	Bayrak tıklanınca
	hızı 5'e ayarla
	durmadan
		Hareket et
	(dur sonsuza kadar)

```
		
Projeni dene. 
Yeşil bayrağı tıkla,  cadının ne yaptığını izle. Niçin ekranın sonuna takılıyor?

6. Cadının takılmasını engellemek için, kenara değdiğinde onu diğer yöne hareket ettirmemiz gerekli.  Bunun için ‘move speed steps’ altına ‘if on edge, bounce’ codu ekle.

```scratch

	Bayrak tıklanınca

	hızı 5'e ayarla

	durmadan

		Hareket et

		Kenara değerse

	(Tam dur)
```
7. Cadının ters dönmesini engellemek için, karakter özeti kısmındaki soldan-sağa düğmesine bas.

Projeni dene. 
Yeşil bayrağı tıkla, 
Cadı ekranın bir kenarından diğer kenara doğru hareket ediyormu?

Projeni kaydet.

Ekstra hedefler:
Cadının hızını değiştir.
Cadının uçtukça hızlanması nasıl mümkün?

(Bu biraz zor, yapamazsan üzülme.Projeleri yaptıkça, daha iyi öğreneceksin.)

Adım 2: Cadının gelişi güzel görünüp, kaybolmasını sağlamak

Oyunun daha zevkli olması için cadının gelişi güzel görünüp, kaybolmasını sağlamak.
Bunun için, yeni bir kod yazacağız. Yeni kodun, cadıyı bir süre saklayıp, sonra bir süre göstermesi lazım.(Oyun bitene kadar).
Bu kodu yaz:

```scratch

	bayrak tıklandığında

	Durmaksızın

		Sakla

		Bekle  gelişigüzel seç 2 to 5 saniye

		göster
		
                Bekle  gelişigüzel seç 3 to 5 saniye


	(hep dur)
```
Projeni dene.
Yeşil bayrağı tıkla.
Cadı ekranın bir kenarından diğer kenara doğru gelişigüzel, bazen görünüp, bazen kaybolup hareket ediyormu?

Projeni kaydet.

Ekstra hedefler:
Gelişiguzel numaraları değiştir, çok büyük ve çok küçük numaralar seçtiğinde ne oldu? 
(Bu sana hız ayarının nasıl ayarlanacağını öğrettimi?) 

Adım 3: Cadıyı tıklandığında görünmez yap

Bunu oyuna dönüştürmek için, oyunu oynayana hedef vermemiz lazım. Oyuncu cadıya basarak görünmez yapmalıdır. Cadı tıklandığıında gizlenip, ses yapmasını programlamalıyız.

1. Ses bölümünden electronic/fairydust sec.

2. Aşağıdakı kodu cadı karakterine ekle

```scratch

	Birinci karakter tıklandığında

	Sakla

	Fairydust sesini oyna 
```
Projeni dene. 

Yeşil bayrağı tıkla.

Cadı karakteri görünmez olup, tıklandiığında ses yapıyor mu?

Projeni kaydet.

Adım 4: Puan ve zaman kodu ekle

Cadı karakterimiz var, ama oyun yapmamız lazım.! Cadıyı her tıkladığımızda puan alıp, zaman sınırlaması yapmamız lazım. Zaman ve puan için değişken kullanmamiız lazım.


1. Her karakter için puan değişkeni yarat, cadı karakteri her tıklandığında bu değişkenin birer birer artması gerekli.

```scratch

	Karakter 1 tıklandığında

	Sakla

	Fairydust sesini oyna 

	Puanı 1 yükselt
```
2.Sahne bölümüne tıkla ve zaman denilen değişken yap. Yeni kod ekle: Yeşil bayrak tıklandığında, zamanı 30'a ve puanı 0'a kur. ... kadar tekrar et dügmesini kullan, 1 saniye bekle, sonra zamanı bir azalt, bu zaman 0 olana kadar tekrar etmeli. En son oyunu sona erdirmek için dur kodu ekle.-

```scratch

	Yeşil bayrak tıklandığında

	Saati 30’a kur

	Puanı 0’a kur

	Tekrar et  saat = 0

		1 saniye bekle

		saati değiştir -1

	(tekrar etme)

	her şeyi durdur
```


Projeni dene. 
Yeşil bayrağı tıkla.

Projeni kaydet.

Ekstra hedefler:

Cadının hızlı gitmesi için ne yapmak gerek? 


Aferin, oyunu tamamladın. Daha değişik kodlar ekleyebilirsin. 

Mesela: Daha çok cadı ekle.

3 tane daha cadı ekle
1.Cadı eklemek için karakterin üstüne sağ tuş bas ve kopyala 
2.Cadıları farklı büyüklükte yap 
3.Farkli hızlarda uçmalarını kodla 
4.Cadıları ekranda ayrı yerlere koy 

Projeni dene.
Yeşil bayrağı tıkla.

Ekranda, bir kenardan diğer kenara hareket eden, gelişigüzel görünüp kaybolan, üzerine tuşlanınca kaybolan 3 cadı var mı?

Extra hedefler:
1.Oyun için kaç tane cadı olması yeterli olur? 
2.Cadıların farklı görünmelerini sağlarmısın? Bunun için cadıların kostümlerini yeniden düzenleye bilirsiniz. 
3.Cadıların farklı puan vermesini kodlarmısınız? Mesela, en hızlı cadı 10 puana eşit.

Aferin, oyunu tamamladın. Şimdi eğlenerek oyna. Oyununu arkadaşlarınla ve ailenle paylaşmak için 'paylaş' düğmesine bas.
