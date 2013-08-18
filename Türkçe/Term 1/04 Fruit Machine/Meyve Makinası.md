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

###Projeni dene
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

##Hedef 2: Oyunu zamanla zorlaştır 

Her insanın oyun oynama yeteneği farklı olacaktır. Dolayısıyla oyununun herkesin düzeyiıne uygun olması için ne yapman gerekir?

Bunu kılık değiştirmenin hızını ayarlayarak yapabilirsin. 'Gecikme' değişkeni kullanarak her kuklanın bekleme zamanını farklı ayarlayabilirsin. Eğer oyuncu oyunu kazanırsa gecikme süresi azaltilabilir ( oyunu zorlaştırma), kaybederse arttırılabilir (oyunu kolaylaştırma).


##Hedef 3: Bütün kuklaların aynı kılıkta olduklarında durduğunu algıla

__Oyunun hedefi, kuklalar tıklandığında, hepsi durur ve aynı kılığı gösterirler. __

Sahnenin oyun bittiği an bunu algılayıp oyuncuya kazanıp kazanamadığını söylemesi oyunu daha zevkli yapacaktır. 

Bunun için, sahnenin oyuncunun oyunu bitirdiğini algılaması lazım. Sahne, kuklaların tıklandıklarında  hareket edip etmediklerine bakarak bunu algılar. Kuklalara, 'checkForEnd' haberini sal kodunu ekle.
Kuklaların x noktası  ' eğer durdu değişkeni 1 ise oyun sona ermiştir' şeklinde kodlanır.

X noktasını kullanarak, bu sefer 'durdu' yerine, 'kılık' tabına bakalım. Eğer Kukla 1, kukla 2 ile aynı kılıkta ise, kukla 2 kukla 3 ile aynı kılıkta ise oyuncu oyunu kazanmıştır.

Haber yayınlama kullanarak, oyunun sonucunu bildirebilirsiniz. Felix oyunculara 'aferin' diyebilir.


__Aferin, oyunu tamamladınız!__
Oyununuzu aile ve arkadaşlarınızla, menu çubuğundaki__paylaş__ düğmesine basarak paylaşabilrisiniz.!
