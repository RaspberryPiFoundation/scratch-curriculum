2.Düzey

#Meyve Makinası

__Tanıtım:__
Bu basit oyunda kılık değişteren 3 kukla vardır. Hepsi aynı anda aynı resmi gösterdiğinde makinayı durdurmanız lazım (meyve makinası gibi).

##1.Adım: Kılık değiştiren kukla yapmak

__Oyun için farklı resimler aktaralım__

1. Yeni bir Scratch projesine başla. Fareyi kedi karakterinin üstüne tutup sağ tıkla ve sil seçeneğine git
2. Yeni kukla ekle
3. Dosyadan resim seç. Biz hings/bananas1 kullandık, ancak siz istediğiniz resmi kullanabilirsiniz.
4. Kılıklar dosyasını açıp, oyuna 3 tane daha kukla ekleyin
(Biz animals/bee1 ve things/lego kullandık, ancak siz istediğiniz resmi kullanabilirsiniz.).

__Kuklaların kılık değiştirmeleri için.__

##2.Adım: Resim değiştirmek

1. Kukla tabını tıkla.
2. Kontrol kodunu tıkla ve bayrak tıklanınca kodunu ekle. Yeşil bayrak tıklanınca bu kod aktif olacak.
3. Alta sürekli tekrarla kodunu ekle
4. Sağ köşedeki yeşil bayrağı tıkla. Kodun etrafında beyaz bir çizgi oluştuğuna dikkat et. Bunun s
5. Kılıklar tabını tıkla ve diğer kılığı aktar
6. Kılık değişimini yavaşlatmak için Kontrol kodunu tıkla ve 1 sn bekle kodunu ekle
7. Zamanı ayarla ( 0.1sn uygun olabilir). Eğer bekle kodu olmasaydı, sonuç ne olacakdı?
```scratch

	Bayrak tıklanınca
	sürekli tekrarla	
		sonraki kılık
		0.1 saniye bekle
	(hepsini durdur)
```

###Projeni dene
__Yeşil bayrağı tıkla. .__ 
Kuklaların kılıkları uygun bir hızla değişiyor mu? 

Projeni kaydet

###Extra Hedefler

Bekle kodundaki zaman süresini seç. Oyunu hızlı veya yavaş yapmak için kaç saniye kullanmalı?

##3. Adım: Üzerine basıldığında durdurmak

Harika! Kuklaların sürekli kılık değiştirmesini becerdik. Ancak üzerlerine tıklandığında durmalarını nasıl sağlarız? 

1.Veri tabına bas ve bütün kuklalar için durdu adında bir değişken ekle. Değişkenin sahnede görünmemesi için yanındaki kutuda işaret olmaması lazım.

2.Durdu değişkeni 1 olsun ve birinci kukla tıklanınca, değişken 0 olsun.

3.Durdu değişkeni 1 olunca resimlerin değişmemesi için, kontrol düğmesini tıkla ve 'sürekli tekrarla' kodu yerine 'eğer ise' kodunu kullan. İşlemler tabından 'eşit' işlemini ekle.

4.Son olarak, 'bayrak tıklanınca' kodunun altına 'Kukla 1 durdu 0 olsun' ekle.

###Prejeni dene
__Yeşil bayrağı tıkla, biraz bekle, sonra kuklayı tıkla.__ 

DKukla, tıklanmadan kılık değiştirdi mi? Tıklanınca durdu mu? Fare oku kuklaya değince, tıklanmadan durdu mu? Sahnenin herhangi bir yerine tıklayınca, kukla durdu mu? 
Scratch penceresinin iç veya dış kısmındaki bir alanı tıklayınca ne oldu?

Projeni kaydet

##4.Adım: Diğer kuklaları oluşturmak
__Oyunu oynayabilmemiz için diğer kuklaları yapmamız lazım!__

1.Kukla 1'in üstüne sağ tıkla ve ikizini yap.
2.Tekrar ikizini yap ki, toplam 3 kukla olsun.
3.Kuklaları bir cizgide sırala. Gerekliyse küçült.

###Projeni dene
__Yeşil bayrağı tıkla. Bütün kuklalar değişmeli. Hepsini aynı sahnede durdurmaya çalış.

Projeni kaydet

###Extra hedefler

Yeşil bayrak tıklanınca, kuklaların gelişi güzel kılık değiştirmesini sağla.
ipucu: Oyun başladığı an her kukla için rastgele bir kılık seçin.


__Aferin, oyunu tamamladın ama oyununu daha iyi geliştirebilirsin!__


##Hedef 1: Oyunu zorlaştır 

Oyunun zorluk oranını değiştir. Yaratıcılığını kullan. Öneriler:

1.Kuklaların kılık sayısını değiştir.
2.Bazı kuklalar için benzersiz kılık yap.
3.Kılık değiştirme sürelerini değiştir.
4.Kuklaların bir sonraki yerine ratsgele kılığa geçmelerini sağla.

__Eğlenerek kendi düşüncelerini hayata geçir!__

Oyun dizayn ettiğin zaman, oyunun çok zor veya kolay olmamasına dikkat et. Bunu nasıl kontrol edebilirsin?

##Challenge 2: Make the game get harder and easier over time

Different people will have different skills at playing the game. __How could you make the game adjust its difficulty depending on the player?__

One way you could do it is to __adjust the speed the costumes change at__. You can use a variable, called __delay__, to give the duration of each sprite’s wait block. If the player wins the round, the delay can be reduced a little (to make the game harder). If the player loses the round, the delay can be increased a little (to make the game easier).

##￼Challenge 3: Detect when all the sprites have stopped on the same costume

__The aim of the game is click on the sprites so they’re stopped while showing the same costume. It would be nice if the stage detected when you’d finished playing and then told you if you had won or lost by checking to see if each sprite had the same costume.__

First, the stage needs to know when the player has finished. We can do this by having the stage check to see if all sprites have stopped moving when we click on one of them. Go back and modify each of the sprite# clicked blocks to broadcast a new message, checkForEnd

The Stage canrespond to this message and check if the game is over by seeing if all three sprites’ stopped variables are set to 1, by using the x position of Sprite block for each sprite, and changing “x position” to stopped If all three sprites have a stopped value of 1, we know the game is over and we can check to see if the player has won.

To do this, we can use the same x position of Sprite block, but instead of looking at the stopped variable, we can look at the costume # and see if Sprite1 has the same costume as Sprite2, and if Sprite2 has the same costume as Sprite3.

To do this, you’ll need an if block to check each stopped variable, and inside that an if... else block to see if the player has won or lost by comparing each
costume #

From this point on, you could announce the result of the game using a broadcast and respond to this with another sprite. Maybe get Felix back to congratulate or commiserate the player?


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
