1.Düzey

#Havai Fisek
__Tanıtım:__
Bu projede, gökyüzünde havai fişek gösterisi oluşturacağız.

##1. Adım: Bilgisayar faresine doğru uçan bir roket tasarla

__Proje için gerekli resimleri aktaralım.__

1. Yeni bir Scratch projesine başla. Fareyi kedi karakterinin üstüne tutup sağ tıkla ve sil seçeneğine git.
2. Sahne resmini bina dışı/ sulu şehir ile değiştir.
3. Dosyadan yeni karakter seç ve Roket karakterini ekle (Kaynaklar/Rocket.png.costume).
4. Yeşil bayrak tıklandığında, roketi görünmez yap.

Bilgisayar faresi tıklandığında, roketi fareye dogru hareket ettir.

5. Aralık tuşuna basıldığında, roket ekranda görünecek ve fareye doğru kayacak. 

```scratch

	Bayrak tıklanınca

	gizle

	boşluk tuşu basılınca
	göster
	1 sn.de x: mouse x y: mouse y süzül
```
		
###Projeni dene
__Yeşil bayrağı tıkla, Biligsayar faresini sahne kelimesinin üzerine kaydır ve 	boşluk tuşuna bas.__

Roket görünüp, bilgisayar faresine doğru hareket etti mi? 
Bilgisayar faresini tekrar hereket ettirip, ara tuşa bastığında ne oldu?

6. Havai fişekler kenardan kenara uçmazlar, ekranın altından bilgisayar faresine doğru kaymaları gerekli. 
Roketi görünür yapmadan önce, 'go' codlamasını kullanarak, ekranın altına doğru hareket ettir ve aynı yatay çizgide kalmasını sağla.

```scratch

	Bayrak tıklanınca

	gizle

	boşluk tuşu basılınca
	x: mouse x y: -200 noktasına git
	göster
	1 sn.de x: mouse x y: mouse y süzül
```

###Projeni dene
__Yeşil bayrağı tıkla, Biligsayar faresini sahne kelimesinin üzerine kaydır ve boşluk tuşuna bas.__ .__ 
Roket görünüp, bilgisayar faresine doğru hareket etti mi? Bilgisayar faresini tekrar hereket ettirip, ara tuşa bastığında ne oldu? 

7. Son olarak, bu kodu boşluk tuşu yerine, fare düğmesini kullanarak yazalım.__sürekli tekrarla eğer fare tıklandıysa __.
__Boşluk tuşu tıklanınca__ kodunu __Bayrak tıklanınca__ akodu ile değiştir ve  
roketin program başladığında görünmez olmasına dikkat et.

```scratch

	Bayrak tıklanınca

	gizle
	sürekli tekrarla eğer fare tıklandıysa
	x: mouse x y: -200 noktasına git
	göster
	1 sn.de x: mouse x y: mouse y süzül
```
	(hepsini durdur)
```
###Projeni dene
Yeşil bayrağı tıkla, Biligsayar faresini sahne üzerine kaydır. Rastgele farklı bir noktaya tıkla.

###Extra Hedefler
1. Roketi kaydırmadan önce, konumunu değiştir.
2. Roketlerin bazılarını diğerlerinden daha hızlı veya yavaş yap.

Projeni kaydet.

##2. Adım: Roketi patlatmak
Roketi patlatmak için, ilk olarak hareket etmeden önce patlama sesi yap. Ses eklemek için SES düğmesine bas ve içeri aktar seçeneğini tıkla.

```scratch

	bayrak tıklanınca
	gizle
	sürekli tekrarla eğer fare tıklandıysa
		x: mouse x y: -200 noktasına git
		bang sesini çal
		göster
		1 sn.de x: mouse x y: mouse y süzül
		gizle
		hide
	(hepsini durdur)
```
2. Roket patladığı zaman, roketin mesaj yayınlamasını programla

```scratch

	bayrak tıklanınca
	gizle
	sürekli tekrarla eğer fare tıklandıysa
		x: mouse x y: -200 noktasına git
		bang sesini çal
		göster
		1 sn.de x: mouse x y: mouse y süzül
		gizle
		Patla haberini sal
	(hepsini durdur)
```
###Projeni dene
__Yeşil bayrağı tıkla.__ 
Roket fareye ulaştığı zaman ses yapıp görünmemesinden emin ol.

3.Kaynaklar dosyasından firework1.png adlı kuklayı aktar
4.Patlama mesajını aldığında, karakter gizlenmeli ve rokete doğru hareket etmeli, sonra gorünmeli, ve bir saniye sonra tekrar görünmez olmali

```scratch

	when I receive explode

	hide

	go to x: x position of rocket y: y position of rocket

	show

	wait 1 sec

	hide
```
###Test Your Project
__Send another rocket flying.__ 
Does it get replaced with the explosion graphic when it explodes?
What happens if you hold the mouse button down whilst moving the mouse? (Don’t worry, we’ll fix this later on).

Save your project

##￼STEP 3: Make each explosion unique

1. Now we can make each explosion even more unique by using the set color effect block, and have it pick a random colour between 1 and 200 before showing it.

```scratch

	when I receive explode

	hide

	set colour effect to pick random 1 to 200

	go to x: x position of rocket y: y position of rocket

	show

	wait 1 sec

	hide
```

###Test Your Project
__Click the green flag.__ 

Does each explosion have a different colour?

2. Lets add a number of different possible explosion graphics as costumes, using Resources/firework2.png and Resources/firework3.png, and switch between them for each rocket, again before showing it.

###Test Your Project
__Click the green flag.__ 

Does each rocket have a different explosion graphic?

3. Finally, lets make the explosion grow over time as opposed to simply appearing. Instead of waiting a second, set the size of the sprite to 5% before we show it, and then once it’s shown, increase the size by 2 fifty times, using a repeat block.

```scratch

	when I receive explode

	hide

	set colour effect to pick random 1 to 200

	go to x: x position of rocket y: y position of rocket

	set size to 5%

	show
	
	repeat 50
		change size by 2
	(end repeat)

	hide
```
###Test Your Project
__Click the green flag.__ 

Does the explosion graphic spread out from the centre of the rocket and slowly grow?

###Things to try
Why not try making each explosion more unique by altering the size and speed of growth for the explosion.

Save your project

##Step 4: Fixing the Broadcast Bug
Remember earlier we had a bug involving holding down the mouse button?
This occurs because when the rocket broadcasts its explosion, it will immediately repeat the if loop and send out another explosion message, before the last one has finished displaying.


1. To fix this, we can replace the broadcast block with a broadcast and wait block. This way, the loop will not repeat until the explosion finishes exploding.

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		play sound bang
		show
		glide 1 secs to x: mouse x y: mouse y
		hide
		broadcast explode and wait
	(end forever)
```
###Test Your Project
__Click the green flag, hold down the mouse button and move the mouse around the stage.__ 

Does the explosion graphic appear in the right place and at the right time?

Save your project
