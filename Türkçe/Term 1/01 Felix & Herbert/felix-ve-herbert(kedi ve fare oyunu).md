1.Düzey

#Felix & Herbert ( Kedi ve fare oyunu)

__Tanıtım:__
Felix adlı kedinin, Herbert adlı fareyi yakalayacağı bir oyun dizayn edeceğiz. Herbert'i bilgisayar faresi ile kontrol edip, Felix'in sizi yakalamasına izin vermeyin. Ne kadar uzun süre Felix'i engellerseniz, puanınız o kadar yükselir. Eger yakalanırsanız, puan kaybedersiniz.

##1.Adım: Felix bilgisayar faresini izler

1. Yeni projeye başla. 
   Doğru yapıp yapmadığınızı aşağıdaki onay kutularını kullanarak kontrol edebilirsiniz:
Kuklanın yanındaki sahne düğmesine bas ve arka plan dosyasını aç, indoors/hall isimli dekoru aç. Sahnedeki boş dekoru sil.
3. Kuklanın adını Felix olarak değiştir.
4. Felix'in sadece sol-sağ ilerlemesi için bu düğmeyi tıkla:
5. Bu kodu yaz:

```scratch

	Bayrak tıklanınca

	Sürekli tekrarla

		Fare oku'na doğru dön

		10 adım git

		Sonraki kılık

		62 davulunu 0.3 vuruş çal

	(Hepsini Durdur)
```
		
###Projeni dene.
__Yeşil bayrağı tıkla.__
Felix bilgisayar okunu takip ediyor mu? Hareket ettiği zaman yürüyor gibi görünüyor mu? Doğru hızda hareket ediyor mu?

Projeni kaydet

##2.Adım: Felix, Herbert'i kovalar

__Şimdi, Felix'in bilgisayar faresi yerine Herbert'i kovalamasını istiyoruz.__

1. Dosyadan yeni kukla seçeneğini seçerek, animals/mouse1 isimli resmi aktar.
2. Karakterin ismini Harbert olarak değiştir
3. Kılığı Felix'den daha küçük yap. Ufaltma düğmesine 6 kere bas.
4. Herbert'in sadece sol-sağ ilerlemesine dikkat et.. 
5. Herbert'e şu kodu ekle:


```scratch
	
        Bayrak tıklanınca
	Sürekli tekrarla
		Fare oku'na doğru dön
		Felix'e doğru dön
	(Hepsini Durdur)
```

###Projeni dene
__Yeşil bayrağı tıkla..__

Herbert bilgisayar faresini takip ediyor mu? Felix, Herbert'i kovalıyor mu?

Projeni kaydet.

##3.Adım: Felix diyor ki: Herbert'i yakaladığım an

__Felix'in Herbert'i yakaladığı zaman bize haber vermesini istiyoruz.__


1. Felix'in kodunu şu şekilde değiştir:

```scratch
	
Bayrak tıklanınca
	Sürekli tekrarla
		Fare oku'na doğru dön
	        10 adım git
	        Sonraki kılık
		62 davulunu 0.3 vuruş çal
	        Eğer Herbert'e değerse
	        1 saniye seni yakaladım! haberini sal
		(Dur eğer)
	(Hepsini Durdur)

###Projeni dene
__Yeşil bayrağı tıkla..__

Felix, Herbert'i yakaladığını söyledi mi?

Projeni kaydet.

##4.Adım: Herbert yakalandığı zaman hayalete dönüşür.

Herbert yakalandığı zaman, Felix'in konuşması yerine, hayalete dönüşmesini istiyoruz.

1. Felix'in, Herbert'i yakaladığı zaman bu mesajı vermesi için Felix'e şu kodu ekle:

```scratch
	Bayrak tıklanınca
	Sürekli tekrarla
		Fare oku'na doğru dön
	        10 adım git
	        Sonraki kılık
		62 davulunu 0.3 vuruş çal
	        Eğer Herbert'e değerse
	       		 1 saniye seni yakaladım! haberini sal
	       		 58 davulunu 0.3 vuruş ça
		       	 1 saniye bekle
		(Dur eğer)
	(Hepsini Durdur)
```
2.Herbert için, fantasy/ghost2-a isimli kostümü aktar. 

3.Kostümü küçült. Küçült düğmesine 6 kere bas.

4.Herbert'in kostümlerinin ismini değiştir. Fare kostümüne ' hayatta', hayalet kostümünede ' öldü' adını ver. Herbert'in hayalete dönüşmesi için yeni bir kod ekle:
```scratch
	
	Yakalandı haberi gelince
	Ölü kılığına geç
	0.5 saniye bekle
	Hayatta kılığına geç
```
	
###Projeni dene
__Yeşil bayrağı tıkla..__

Herbert yakalandığı zaman hayalete dönüşüyor mu? 
Felix doğru anda doğru sesi oynuyor mu? 
Felix, Herbert'in uzaklaşmasına yetecek süre kadar hareketsiz bekliyor mu?

Projeni kaydet.

##5.Adım:Puan tut

Puan ekleyelim ki, Herbert'i hayatta tutma konusunda ne kadar başarılı olduğumuzu bilelim. 
Puana sıfır ile başlayacağız ve her saniye 1 ekleyeceğiz. Eğer Felix, Herbert'i yakalarsa, 100 puan düşüreceğiz.

1.Bütün karakterler için puan adlı değişken yap. Üst kısımdaki Değişkenler bölümüne tıkla ve puan 2 isimli değişken yap. 
2.Sahne ekranında şu iki kodu ekle:

```scratch
	
	Bayrak tıklanınca
	Puanı 0 olsun
	Sürekli tekrarla
		Puanı 1 arttır
		1 saniye bekle
	(Hepsini Durdur)
	
	Yakalandı haberi gelince
	Puanı 100 numara indir (-100)
```
###Projeni dene
__Yeşil bayrağı tıkla..__

Puan her saniye 1 numara artıyor mu? Puan Herbert yakalanınca, 100 numara azalıyor mu? Herbert puan 100 olmadan önce yakalanınca ne oluyor? Yeni oyuna başladığında, puan sıfır oluyor mu?

Projeni kaydet.

__Aferin, oyunu tamamladın, şimdi eğlenerek oynayabilirsin.__
Oyununu arkadaşlarınla ve ailen ile paylaşmak için menü çubuğundaki 'paylaş' seçeneğine bas.
