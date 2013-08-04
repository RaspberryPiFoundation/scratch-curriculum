  Düzey 2

#Balık avı

__Tanıtım:__
Balık avı oyunu dizayn edeceğiz. Büyük açgözlü balığa etrafındaki küçük hayvanları avlamasına yardım edin.

##￼STEP 1:Kılık değiştiren kukla yap
__Açgözlü balığın denizde yüzmesini sağlıyalım!__

1.Yeni Scratch perojesine başla
2.Sahne tabını tıkla ve sahne dekoru dosyasından nature/underwater adlı dekoru aktar. Background1'i sil.
3.Birinci kuklanın adını Açgözlü balık olarak değiştir
4.Açgözlü balık kuklasının 1. ve 2. kılıklarını sil ve kılıklar dosyasından hungry-fish kılığını aktar
5.Kılıklar tabının üzerindeki sadece sağ-sola hareket et düğmesine bas
6.Açgözlü balığın bilgisayar faresini takip etmesi için şu kodlamayı yaz:

```scratch

	Bayrak tıklanınca
	Sürekli tekrar et	
		Fare okuna doğru dön
		3 adım git
	(Hepsini durdur)
```

###Projeni dene
__Yeşil bayrağı tıkla.__ 
Bilgisayar okunu deniz etrafında hareket ettir. Balık biligsayar okunu takip ediyor mu? Eğer biligsayar okunu hareket ettirmezsen ve balık yetişirse ne oldu? 
Neye benzer? Niçin bu şekilde sonuçlandı?

7. Açgözlü balığın deli gibi ters donüp yüzmesini, biligsayar okuna yakın olamdığı zaman yüzmesini kodlayarak durdurabilirisniz ( mesafe kodu algılama tabındadır).

```scratch

Bayrak tıklanınca
sürekli tekrarla eğer biligsayar okuna mesafe > 10
	fare okuna doğru dön
	3 adım git
(Hepsini durdur)
```

###Projeni dene

Projeni kaydet

##Extra hedefler

İstersen, kodlamaya farklı numaralar ekleyebilirsin. Bu açgözlü balığın hareketlerini ne şekilde etkiler? Mesafeyi büyük bir rakam ile değiştir (mesela 100), veya küçük bir rakam (mesela 1). Balığın daha fazla (mesela 20) veya daha az hareket etmesini (mesela 1 veya 0) için yazılımı değiştir.

##2. Adım: Daha çok av ekle

1.Animals/lobster1 adlı kuklayı aktar.
2.Sahnenin uzerindeki küçültme dügmesini kullanarak kuklayı küçült
3.Avların yüzmesi için kod yaz. Avların rastgele hareket etmesini istiyoruz, önce ileriye doğru hareket etsinler, sonra rastgele sağa ve sola dönsünler, bunu tekrar et.
```scratch

	Bayrak tıklanınca
	sürekli tekrarla	
		2 adım git
		dön 20 ile -20 arasında rastgele rakam seç
		kenara değdimi geri dön
	(hepsini durdur)
```

###Projeni dene
__Yeşil bayrağı tıkla__ avların yüzmelerini izle. Beklediğin şekilde yüzüorlar mı? Yüzmeleri gerçek yüzmeye benziyor mu?

__Şu an açgözlü balık ve avları arasında bir iletişim yoktur. Sonraki adımda bunu yazacağız.__

Projeni kaydet

###Extra hedefler

* Rastgele ve hareket yazılımlarındaki rakamları değiştir. Avlar şimdi farklı hareket ediyorlar mı? 
* Eğer kenara değerse geri dön kodu ne yapar? Kodu sil ve etkisini gör.

##3.Adım: Açgözlü balık avlarını yer

__Şimdi,açgözlü balığın  avlarını yemesini istiyoruz!__ Açğözlü balık avını ağzına aldığı an 2 şeyin olmasi gerekli:
* Açgözlü balık ağzını kapatıp, "chomp" sesi yapmalı.
* Av bir süre görünmez olup, sonra tekrar goörünmeli.

1. Eaçgözlü balığa değerseğer av, açgözlü balığa değerse 3 saniye görünmez olmalı. 

```scratch

	Bayrak tıklanınca
	sürekli tekrarla	
		2 adım git
		dön 20 ile -20 arasında rastgele rakam seç
		kenara değdimi geri dön
		Eğer açgözlü balığa değerse
			gizle
			3 saniye bekle
			göster
			(eğer ise)
	(hepsini durdur)
	
```

###Projeni dene
__Projeni tekrar dene – Herhangi bir sorun var mı?__ Avın, açgözlü balığın neresine dokunursa dokunsun kaybolduğunu farket. Onun 3 saniye bekleyip, av görünür görünmez yemesi iyi değil.

2. Avın sadece acgözlü balığın ağızına dokunduğu an görünmez olmasını nasıl sağlarız? Renk kodunu kullanabiliriz. Değme kodunu, renk kodu ile değiştirmek için, önce renge dokun, sonra açgözlü balığın dişine dokun.
3. Avın tekrar görunmeden önce, farklı noktalara gitmesi için x ve y için 'rastgele rakam seç ve noktasına git' kodu kullan.

```scratch

	Bayrak tıklanınca
	sürekli tekrarla	
		2 adım git
		dön 20 ile -20 arasında rastgele rakam seç
		kenara değdimi geri dön
		Eğer [] rengine değerse
			gizle
			3 saniye bekle
			x:rastgele -220 to 220 y: random -170 to 170 noktasına git
			göster
			(eğer ise)
	(hepsini durdur)

```
###Projeni dene

