Düzey 3

#Tahmin et

__Tanıtım__
Kara tahtada rastgele bir nesne, biçimi bozulmuş şekilde gösterilir. Doğru resmi tıklayarak ne olduğunu tahmin etmen gerekli. Ne kadar çabuk tahmine dersen, puanın o kadar yüksek olur.
##Adım 1: Tahtada farklı nesnelerin görünmesini sağla

Tahtada bir kaç farklı reimin görünmesini istiyoruz.
1. Yeni Scratch projesi oluştur ve kedi kuklasını sil.
2. Sahneyi tıkla ve dekorlar dosyasından binaiçi/chalkboard dekorunu seç.
3. Yeni bir kukla ekle ve istediğin kılığı seç.
4. Yeni kuklayı ekranın orta noktasına yerleştir. Gerekli ise büyüt veya küçült.
5.Kuklalar gurubuna git ve dört tane daha nesne aktar. Ne olacaklarına sen karar ver. Şimdi rastgele bir resimin görünmesini sağlıyalım.
6. Bu kodlamayı yaz:


```scratch

	bayrak tıklanınca
	tekrarla rastgele 1 ile 5
	sonraki kılık
	(bu diziyi durdur)

```

###Projeni dene
__Yeşil bayrağı tıkla.__

Kuklanın kılığı değiştimi?

__Bir kaç kere daha tıkla.__
Her defasında, farklı bir kılık göründümü? Bazen aynı kılık iki kere arka arkaya görünebilir. Bu önemli değil. Kuklanın kılık değişirken titrediğini gördünmü? Bunu sonraki adımda çözeceğiz.hen FLAG clicked
Projeni kaydet.

##Adım 2: Resimlerin biçimini değiştir

__Biçimi bozulmuş bir şekilde görünen ve bir kaç  saniye sonra düzelen bir resim oluşturalım.__

Biçimin bozulma düzeyini kontrol etmek için puan verisi kullanacağız. Eğer puan yuksek ise, biçim bozukluğu da yüksek olacak, eğer puan düşük ise, bozulma oranı da az olacak. Bu puan aynı zamanda Zaman Ayarı  Kartındaki süreç ayarı gibi işler.

1. Veri grubunun altında, puan adlı değişken oluştur.
2. Kodlamayı şu şekilde yaz:


```scratch

	Bayrak tıklanınca
	gizle
	tekrarla rastgele 1 ile 5
	sonraki kılık
	(bu diziyi durdur)
	Puan 110 olsun
	tekrarla puan=0
	puanı -10 arttır
	mozaik etkisini puana ayarla
	renk etkisini puana ayarla
	göster
	1 saniye bekle
(bu diziyi durdur)

```

gizle kodunu üste ekle ve  altındaki her şeyi ve puanı 110'a ayarla 

###Projeni dene
__Yeşil bayrağı tıkla.__

Rastgele biçimi bozulmuş bir resim göründümü?
Biçim bozulmanın oranı zamanla azaldımı?
Biçim bozulmanın oranı azalırken, puan düştümü?
Puan 0 olunca, biçimi bozulmamış bir resim göründümü?
Yeşil bayrağı her tıklayışında, farkli bir resim gördünmü?
Projeni kaydet


##Deneyebilecekleriniz

__Başlangıç puanını değiştir ve zamanla ne kadar değiştığini gözlemle.__ Bu resimin tanınmasını ne şekilde etkiler, güçleştirirmi yoksa kolaylaştırırmı?

__Listeden farklı etkiler dene. __ Bunların etkisi nedir?

##Adım 3: Oyuncuların resmi tahmin etmesine izin ver ￼

Şu ana kadar  seçtiğimiz resimin ekranda yavaşca görünmesini ve zamanla düşen bir süre ölçer oluşturduk, ama oyunu nasıl kazanırız? Ekranın alt kısmına oyuncular için kuklalar ekleyelim. Eğer doğru olanın uzerine tıklarlarsa oyunu kazanırlar. Eğer yanlış olanı seçerlerse, kukla görünmez olur ve oyun devam eder.

