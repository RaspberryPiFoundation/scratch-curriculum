Düzey 3

#Boya kutusu

__Tanıtım:__
Bu proje, basit bir boyama aleti oluşturur. Bilgisayar faresini hareket ettirirdiğin zaman çizgi çizer. Çizginin rengini değiştirip, ekranı temizliyebilirsin.

##Adım 1: çek ve çiz 

Kodlamaya, kalemi sahnede hareket ettirdiğimizde çizmesini yazarak başlayacağız
1. Yeni Scratch projesine başla. Kedi kuklasına sağ tıkla ve sil
2. Sahneyi tıkla ve dekor dosyasından indoors/chalkboard dekorunu aktar.
3. Kaynaklar/greenpencil kullanarak kalem adlı kuklayı ekle.
4. Kılıklar tabını seç ve resim editör  kullanarak, resimin merkezini değiştir.
5. Hep sürekli ve 'ye doğru dön kodlarını kullanarak kalemin, bilgisayar faresini ekranda izlemesini ayarla


```scratch
Bayrak tıklanınca
sürekli tekrarla
	fare okuna doğru dön
(hepsini durdur)
```
__Şimdi, bu kalem kuklasını gerçek bir kalem olarak kullanmak istiyoruz. Kalem aşağı ve kalem yukarı kodlarina bak..__ 
6. Bilgisayar faresini aşağı bastığımız zaman kalemin de aşağıya inmesini, serbest bırakınca yukarıya çıkmasını istiyoruz. Bunu eğer... Bunu eğer... ise ve fare basılınca kodları ile yapabiliriz.

```scratch
Bayrak tıklanınca
sürekli tekrarla
	fare okuna doğru dön
	eğer fareye basılı(mı)
	kalemi bastır
	değilse
	kalemi kaldır
	(dur eğer)
(hepsini durdur)
```
##Projeni dene
__Yeşil bayrağı tıkla.__
Kalem, fareyi ekranda takip ediyor mu?Fareye basıp, hareket ettirince ne oldu?

7. Ekran karalamalarla dolunca, sil kodlamsını kullanarak sil.

```scratch

Bayrak tıklanınca
sürekli tekrarla
	fare okuna doğru dön
	eğer fareye basılı(mı)
	kalemi bastır
	(dur eğer)
(hepsini durdur)
```

##Projeni dene
__Yeşil bayrağı tıkla.__

Çizimin, yeşil bayrağı tıklayınca kayboldu mu?

PROJENI KAYDET

##Adım 2: silmek

Projeyi kapatıp yeniden başlamak yerine, ekrandaki karalamayı silecek bir düğme ekleyelim.

1. Resources/cancel button kuklasını aktar
2. Kuklanın adını sil olarak değiştir.
3. Kuklayı sahnenin alt kısmında sola yerleştir.
4. Sil kuklasına bu kodlamayı ekle:

```scratch
Temizle tıklanınca
temizle
```

##Projeni dene
__Yeşil bayarağı tıkla.__

Sil düğmesi bütün karalamayı sildi mi?

Projeni dene

##Adım 3: renk değiştirmek

Şu ana kadar sadece mavi çizgi çizdik. Şimdi diğer renkleri kullanalım. Değişik renkde kuklalar ekleyelim. Renli düğmelere-kuklalara tıklayınca çizginin rengi değişecek.

1. Resources/red-selector kılığını kullanarak kırmızı adında kukla oluştur.
2. Bunu ekranın alt kısmına, sil düğmesinin yakınına koy
3. Kırmızı kuklası tıklanınca, kırmızı haberini salsın


```scratch
Kırmızı tıklanınca
kırmızı haberini sal
```
__Evet, yaptığı budur. Kalemin zor işi budur.__

Resources/red-pencil dosyasından yeni kılık aktar. Kılığın  merkezini kalemin ucu olarak ayarla

4.Kaleme yeni kod ekle. Kalem kırmızı haberini alınca, kırmızı kalem kılığına girsin.


```scratch
kırmızı haberini alınca
kırmızı kalem kılığına gir
kalem rengi kırmızı olsun

```

##Projeni dene
__Yeşil bayrağı tıkla.__

Çizgi çiz. Kırmızı kuklayı seç ve çizmeye devam et. Kalem kılık değiştirdi mi? Kırmızı çizmedi mi? Kalemin ucu ile çizebiliyor musun?

Projeni kaydet

5. Aynı yazılımı mavi, sarı ve yeşil kuklalar için tekrarla.

##Projeni dene
__Yeşil bayrağı tıkla.__

Bütün renk düğmeleri çalıştımı? Kalemler doğru renklerde çizdiler mi? Kalemler uç kısımlarını kullanarakmı çizdiler?

