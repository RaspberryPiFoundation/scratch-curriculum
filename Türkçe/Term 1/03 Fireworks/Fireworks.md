1.Düzey

Havai Fisek

Tanıtım:

Bu projede, gökyüzünde havai fişek gösterisi oluşturacağız. 


Adım 1: Bilgisayar faresine doğru uçan bir roket tasarla. 


Proje için değişik resimler aktaralım

1. Yeni bir Scratch projesine başla. Fareyi kedi karakterinin üstüne tutup sağ tıkla ve sil seçeneğine git.
2. Arka plandaki resmi açık hava/ sulu şehir ile değiştir.
3. Dosyadan yeni karakter seç ve Roket karakterini ekle (Kaynaklar/Rocket.png.costume).
4.Yeşil bayrak tıklandığında, roketi görünmez yap.
Bilgisayar faresi tıklandığında, roketi fareye dogru hareket ettir.
5. Aralık tuşuna basıldığında, roket ekranda görünecek ve fareye doğru kayacak. 


```scratch

	Bayrak tıklanınca

	sakla

	
	Ara tuş basılınca
	goster
	kaydır 1 saniye x: fare x y: fare y-
```
		
Projeni dene. 
Yeşil bayrağı tıkla, Biligsayar faresini sahne kelimesinin üzerine kaydır ve ara tuşuna bas. 

Roket görünüp, bilgisayar faresine doğru hareket etti mi? 
Bilgisayar faresini tekrar hereket ettirip, ara tuşa bastığında ne oldu? 

6. Havai fişekler kenardan kenara uçmazlar, ekranın altından bilgisayar faresine 
doğru kaymaları gerekli. Roketi görünür yapmadan önce, 'go' codlamasını kullanarak, 
ekranın altına doğru hareket ettir ve aynı yatay çizgide kalmasını sağla.

```scratch

	Bayrak tıklandığında

	sakla

	
	Ara tuş tıklandığında
	Ayarla  x: fare x y: -200
	göster
	Kaydır 1 saniye x: fare x y: fare y

```

Projeni dene. 
Yeşil bayrağı tıkla, Biligsayar faresini sahne kelimesinin üzerine kaydır ve ara tuşuna bas. 

Roket görünüp, bilgisayar faresine doğru hareket etti mi? 
Bilgisayar faresini tekrar hereket ettirip, ara tuşa bastığında ne oldu? 

7. Son olarak, bu kodu ara tuş yerine, fare düğmesini kullanarak yazalım.
'when space key pressed' kodunu, 'when flag clicked' kodu ile değiştir ve  roketin program başladığında görünmez olmasına dikkat et.

```scratch

	
	Bayrak tıklandığında
	sakla
	eğer fare tıklandıysa devamlı gizle
		Git  x: fare x y: -200
		göster
	Kaydır 1 saniye x: fare x y: fare y
	(Dur)

```
Projeni dene. 
Yeşil bayrağı tıkla, Biligsayar faresini sahne kelimesinin üzerine kaydır ve ara tuşuna bas.

Ekstra hedefler:
1. Roketi kaydırmadan önce, konumunu değiştir.
2. Roketlerin bazılarını diğerlerinden daha hızlı veya yavaş yap.

Ekstra hedefler:

Adım 2: Roketi patlatmak

￼1.Roketi patlatmak için, ilk olarak hareket etmeden önce patlama sesi yap Kaynaklar/bang ve sonra fareye değene kadar görünmez yap. Ses eklemek  için SES düğmesine bas ve içeri aktar seçeneğini tıkla.

```scratch

	
	Bayrak tıklandığında 
	sakla 
	eğer fare tıklandıysa devamlı gizle
		Git x: fare x y: -200
		Bang sesi oynat
		göster
		kaydır 1 saniye  x: fare x y: fare y
		Sakla
		(Dur)

```
2. Roket patladığı zaman, roketin mesaj yayınlamasını programla