Önce, doğru seçeneğin ne olduğunu bilmemiz gerekli. 

1. Bütün kuklalar için yeni bir veri oluştur ve veri adını ver. 
2. Doğru cevabı kayıt etmek için kodlamayı değiştir. İlk tekrarla döngüsünden sonra cevap veri setini kılığa ekle.

```scratch

bayrak tıklanınca
gizle
tekrarla rastgele 1 ile 5
          sonraki kılık
(bu diziyi durdur)
kılığa cevap ayarla
puan 110 olsun
tekrarla puan =0 olana kadar
         puanı -10 arttır
         mozaik etkisini puana ayarla
         renk etkisini puana ayarla
         göster
         1 saniye bekle
(bu diziyi durdur)

```
__Şimdi oyuncu için kuklalar ekleyelim.__

1.Ana kuklayı ikizle ve ikizini ekranın alt kısmına yerleştir. Bu kuklaya cevap 1 adını ver.
2. Cevap1'in kodlamsını ve birincisi hariç, bütün kılıklarını sil.
3. Bunu tekrarla ve cevap2 kuklasını, cevap1 kukalasının yanina koy, ikincisi hariç bütün kılıklarını sil.
4. Bunu cevap3, cevap4 ve cevap5 için tekrarla. Şimdi ekranın alt bölümünde 5 cevap kuklası farklı kılıkda sıralanmış olmalı. Bu cevap kuklalarının hiç birinde kodlama olmamalıdır.

Şimdi, kuklaların tıklandıklarında cevabın doğru ve yanlış olmasına bağlı olarak tepki göstermelerini istiyoruz.
8. Bu kodlamayı cevap 1'e ekle:

```scratch

	cevap1 tıklanınca
	eğer cevap=1
        	kazandı haberini sal
değilse
gizle
(dur eğer)
```

1.Bu kodlamayı diğer cevap kuklalarına da ekle.
2.Bu kazandı haberi gelince buna cevap vermemiz lazım. Kukla1'i seç ve şu yazılımı ekle:

```scratch

	kazandı haberi alınca
	'Aferin, sen puan aldın' de.
```

￼￼#Projeni dene
__Yeşil bayrağı tıkla.__

Oyunu denediğin zaman sahnedeki cevap monitörünü doğru cevabın verilip verilmediğini anlamak için kullanabilirsin. Bu iyi bir test yöntemidir.

Doğru cevabı tıklayınca ne oldu?
Yanlış cevabı tıklayınca ne oldu?
Yeni bir oyuna başladığın zaman yanlış cevaba ne oldu?

2 problemimiz var.Birincisi, yanlış secenekler oyun yeniden başladığı zaman tekrar görünmüyor.  İkincisi, puan doğru cevabı vermemize rağmen düşmeye devam ediyor

Bunu çözmek için şu kodu her 5 cevap kuklasına ekleyin:

```scratch

	bayrak tıklanınca
	göster
```

İkinci sorunu çözmek için, soru kuklasının, oyuncu doğru cevabı verene kadar, kodu tekrar etmesini sağlamalıyız. Bunun için, kazandı adında yeni bir veri oluştur ve oyun başladıgında 0'a, oyun kazanılınca 1'e ayarla.Bu kodlama puan 0'a ulaşana dek veya oyun-kazanma bayrağı 1 olana kadar tekrarlansın.


1. Kazandı adlı yeni bir veri oluştur.
2. Kodlamayı şu şekilde değiştir:

```scratch

	bayrak tıklanınca
	gizle
	tekrarla rastgele 1 ile 5
          sonraki kılık
	(bu diziyi durdur)
	kılığa cevap ayarla
	puan 110 olsun
	kazandı 0 olsun
	tekrarla puan =0 olana kadar veya kazandı =1
         	puanı -10 arttır
        	mozaik etkisini puana ayarla
        	renk etkisini puana ayarla
       		göster
      		1 saniye bekle
      		(bu diziyi durdur)
kazandı haberi gelince
kazandı 1 olsun
görsel etkileri temizle
aferin, sen puan aldın de

```