Projeni kaydet

##Adım 4: Sınırların içerisinde çizmek 

Çerçeveye çizilmesini istemiyoruz. Sadece ekranın ortasına çizilebilmesi için, kalemin açık gri olan bölge dışına çıkmasını engellememiz lazım.

Çizim bölgesi 230 ve -230 x noktasında ve 170 ile -170 y noktasındadır.Bu değerleri eğer kodunu kullanarak ayarlayabiliriz.

Bunun için, git kodunun etrafına, eğer kodu ekle. Eğer kodunun içerisine su kodu yaz:
Fare y> -120 ve fare y< 170
Fare x >-230 ve fare x <230

Bu yazılım için  bir kaç tane İşlemler kodlarını kullanmamız lazım.

Çizim bölgesi dışına çizemiyeğimiz için, kalemi her bıraktığmızda görünmez yapalim.
Bunun için, eğer kodunu eğer ise ile değiştir. 


```scratch
Sürekli tekrarla 
eğer fare y>-120 ve fare y <170 ve fare x>-230 ve fare x<230
Fare okuna doğru dön

```

Çizim alanı dışına çizemediğimiz için, kalemi kullanmadığımız zaman gizleyebiliriz. Bunun için, eğer kodunu, eğer ise ile değiştirin.  Eğer için koşulları aynı bırak, eğer doğru ise kalemi göster, değilse gizle.

```scratch
Bayrak tıklanınca
kalemi kaldır
temizle
sürekli tekrarla
	eğer fare y>-120 ve fare y <170 ve fare x>-230 ve fare x<230
		Fare okuna doğru dön
		göster
		fareye basılı mı
			kalemi bastır
		değilse
			kalemi kaldır
		(dur eğer)
	değilse
		gizle
	(dur eğer)
(sürekli durdur)
```

##Projeni dene

__Yeşil bayrağı tıkla.__


Çizim alanının içerisine ve dışına çizebiliyor musun?

Projeni kaydet

##Adım 5: Temizleme

__Çizgi çizmek çok iyi, ama bazen hata yaptığın zaman onu silebilmen lazım. Bunu yeni bir kalem aleti ile yapabilirizi. Bu alet dekor ile aynı renkde, gri renginde çizer.


1. İstediğin bir resimi yeni kukla olarak ekle. Küçült ve ekranin alt noktasına kaydır. Bu kukla tıklanınca, damga haberi salması lazım.
2. Bu kalem kuklası için damga düğmesi gibi yeni bir kılık ekle.
3. Kalem kuklasını seç ve bu sadece bu kukla için kalem kodu denilen bir değişken ekle. Bunu çizgi çizdiğimizi ya da damgalama yaptığımızı algılamak için kullanacağız.
4.Damga haberine karşılık vermek için yeni bir yazılım ekle. Bunun kılığı damga olarak  ve kaem modu değişkeninide yanlış olarak ayarlaması gerekli.
5. Diğer alet haberlerini ( kırmızı, yeşil, mavi ve temizleme) için de yazılımı değiştir ki kalem modu verisi doğru'ya ayarlansın.


Resources/eraser dosyasından sahneye yeni düğme-kukla aktar. Küçültki, sahneye uygun ebatda olsun. Diğer dügmelerle aynı şekilde çalışsın, tek farkı temizleme haberi salması.

Kalem kuklası, temizleme haberine, renk değiştirip gri olarak karşılık vermeli. Ayrıca, temizleme aletlerini temsil eden yeni bir kılığa ihtiyacı olacak. Bunun için resources/eraser kılığını kullanın. Kılığı sahnenin merkezine yerleştirmeyi unutmayın.
##Projeni dene
__Yeşil bayrağı tıkla.__

Temizleme aleti çizgileri sildi mi? Kenarlara kadar çalıştı mı? Temizleme aletinden kalem aletlerine değiştirebiliyor musun?

Projeni kaydet

##Adım 6: damga 

Bu adımda, resime küçük resimler damgalayacak bir damga aleti eklemen gerekli.

Etkinlik kontrol listesi
eğer düğme basıldığında biz çizim veya damga yapmamız gerektiğini algılıyormuyuz?
Eğer kalem modu =doğru, biz tıklanan kalemi , değilse damgayı kullanmalıyız.

##Projeni dene 
__Yeşil bayrağı tıkla.__
￼￼
Temizleme aleti doğru calıştımı?

Bundan diğer kalem aletine değiştirdiğin zaman ne oldu?

Projeni kaydet
￼
__Aferin, bu oyun için gerekli olan temel adımları tamamladın.

Extra Hedefler!__
￼￼￼
##Hedef 1: Gökkuşağı renginde kalem

