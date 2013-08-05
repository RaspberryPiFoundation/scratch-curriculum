Düzey 2

#Çölde yarış

__Tanıtım:__
Bu oyun iki kişi tarafından oynanır. Oyunda papağan ve aslan çölde yarışırlar. Oyuncular, hayvanları kontrol etmek için klavyede bir düğmeye en hızlı şekilde basarlar. Ekranın sonuna ilk ulaşan oyuncu oyunu kazanır.


##Adım 1: Sahneyi oluştur ve kuklaları ekle

1.Sahneyi seç ve çöl dekorunu ekle. 
2.Hayvanlar dosyasından aslan ve papağan kuklalarını ekle.



##Adım 2: Kuklaları haraket ettir


Kuklanın bir tuşa basınca hareket etmesini istiyoruz.


1.Aslan kuklasını seç ve 'L' tuşu basılınca 4 adım git olarak programla

```scratch

	l tuşu basılınca
	4 adım git
```

2. Papağan kuklasını seç ve 'A' tuşu basılınca 4 adım git olarak programla

```scratch

	l tuşu basılınca
	4 adım git
```

###Projeni dene
__Yeşil bayrağı tıkla__ 
'A' ve 'L' tuşlarına bastığında aslan ve papağan hareket ediyor mu?

Projeni kaydet


##Adım 3: Yarışı başlat

Yarışı başlatmak ve kimin kazandığını algılamamız için bir yol bulmamız lazım. __Önce başlangıç düğmesi oluşturalım.__

1. Dosyadan yeni kukla ekle. 'Things' dosyasından düğme kuklasını seç.
2. Düğme kuklasının kılığını düzenle ve üzerine 'başlangıç' yaz. Kuklayı sahnenin ortasına koy.
3. Proje başladığında kuklanın görünmesi için bu yazılımı ekle:

```scratch

	bayrak tıklanınca
	göster
```
4. Başlangıç düğmesinin 3'den geriye sayıp, tıklanınca görünmez olamsını istiyoruz. Bunun için bu yazılımı ekle:

```scratch

	Yarışa başla tıklanınca
	3 de 1 saniye
	2 de 1 saniye
	1 de 1 saniye
	Git! de 1 saniye
	gizle
	
```
###Projeni dene
__Yeşil bayrağı tıkla.__

Başlangıç dügmesine bastığında, görünmez olmadan önce, geri geri 0'a sayıyor mu

Projeni kaydet

Yarışmacıların yarış başladıktan sonra haraket etmesini  sağlamak ve yarış bitince bunu algılamamız için veri eklememiz lazım.

5. Bütün kuklalar için yarışma adında veri ekle. Yanındaki kutuda işaret olmasınki, sahnede görünmesin.
6. Proje başladığında, yarışma verisi 0 olsun. Bayrak tıklanınca yazılımını şu şekilde değiştir:

```scratch

	bayrak tıklanınca
	göster
	Yarışma verisi 0 olsun
```
7. Geri sayım bitince yarışma verisi 1 olsun..
8. Eğer veri 1 değilse aslan ve papağanın hareket etmemesi lazım. Papağan kuklasını tıkla.
Papağan kuklasına sadece veri 1 olduğunda hareket etmesine izin verecek bir yazılım ekle:

```scratch

	bir tuş basılınca
	eğer yarışma verisi = 1
		4 adım git
	(Hepsini durdur)
```
9. Bunu aslan kuklası için tekrar et

###Projeni dene
__Yeşil bayrağı tıkla.__

Aslan ve papağan geri sayım bittikden sonra hareket etmeye basliyor mu?

Yarışı kimin kazandığını bilmek istiyoruz. Yarış bitince, tekrar başlaması için başlangıca dönmesini istiyoruz.


##Adım 4: Yarışı bitir

1. Papağan kuklasına yeni bir yazılım ekle ki, ekranın kenarına değince, yarışma verisi 0 olsun.


```scratch

	bir tuş basılınca
	eğer yarışma verisi = 1
		4 adım git
		kenara değdi mi
			yarışma verisi = 1
		(Dur eğer ise)
	(Dur eğer ise)
```
2. Papağanın eğer yerışı kazanırsa bize söylemesini istiyoruz. Bunun için ses düğmesine bas ve yeni bir ses kayıt et. 

3. Şimdi, kayıt ettiğin sesi çalıp, papağanın ben kazandım demesini sağlayacak bir yazılım ekle:

```scratch

	bir tuş basılınca
	eğer yarışma verisi = 1
		4 adım git
		kenara değdi mi?
			yarışma verisi 0 olsun
			recordin 1 ses çal
			papağan kazandı de 3 saniye
		(Dur eğer ise)
	(Dur eğer ise)
```
4. Aynı yazılımı aslan kuklasına ekle.

###Projeni dene
__Yeşil bayrağı tıkla.__

Başlangıç düğmesine basa biliyor musun? 'A' ve 'L' tuşlarına basarak yarışa biliyor musun? 
Kuklalar yarış sonunda, yarışı kazanınca ses yapıp, kazandıklarını söylüyorlar mı?

Projeni kaydet

##Adım 5: Oyunu yeniden konumla

Yarışma bitince, bunu diğer kuklalara söyleyip, yeniden başlangıç noktasına dönmemiz lazım.

__Kazanan kuklanın kazandım haberini salması gerekl.__

1. Papağan kuklasına tıkla. Kuklanın kazandığını söyledikten sonra, bitirdim haberini salan bir yazılım ekle.

```scratch

	bir tuş basılınca
	eğer yarışma verisi = 1
		4 adım git
		kenara değdi mi?
			yarışma verisi 0 olsun
			recordin 1 ses çal
			papağan kazandı de 3 saniye
			Haber gelince
		(Dur eğer ise)
	(Dur eğer ise)
```
2. Şimdi, bitirdim haberinden sonra, papağanı başlangıç noktasına götürecek bir kod yazalım. X değerini değiştirirsen ne olur?

```scratch

	Bitti haberi gelince
	x, -175 olsun
```
3. Aynı yazılımı aslan kuklasına ekle. Farklı x değerlerini dene ki, aslan ve papağan başlangıc noktasında hazır olsunlar.
4. Proje başladığında, aslan ve papağanın aynı noktada olmaları için, bayrak tıklanınca onları hareket ettiren bir yazılım ekle.

```scratch

	bayrak tıklanınca
	x, -175 olsun
```
5. Düğme kuklasını tıkla ve bitirdim haberini aldığını gösteren bir kod ekle.
￼￼￼￼￼￼￼￼￼￼
###Projeni dene
__Yeşil bayrağı tıkla.__

Arkadaşınla yarışa bilir misin? Biriniz aslan olsun ve 'A' düğmesine bassın, biriniz papağan olsun ve 'L' düğmesine bassın.

Projeni kaydet

##Ekstra hedefler: Destek / Hızlandırıcı ekle


* Kuklaları bir gidişte, 30 adım ilerletecek bir yazılım ekle.
* Kuklalara arkasından ateş çıkacak bir kılık ekle.
* Kuklalara, hızlandırıcı tıklanınca çalınacak yeni bir ses ekle.
￼

###Projeni dene

Projeni kaydet


__Aferin, oyunu tamamladınız!__
Oyununuzu aile ve arkadaşlarınızla, menu çubuğundaki__paylaş__ düğmesine basarak paylaşabilrisiniz.