Projeni kaydet

__Aferin, temel oyun adımlarını tamamladın!__

Oyunu daha zevkli yapmak için şu extra hedeflere bak


##Hedef 1: Oyunu daha kolay veya zor yap

Oyunun zorluk derecesini değiştir.

* Resimlerin göerünme hızını ve puanın ne hızla düştüğünü değiştir.
* Resimin biçim bozukluğunu değiştir.
* Tahmin edilen resimleri ve daha farklı veya daha benzer yap. Cevap kılıklarını da değiştirmeyi unutma.


Projeni kaydet
￼￼￼

##Hedef 2: Resmin biçimini her oyunda değiştir

Şu an her oyun aynı bozunumu kullanmakda. Değişik renk ve mozaik etkileri kullanın.

Oyunu değiştirki, her oyun tekrarla kodunda farklı biçim etkileri kullansın.


__ipucu:__ etkiler adında yeni bir veri oluştur. Oyunun başında rastgele bir değeri olsun. Eğer kodunu tekrarla döngüsünde kullanarak uygun etkiyi uygula. Projeni kaydet.

￼￼￼￼￼
Projeni kaydet

##Hedef 3: Bir kaç seviyeli oyun oluştur

Şu anda bütün oyunlar birbirinden bağımsız. Bunu değiştirki oyun  bir kaç kere tekrar etsin. Mesela, bir oyunun 3 defa tekrarlamasını ayarlaki, oyuncu 3 resim tahmin etsin ve 300 puan alma şansi olsun.

__ipucu:__ Üç kere tekrarlanan oyunlardaki bütün puanları bi araya getirecek bir veri oluştur.  Her oyun sırası için döngü yazman gerekli.

__ipucu:__ Belki yanlış cevapların oyunun başlangıcında tekrar görünmesi için, haber sal kodlaması kullanabilirsin. Projeni kaydet.

￼￼￼￼￼
Projeni kaydet
￼￼￼

##Hedef 4: Sonraki seviyeleri daha zor yap

Oyun her defasında aynı puanımı veriyor?  Daha çabuk tahmin ettiğin zaman daha çok puan alman gerekmezmi?

__ipucu:__ Hangi seviyede olduğunu nasil bileceksin? Bunu oyunun zorluluk düzeyini ve puanını değiştirmek için nasıl kullanabilirisin?

Projeni kaydet
￼￼

##Hedef 5: Oyuncu yanlış yapana dek oyun devam etsin

Oyunu belli bir kez tekrarlamak yerine, oyuncu yanlış cevap verene kadar devam ettir.  Bu sadece oyun gittikçe zorlaşırsa ayarlanabilir.

Projeni kaydet

##Hedef 6: Oyuncunun oynama yeteneğine göre oyunu daha zor veya kolay yap

Oyunu zorlaştırmak yerine, oyuncunun düzeyine göre ayarlaya.Eğer resmi hemen tahmin ederlerse, oyunu zorlaştır.  Eğer tahmin etmede başarısızlarsa, oyunu kolaylaştır.
Bu sadece, oyuncunun değişik seferlerdeki puanını toplamazsak çalışır.

Projeni kaydet

##Hedef 7: En yüksek puanları kayıt et

En yüksek puanı kayıt et. Eğer biri daha yüksek puan alırsa, isim sor ve puanı güncelle. En yüksek puanı alan oyuncunun adını ve puanını göster.

Projeni kaydet


##￼ Hedef 8: Yanlış tahminleri ceza


Şu an yanlış tahmin edince hiç bir yaptırım yok. Oyunu değiştirki, yanlış cevap seçince, puanın düşşün.

Bu oyunu daha iyi yaptımı?


Projeni kaydet


__Aferin, oyunu tamamladın. Eğlenerek oyna!__
Oyununuzu aile ve arkadaşlarınızla, menu çubuğundaki__paylaş__ düğmesine basarak paylaşabilrisiniz.
