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

##STEP 2: Resim değiştirmek

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

###Test Your Project
__Click the green flag.__ 
Do the costumes change at a sensible rate?

Save your project

###Things to try

Adjust the time in the wait block.What numbers do you think would make the game too easy, or too hard?

##￼STEP 3:Üzerine basıldığında durdurmak

Great! We can make the sprite change costumes forever, but how do we make it stop when we click on it?

1. Create a new variable by clicking Variables and Make a variable. Call it stopped and make it for all sprites, then uncheck the box next to it so it doesn’t display on the stage.
2. Set stopped to 1 when someone clicks on the image using
when sprite1clicked and set stopped to 0 making sure to change the value from 0 to 1.
3. Now we need to make the image stop changing when the variable stopped equals 1. Click Control and change the forever loop to a forever if and use a new equals operator to check if stopped equals 0
4. Finally, add a set sprite1stopped to 0 underneath the when flag clicked

###Test Your Project
__Click the green flag, wait for a moment, then click on the sprite.__ 

Does it change costume before you click on it? 
Does it stop when you do click on it?
__Start the sprite again.__ Does it stop when you put the mouse pointer on it, without clicking? Does the sprite stop when you click somewhere else on the Stage? Somewhere else in the Scratch window? Somewhere outside the Scratch window?

Save your project

##Step 4: Diğer kuklaları oluşturmak
__Now we need to make the other sprites so we can play our game!__

1. Duplicate the sprite (Sprite1) by right clicking on it in the bottom right corner.
2. Duplicate it again so there are 3 sprites on the screen.
3. Move each sprite so they are in a line. Make them a bit smaller with if you need to.

###Test Your Project
__Click the green flag.__ All the sprites should change. Try to stop them all on the same picture!

Save your project

###Things to try

When you start the game just after you’ve loaded it, all the sprites show the same costume and change in unison. How about you make the sprites change to a random costume when the green flag is clicked?
Hint: try picking a random costume for each sprite when the game is started.

__Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at these challenges!__


##Challenge 1: Make the game harder

Change the difficulty of the game somehow. Just making the costumes change quicker is easy. Try and do something more imaginative. Some ideas you might like to try:

1. Change the number of costumes each sprite has.
2. Make some sprites have unique costumes.
3. Have different times between costume changes.
4. Have each sprite move to a random costume rather than the next one. 

__Have fun coming up with your own things!__

Every time you make a change, think about whether it make the game easier or harder. Is the game too easy or too hard? How can you adjust the difficulty so it’s just right?


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