Gökkuşağı renklerinde çizen bir kalem ekleyelim. Bunu normalde kalemlerle yapabilirisin, bilgisayarda nasıl yapılacağını öğrenmek zevkli olur. Bunun için kalemin rengini blok kodlama ile değiştirmen lazım.

İlk olarak, gökkuşağı aleti kuklasını ve kılığını kalem kuklasına ekle.

1. Yeni alet kuklası yap ve sahnenin alt noktasına diğer kalem aletlerinin yanına yerleştir. Resources/rainbow-selector kılığını kullanarak gökkuşağı haberini sal.
2. Resources/rainbow-pencil kılığını kalem kuklasına ekle. Kalemin rengini 1 saniyede bir çok kere değiştirecek bir kodlama yazmalısın( ben her 0.05 saniyede 5 defa değiştirmenin uygun olduğunu düşünüyorum ama siz farklı değerleri deneyebilirsiniz.  Zaman ayarı kartı bunun nasıl yapıldığını gösterir. Kalemin rengini  zamanla -1 ile değiştir yerine 5 ile değiştir blokunu kullan.

Kalemin renginin sadece seçtiğin zaman değişmesi için bunu kontrol etmen lazim, yoksa bütün kalemler gökkuşağı gibi yazar! Bunun için gökkuşağı-değiş adlı bir veri oluştur ve gökkuşağı etkisi oluşturmak istediğinde doğru değerini ver, yoksa yanlış değerini ver. Kalem her aletin verdiği habere, bu değişkene göre cevap versin.
Damga adımında öğrendiklerini gökkuşağı etkisi oluşturmak için kullan. Aletlerin haberine iki değişken kullanarak cevap verebilirsin: kalem mode ve gökkuşağı-değiş.

##Projeni dene
__Yeşil bayrağı tıkla.__

Gökkuşağı aleti doğru çalışıyormu?
Normal kalem aletine geri döndüğünde ne oldu?


Projeni kaydet

##￼Hedef 2: Klavye kısayollarıı

Alet kuklaları yerine, klavye kısayollarını kullanabiliriz. Mesela, boşluk tuşu basılınca, klavyeye cevap vermeyi durdurur. Her kullanmak istediğin tuş için yeni bir .. tuşu basılınca kodu kullanman lazım. Bu kodları shaneye ekle.

Ben bu klavye kısayollarını kullandım:

Hepsini temizle- a
Temizleyici- e
Kırmızı kalem-r
Mavi kalem-b
Sarı kalem-y
Yeşil kalem-g
Gökkuşağı kalem-w 
Damga-s


##Projeni dene
__Yeşil bayrağı tıkla.__

￼Klavye kısayolları doğru çalıştımı?
Seçtiğin aletler bastığın klavye kısayollarına göre çalıştımı?

Projeni kaydet

##Hedef 3: Büyük ve küçük
ABir cok resim çizme programlarında büyütme ve küçültme işlemi vardır. Bunu bizim programa ekleyelim. Sorun şu ki bazen kuklanın bazen de kuklanın kılığının ebatını değiştirmemiz gerekli.

Iki tane yeni alet kuklası oluştur, birine büyük diğerine küçük adını ver. Resources/bigger-selector ve resources/smaller-selector adlı kılıklarını ekle, bunlar büyük ve küçük haberlerini salsınlar.

Kalem kuklası bu habere ya ebatını 1 olarak değiştirerek veya kılığının ölçütünü 10 ile değiştirerek cevap verebilir. Büyük ve küçük işlemleri için klavye kısayollarını kullanamayı unutma. Ben aşağı ve yukarı tuşlarını kullandım.


Projeni kaydet

Damganın ölçütünü değiştirdiğin zaman, kalemin ekrandaki ölçütününde değiştiğini fark ettinmi?
Bunun olmaması için, ölçütü her kalem kuklasını seçtiğinde %100 'e ayarla.

Daha da iyi sonuç alabilmek için, damganın tıklanınca, kalemi seçmeden once ne büyüklükde olduğunu hatırlayıp, o ebata dönmesini ayarla.  Bunun için damga-ölçütü denilen bir değişken oluştur. Bu veri damganın ölçütü her değiştiğinde, değişsin. Böylece damga aleti seçilince, ölçutünü bu değişkene göre ayarlayabilir.

##Projeni dene
__Yeşil bayrağı tıkla.__

Ölçüt kontrolları kalem kuklaları için çalışıyor mu?

Damga aletini seçip, ebatını değiştirip, geri kalem aletine dönünce ne oldu?

Projeni kaydet


__Aferin, oyunu tamamladın. Eğlenerek oyna!__

Oyununuzu aile ve arkadaşlarınızla, menu çubuğundaki__paylaş__ düğmesine basarak paylaşabilrisiniz.