```scratch

	Bayrak tıklandığında 
	sakla 
	eğer fare tıklandıysa devamlı gizle
		Git x: fare x y: -200
		Bang sesi oynat
		göster
		kaydır 1 saniye  x: fare x y: fare y
		Sakla
		Mesaj yayınla
	(Dur)

```
Projeni dene. 
Yeşil bayrağı tıkla.
Roket fareye ulaştığı zaman ses yapıp görünmemesinden emin ol.

3. Kaynaklar dosyasından firework1.png adlı karakter aktar.
4. Patlama mesajını aldığında, karakter gizlenmeli ve rokete doğru hareket etmeli, sonra gorünmeli, ve bir saniye sonra tekrar görünmez olmali


```scratch

	Patlama mesajı gelince

	sakla

	Git  x: x konum of roket y: y konum of roket
	
	göster
	
	1 saniye bekle
	
	Gizle 

```
Projeni dene.
Bir roket daha ekle.
DPatladığı zaman, patlama resmi onun yerini aldı mı? 
Fareyi kullanırken, aşağı basarsan ne olur? (Bunu daha sonra çözegeğiz).

Projeni kaydet

Adım 3: Her patlamayı farklı yap

1. Renkleri kullanarak patlamaları farkli yapabiliriz. Bunun için, 1 ile 200 arası bir renk seç.

```scratch

	Patlama mesajı gelince

	sakla

	1 ile 200 arası bir renk seç.
	
	git x: x roketin konumu y: y roketin konumu
	
	göster
	
	1 saniye bekle
	
	Gizle 

```

Projeni dene.
Yeşil bayrağı tıkla.

Her patlama değişik renkte mi?

2. Her roket için Kaynaklar/firework2.png ve Kaynaklar/firework3.png  kostümlerini kullan. 

Projeni dene.
Yeşil bayrağı tıkla.

Her roketin farklı patlama grafiği var mı?

3. Son olarak, patlamanın aniden olması yerine zamanla büyümesi için kod yazalim. 1 saniye bekle kodu yerine, karakterin büyüklüğünü göstermeden once 5% olarak yaz. Karakter göründükten sonra, tekrar et seçeneğini kullanarak 2 kere elli defa daha büyük yapın

```scratch

Patlama mesajı gelince

	sakla

	1 ile 200 arası bir renk seç.
	
	git x: x roketin konumu y: y roketin konumu
	
	Büyüklük 5%
	
	göster
	
	Tekrar et 50
	
	change size by 2
	
	(tekrar etme)
	
	Gizle

```
Projeni dene.
Yeşil bayrağı tıkla.

Patlama roketin merkezinden yayılıp, yavaşça büyüyor mu?

Extra hedefler:
Patlamaları, ses ve hızlarını değiştirerek benzersiz yapalım mı?

Projeni kaydet.

Adım 4: Mesaj yayınlama sorununu çözüm bulma

Bilgisayar faresini tıklama konusunda yaşadığımız sorunu hatırlıyormusun?

Bunun sebebi, roket patladığı an,  bir önceki patlama bitmeden, yeni patlama mesajı yollamasıdır.

Bu sorunu çözmek için, mesaj kodunu, mesaj ve bekle kodu ile değiştirmemiz lazım. Böylece, ikinci patlama mesajı birincisi bitinceye kadar başlamıyacak.

```scratch

	wBayrak tıklandığında 
	sakla 
	eğer fare tıklandıysa devamlı gizle
		Git x: fare x y: -200
		Bang sesi oynat
		göster
		kaydır 1 saniye  x: fare x y: fare y
		Sakla
		Mesaj yayınla ve bekle
	(Dur)
	
```
Projeni test etmek için, yeşil bayrağin üzerine tıkla, bilgisayar faresini sahnenin üstünde kımıldatıp, ara tuşa bas.

Roket ekranda görünüyor mu ve bilgisayar faresini izliyor mu? Bilgisayar faresini kımıldattığında ve ara tuşa bastığında ne oluyor?

Projeni kaydet.
