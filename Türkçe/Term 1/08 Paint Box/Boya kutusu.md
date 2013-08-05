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

Since we can’t draw outside of the drawing area, we could hide the pencil tool whenever we leave it. To do this, replace the __if__ with an __if else__ block. Keep the same condition for the __if__, and __show__ the pencil if it’s true, otherwise hide it.

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

##Adım 5: silgi

__￼￼￼￼Drawing lines is great, but there are times when you’ve made a mistake and you want to rub it out.__ We can do that with a new pencil tool that draws in grey (the same colour as the background).

Add a new button-sprite to the Stage to select the eraser. Use the __resources/eraser__ costume for it, making it smaller to fit at the bottom of the Stage. It should work the same as the other colour-selection buttons, sending an eraser message.

The pencil sprite should respond to the eraser message by switching the pen colour to grey (remember you can use the __picker__ to select the colour of the background). It will also need a new costume to represent the eraser tools: use the same __resources/eraser__ costume. __Remember to reset the costume’s centre.__

##Test Your Project
__Click on the green flag.__

Does the eraser rub out lines? Does it work right up to the edges? Can you switch between eraser and pencil tools?

SAVE YOUR PROJECT

##Adım 6: damga 

The next thing to add is a stamp tool, to stamp small pictures on the drawing.
Activity Checklist

1. Add a new sprite, using whichever image or costume you want. Shrink the sprite down and place it at the bottom of the screen alongside the other tools. When this sprite is clicked, it should __broadcast stamp__
2. Add a new costume for this pencil sprite, the same as the one you chose for the __stamp__ button.
3. Select the pencil sprite and create a new variable __pencil mode__ for this sprite only. We’ll use this variable to keep track of whether or not we are drawing or stamping.
4. Add a new script to respond to the stamp message. It needs to set the costume to the stamp and set the __pencil mode__ variable to __false__.
5. Change the other scripts that respond to tool-selection messages (red, green, blue, and eraser) so that they each set the __pencil mode__ to __true__.
6. Finally, lets check this variable __when the mouse button is down__ to see if we should be drawing or stamping. If pencil mode = true we should use the existing __pen down__, if not we should stamp instead. 

##￼￼￼￼￼￼￼￼￼￼￼Test Your Project
__Click on the green flag.__
￼￼
Does the stamp tool work correctly?

What happens when you switch back to one of the normal pencil tools?

SAVE YOUR PROJECT
￼
__Well done, you have completed the basic steps for this project.
Extra Hedefler!__
￼￼￼
##Hedef 1: Gökkuşağı renginde kalem

Let’s add a special pencil that paints in rainbow colours. It’s something that you can’t do with ordinary pens and pencils, so it’s nice to show off how drawing on a computer allows you do to different things. The secret to making it work is the change pen colour by block.

First, add the rainbow tool selection sprite and the rainbow tool costume to the pencil sprite:

1. Create a new tool selection sprite and place it at the bottom of the stage, alongside all the other pencil colour sprites. Use the resources/rainbow-selector costume and have it broadcast rainbow when clicked.
2. Add the resources/rainbow-pencil costume to the pencil sprite.

You need to build a script that will change the pen colour many times a second to give the rainbow effect (I found that changing it by 5 every 0.05 seconds works well, but you should try out different values). The timer Scratch card shows how you can make something change every so often. Use a change pen colour by 5 block instead of a change timer by -1 block inside the loop.

You also need to control that loop so that it only changes the pen colour when you’ve selected the rainbow pencil, otherwise all the pencils will have a rainbow effect! You can do this in a very similar way to how the pencil sprite changes between pencil and stamp modes. You need to create a variable called rainbowChange that has the value true when you want the rainbow effect and false otherwise. Every time the pencil responds to a tool-selection message, it should set the value of rainbowChange accordingly.

Use what you learnt from the stamp step above to control the rainbow effect. The scripts that respond to the tool-selection messages will set two variables each: pencilMode and rainbowChange.

##Test Your Project
__Click on the green flag.__

Does the rainbow tool work correctly?

What happens when you switch back to one of the normal pencil tools?

SAVE YOUR PROJECT

##￼Hedef 2: Klavye kısayollarıı

Rather than using the tool-selection sprites at the bottom of the stage, you can use the keyboard to select the different tools.
You can use the when [] key pressed blocks to respond to the keyboard. For each key you want to use, you’ll need another when [] key pressed block, which sends the same message as the respective tool-selection sprite does when its clicked. Add these scripts to the stage.

I used these shortcuts:
* Clear all - a
* Eraser - e
* Red pencil -r 
* Blue pencil - b
* Yellow pencil - y
* Green pencil - g
* Rainbow pencil - w
￼￼￼* Stamp - s

##Test Your Project
__Click on the green flag.__

￼￼Do all the tools get selected with the correct keyboard shortcuts? Does each of the tools work correctly when you select it with keyboard? Are the correct tools still selected with the tool-selection sprites on the stage?

SAVE YOUR PROJECT

##Hedef 3: Büyük ve küçük
Another feature that most drawing packages have is the ability to change the
size of the pencil. Let’s add that.
There’s one complication, though, which is that sometimes the resizing needs to change the pen size and sometimes it needs to change the pencil sprite’s costume size. It depends on whether you’re using a pencil or a stamp.

Create two new tool-selection sprites, called bigger and smaller. They should have the resources/bigger-selector and resources/smaller-selector costumes and should send the bigger and smaller messages.

The pencil sprite can respond to the messages by changing either the pen size by 1 or the costume size by 10, depending on the value of pencil mode (use an if-else block, similar to how the sprite chooses between putting the pen down or stamping)
Don’t forget the keyboard shortcuts for the bigger and smaller tools. I used the up and down arrows.

SAVE YOUR PROJECT

What you should have noticed is that changing the size of the stamp also changes the size of the pencil on-screen when you change to that tool.
To stop that, you need to set the size to 100% every time you change to a pencil tool. so that the tools look the right size.

To make it even better, have the stamp remember what size it was before you selected the pencil and go back to that size when you select the stamp tool again. The easiest way to do that is to create a new variable called stampSize, that is updated with the current size every time the stamp is resized. When the stamp tool is selected, it can set its size from the contents of this variable.
￼￼￼￼￼￼￼￼
￼
##￼Test Your Project
__Click on the green flag.__

Do the size controls work for the pencils?

What happens if you switch to the stamp, change the size and then switch back to a pencil?

SAVE YOUR PROJECT


￼￼￼￼￼￼￼__Well done you’ve finished, now you can enjoy the game!__


Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
