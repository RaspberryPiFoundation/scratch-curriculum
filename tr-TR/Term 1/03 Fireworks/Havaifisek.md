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

##2.Adım: Roketi patlatmak
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

	Patlama haberi gelince

	gizle

	x: x konum of roket y: y konum of roket noktasına git

	göster

	1 saniye bekle

	gizle
```
###Projeni dene
__Bir roket daha ekle .__ 
Patladığı zaman, patlama resmi onun yerini aldı mı? Fareyi kullanırken, aşağı basarsan ne olur? (Bunu daha sonra çözegeğiz).

Projeni kaydet

##3.Adım: Her patlamayı benzersiz yapmak

1. Renkleri kullanarak patlamaları farkli yapabiliriz. Bunun için, 1 ile 200 arası bir renk seç. 

```scratch

	patlama haberi gelince

	gizle

	1 ile 200  arası bir renk seç.

	x: x konum of roket y: y konum of roket noktasına git

	göster

	1 saniye bekle

	gizle
```

###Projeni dene
__Yeşil bayrağı tıkla.__ 

Her patlama değişik renkte mi?

Her roket için Kaynaklar/firework2.png ve Kaynaklar/firework3.png kılıkları kullan. 

###Projeni dene
__Yeşil bayrağı tıkla.__ 

Her roketin farklı patlama grafiği var mı?

3. Son olarak, patlamanın aniden olması yerine zamanla büyümesi için kod yazalim. 1 saniye bekle kodu yerine, karakterin büyüklüğünü göstermeden once 5% olarak yaz. 
Karakter göründükten sonra, tekrar et seçeneğini kullanarak 2 kere elli defa daha büyük yapın
```scratch

	patlama haberi gelince

	gizle

	1 ile 200  arası bir renk seç.

	x: x konum of roket y: y konum of roket noktasına git

	büyüklüğü %5 yap
	
	göster

	50 defa tekrarla 
		2 birim büyüt
	(tekrarlama)

	gizle
```
###Projeni dene
__Yeşil bayrağı tıkla.__ 

Patlama roketin ortasından başlayıp, yavaşca büyüyor mu?

###Extra Hedefler
Patlamanın büyüklüğünü ve hızını değiştirerek her patlamayı benzersiz yapmayı deneyin.

Projeni kaydet

##4.Adım: Haber alma/salma hatasını çözmek
Daha önce bilgisayar faresini aşağı tuttuğumuzda sorunlar olmuştu. 
Bunun sebebi, roketin patlama haberini yayınladığı an, 'eğer' kodunu  harekete geçirip, diğer haber bitmeden, yeni bir haber yayınlamasıdır.


1. Daha önce bilgisayar faresini aşağı tuttuğumuzda sorunlar olmuştu. Bunun sebebi, roketin patlama haberini yayınladığı an, 'eğer' kodunu  harekete geçirip, diğer haber bitmeden, yeni bir haber yayınlamasıdır.

Bu sorunu çözmek için, haber sal kodunu, haber al ve bekle ile değiştirmemiz gerekli. Böylece, kod, patlama bitinceye dek tekrarlanmayacak.

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
		Patlama haberini sal ve bekle
		
	(hepsini durdur)
```
###projeni dene
__Yeşil bayrağı tıkla. Bilgisayar faresinin üzerine bas ve sahnede hareket ettir.__ 

Patlama, uygun zamanda uygun yerde oluyor mu?

Projeni kaydet
