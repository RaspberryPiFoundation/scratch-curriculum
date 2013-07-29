2.Düzey

#Cadı Yakalamaca

__Tanıtım:__
Bu proje köstebek yakalama oyununa benzer. Ekranda beliren her cadıya vurduğunuzda puan alırsınız. Amacınız 30 saniye içerisinde alabildiğiniz kadar puan almaya calismaktır!
##Adım 1: Uçan cadı dizayn etmek

1. Yeni bir Scratch projesine başla. 
2. Kedi kuklasını sil ve doga/orman dekorunu sec. 
3. Kuklalar dosyasından cadı karakterini ekrana ekle ( Fantazi/cadı1 kılığını sec).

Şimdi cadıyı hareket ettirmeniz gerekli

4. Sadece bu karaktere hız değıskeni ekle. 
Ekranda, sahne bölümünde " Kukla 1 hız" yazılmış olmali. Eğer  sadece "hız" diyorsa, değişkeni sil ve yeniden sadece bu karakter için ekle. Değişken kısmındaki hız düğmesinin yanındaki seçenek kutusunu boş bırak. Hız değişkeni cadı karakterinin hareket hızıni kontrol eder.  
5. Cadının oyun başladığı an hareket etmesi için bu kodlamayı ekleyin:


```scratch

	Bayrak tıklanınca

	Puan 5 olsun

	Sürekli tekrarla

		adım git

	(Hepsini Durdur)
```
		
###Projeni dene
__Yeşil bayrağı tıkla__ 
Cadının ne yaptığını izle. Niçin ekranın sonuna takılıyor?

6. Cadının takılmasını engellemek için, kenara değdiğinde onu diğer yöne hareket ettirmemiz gerekli.  Bunun için ‘adım git’ altına ‘Kenara geldiysen sek’ codu ekle.

```scratch

	

	Puan 5 olsun

	Sürekli tekrarla

		adım git
		Kenara geldiysen sek
	(Hepsini Durdur)
```
7. Cadının ters dönmesini engellemek için, Kukla özeti kısmındaki __Kuklanın şekli sağa-sola dönebilsin__ düğmesine bas.

###Projeni dene
__Yeşil bayrağı tıkla__
Cadı ekranın bir kenarından diğer kenara doğru hareket ediyormu?

Projeni kaydet

###Ekstra hedefler 
_Cadının hızını kontrol etmek için, hız değişkenini değiştir.__

__Cadının uçtukça hızlanması nasıl mümkün?__
(Bu biraz zor__, yapamazsan üzülme.)

##Adım 2: Cadının gelişi güzel görünüp, kaybolmasını sağlamak.

Bunun için, yeni bir kod yazacağız. Yeni kodun, cadıyı bir süre saklayıp, sonra bir süre göstermesi lazım.(Oyun bitene kadar).
Bu kodu yaz:


```scratch

        Bayrak tıklanınca

	Sürekli tekrarla

		gizle

		Bekle 2 ile 5 arasında bir sayı tut

		görün

		Bekle 3 ile 5 arasında bir sayı tut

	(Hepsini Durdur)
```
###Projeni dene
__Yeşil bayrağı tıkla.__ 
Cadı ekranın bir kenarından diğer kenara doğru gelişigüzel, bazen görünüp, bazen kaybolup hareket ediyormu?

Projeni kaydet

###Ekstra hedefler 
__Gelişiguzel numaraları değiştir, çok büyük ve çok küçük numaralar seçtiğinde ne oldu?__
(Bu sana hız ayarının nasıl ayarlanacağını öğrettimi?)

##Adım 2: Cadıyı tıklandığında görünmez yap

Bunu oyuna dönüştürmek için, oyunu oynayana hedef vermemiz lazım. Oyuncu cadıya basarak görünmez yapmalıdır. Cadı tıklandığıında gizlenip, ses yapmasını programlamalıyız.
1. Ses bölümünden electronic/fairydust sec.

2. Aşağıdakı kodu cadı kuklasına ekle:

```scratch

	Cadı kuklası tıklanınca

	gizle

	Fairydust sesini çal
```
###Projeni dene
__Yeşil bayrağı tıkla..__ 

Cadı kuklası görünmez olup, tıklandiığında ses yapıyor mu?

Projeni kaydet

##Adım 4: Puan ve zaman kodu ekle

Cadı kuklamız var, ama oyun yapmamız lazım.! Cadıyı her tıkladığımızda puan alıp, zaman sınırlaması yapmamız lazım. Zaman ve puan için değişken kullanmamiız lazım


1. Her kukla için puan değişkeni yarat, cadı kuklası her tıklandığında bu değişkenin birer birer artması gerekli

```scratch

	Cadı kuklası tıklanınca

	gizle

	Fairydust sesini çal

	Puanı 1 arttır
```
2. Sahne bölümüne tıkla ve zaman denilen değişken yap. Yeni kod ekle: Yeşil bayrak tıklandığında, zamanı 30'a ve puanı 0'a kur. ... kadar tekrar et dügmesini kullan, 1 saniye bekle, sonra zamanı bir azalt, bu zaman 0 olana kadar tekrar etmeli. En son oyunu sona erdirmek için dur kodu ekle.

```scratch

	Bayrak tıklanınca

	Zaman 30 olsun

	Puan 0 olsun

	Zaman 0 olana kadar tekrar et

		1 saniye bekle

		Puanı -1 arttır

	(Tekrar etme)

	Hepsini Durdur
```


###Projeni dene
__Yeşil bayrağı tıkla.__ 

Projeni kaydet

###Ekstra hedefler 
__Cadının hızlı gitmesi için ne yapmak gerek?__
__Aferin, oyunu tamamladın. Daha değişik kodlar ekleyebilirsin. Mesela:__

##Daha çok cadı ekle

3 tane daha cadı ekle.
1.Cadı eklemek için karakterin üstüne sağ tuş bas ve kopyala 
2.Cadıları farklı büyüklükte yap 
3.Farkli hızlarda uçmalarını kodla 
4.Cadıları ekranda ayrı yerlere koy 

###Projeni dene
__Yeşil bayrağı tıkla.__ 

Ekranda, bir kenardan diğer kenara hareket eden, gelişigüzel görünüp kaybolan, üzerine tuşlanınca kaybolan 3 cadı var mı?

Projeni dene

###Extra hedefler:
1.Oyun için kaç tane cadı olması yeterli olur? 
2.Cadıların farklı görünmelerini sağlarmısın? Bunun için cadıların kostümlerini yeniden düzenleye bilirsiniz. 
3.Cadıların farklı puan vermesini kodlarmısınız? Mesela, en hızlı cadı 10 puana eşit.
__Aferin, oyunu tamamladın. Daha değişik kodlar ekleyebilirsin. Mesela:__

__Aferin, oyunu tamamladın, şimdi eğlenerek oynayabilirsin!__
Oyununu arkadaşlarınla ve ailen ile paylaşmak için menü çubuğundaki __paylaş__ seçeneğine bas.