Oyunu tekrar dene- Av sadece balığın ağızına dokununcamı kayboluyor? Tekrar göründüğünde, avlandığı noktadan farkl bir noktada mı görünüyor?

4. Balık avını yediği zaman, bunu algılayıp, ses çalıp kılık değiştirmesi lazım. Bunun için, avın görünmez olmadan once haber salması gerekli.
```scratch

		Bayrak tıklanınca
	sürekli tekrarla	
		2 adım git
		dön 20 ile -20 arasında rastgele rakam seç
		kenara değdimi geri dön
		Eğer [] rengine değerse
			Yakalandım haberini sal
			gizle
			3 saniye bekle
			x:rastgele -220 to 220 y: random -170 to 170 noktasına git
			göster
		(eğer ise)
	(hepsini durdur)
```
__Şimdi, balığın cevap vermesi için 'chomp' sesi yap ve çenesini kapat.__

5. Açgözlü balık kuklasına kaynaklar dosyasından, motuh-closed kılığını ve chomp sesini ekle.
6. Balığın avına cevap vermesi için yeni kod yaz. Bu kod balığın chomp sesi yapmasını ve mouth-closed kılığına girmesini, biraz bekleyip, geri kılık değiştirmesini sağlamalı.

```scratch

	Yakalandım haberi gelince
	chomp sesi çal
	2 defa tekrarla
		mouth-closed kılığına geç
		0.5 saniye bekle
		açgözlü balık kılığına geç
	(hepsini durdur)
```

__Şimdi, balık avlanmaya hazır, okyanusu av ile dolduralım. Av kuklasına sağ tıkla ve 'ikizle' seçeneğine bir çok defa bas.__

###Projeni dene
Yeşil bayrağı tıkla
Balık avını yedi mi? Balık bütün avlarını yedi mi?

Projeni kaydet

###Düşünülmesi gereken konular
Av yazılımına neden 'göster' kodu ile başladık? Eğer av, yakalandıktan sonra, tekrar görünmeden önce oyun dursaydı ne olurdu? Oyun bundan sonra tekrar başlarsa ne olurdu?

__Aferin, oyununu tamamladın. Oyununu daha ilginç yapabilirsin. Duelloya hazır mısın?


##Extra Hedef 1: Avları farklı şekilde hareket ettir 

Bütün avlar aynı şekilde hareket ediyor? Birini farkli hareket ettire bilir misin?__
__ipucu:__ Bu projedeki diğer aktivetelere bakmadan bu soru için çok zaman harcama

__Avlardan birini seç.__ Eğer kılıkları aynı ise, farklı renk yap. Böylece onu diğerlerinden ayıra bilirsin.

Bu avın diğerlerinden daha yavaş hareket etmesini sağla. __ipucu:__ (2) adım git koduna bak.


###Projeni dene
Av daha yavaş hareket ediyor mu? Bu oyunu daha iyi yaptı mı?
--Bir balığı, diğerinden daha hızlı hareket ettire bilirmisin?.__


Bu değişiklikler oyunu daha iyi yaptımı?
__ipucu:__ Eğer av daireler çizerek yüzüyorsa, rastgele rakam seç kodundaki değerleri kontrol et.

Bu değişiklikleri kullanarak, her avın farkli davranmasını saglaya bilir misin?

Bu değişiklikler oyunu daha iyi yaptımı?  Oyun daha ilginç, daha eğlenceli, daha kolay veya zor oldu mu? Bunlar daha mi iyi?

Projeni kaydet

##Extra Hedef 2: .Avın açgözlü balıktan sakınmasını sağla 

Bu oyundaki avlar aptal. Avlanana kadar rastgele yüzüyorlar. Gerçek av, avcısından uzaklaşır. __Avlardan birini, balıktan uzağa yüzdürelim.__

Scratch programında, kuklaların yönünü belirten kod yoktur. Ancak bir avın diğer ava bakıp, diğer yöne dönmesini sağlayabilirsin. Bunun için gerekli kod 'Hareket' paletindedir.
Bu bilgiyi kullanarak, avlardan birinin hep balıkdan uzağa dönmesini sağla. Yüzerken kıpırdatata bilirsin.

###Projeni dene
Bu avın yakalanmasını zorlaştırdı mı? Oyunu daha iyi yaptı mı?

Projeni kaydet

##Extra Hedef 3: Puan ekle
It’s not enough just to eat fish. How do you know you’re better at the game than your
friends? __You need a way to keep score so lets add a score board.__ Look at the __Keep Score scratch card__ for an idea of how to do it. 

Where should you put the block that changes the score?

Make sure the score goes back to zero at the start of the game. Where should you put that block?

###Projeni dene
￼￼￼Does the score go to zero at the start of the game? Does it go up every time you eat prey?

Projeni kaydet

##Extra Hedef 4:Geriye doğru sayma ekle

__Give yourself a time limit in the game.__ How many fish can you eat in thirty
seconds?

Look at the __Timer scratch card__ for how to add a timer to the game. Start with the game lasting thirty seconds.

###Projeni dene
Does the timer start at 30?

Does it go down at the right speed?

Can you catch prey while the timer is going?

Does the game stop when the timer reaches zero?

Projeni kaydet

##Extra Hedef 5: :Ödül puanı ekle
Award a large bonus score if you can eat all three fish at the same time. How can
you tell how many fish have been eaten?
__Hint:__ One way to do this __uses a variable to count how many prey are swimming around.__

Projeni kaydet

##Extra Hedef 6: Oyunu değiştir; av canlı kalsın

__Modify the game so that, instead of you controlling a fish that tries to eat the others, you control one prey in a sea with lots of Hungry Fish.__ How long can you last before you’re eaten?

Projeni kaydet

__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!T
