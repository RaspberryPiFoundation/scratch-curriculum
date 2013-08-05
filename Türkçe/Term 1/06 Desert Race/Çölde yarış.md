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
4. NBaşlangıç düğmesinin 3'den geriye sayıp, tıklanınca görünmez olamsını istiyoruz. Bunun için bu yazılımı ekle:

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

1. Add a block to the parrot’s script that sets the racing variable to be 0 when the sprite touches the edge of the screen.

```scratch

	bir tuş basılınca
	eğer yarışma verisi = 1
		4 adım git
		kenara değdi mi
			yarışma verisi = 1
		(Dur eğer ise)
	(Dur eğer ise)
```
2. Now we want the parrot to let us know if it wins the race. Record a new sound for the Parrot sprite that will be played when the parrot wins. Click __sounds__ and then record the sound of the a parrot winning the race!
3. Now add blocks that play the sound you recorded and makes the parrot say it has won:

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
4. Now repeat these steps for the lion.

###Projeni dene
__Yeşil bayrağı tıkla.__

Can you press the start button and race by pressing the ‘A’ and ‘L’ keys?
Do the sprites make their winning sound and say they’ve won when they reach the end of the race?

Projeni kaydet

##Adım 5: Oyunu yeniden konumla

After the race is finished we need to tell the other sprites we have won and reset the
game so we can play again.

__We need the winning sprite to broadcast that it has won.__

1. Click on the Parrot sprite.
Add a block that broadcasts “finished” after the sprite says it has won.

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
2. Now we need to add a new script that listens for the finished broadcast and moves the parrot
back to the start. What happens if you change the value that x is set to?

```scratch

	Bitti haberi gelince
	x, -175 olsun
```
3. Now add the same script for the lion. Test different x values to make sure the lion and the parrot line up at the start.
4. We also want to put the lion and the parrot in the same position when the project is run, so add another script to each that moves them to the start
when we click the flag.

```scratch

	bayrak tıklanınca
	x, -175 olsun
```
5. Now click on the button sprite and add a script that shows it when it receives the finished message.
￼￼￼￼￼￼￼￼￼￼
###Projeni dene
__Yeşil bayrağı tıkla.__


Can you race against a friend, one of you moving the parrot by pressing ‘A’ and the
other moving the Lion by pressing ‘L’?

Projeni kaydet

##Ekstra hedefler: Destek ekle


* __Try to add a booster__ that you can use once each race that moves the parrot or the lion __30 steps in 1 go.__
* __Add a new costume__ with fire coming out behind for each sprite and make it appear when the boost is pressed.
* __Create another sound__ that the sprite will make when the boost is pressed.
￼

###Projeni dene

Projeni kaydet


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
