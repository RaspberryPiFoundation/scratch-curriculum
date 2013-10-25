Taso 2

#Kalannälkä

__Johdanto:__
Tehdään Kalannälkä-peli! Ohjaa isoa Nälkäistä Kalaa ja yritä syödä kaikki ympärillä liikkuvaa saalista.

##VAIHE 1: Luo hahmo joka vaihtaa asusteita
__Pistetään Nälkäinen Kala uimaan meressä!__

1. Aloita uusi projekti.
2. Valitse esiintymislava, valitse lavan 'Tausta'-välilehti. Tuo kirjastosta Luonto/underwater2 ja poista backdrop1.
3. Muuta Sprite1:n nimi Nälkäiseksi Kalaksi.
4. Tuo Nälkäisen Kalan asuste, Resurssit/NälkäinenKala.png ja poista olemassa olevat asusteet costume1 ja costume2. Poista kissa hahmo oikeanapsauttamalla sitä ja valitsemalla poista.
5. Varmista, että hahmo suuntaa vain vasemmalle ja oikealle napsauttamalla hahmon tiedoissa: (kuva jossa vasen/oikea-nuolet)
6. Nyt luo skripti jolla Nälkäinen Kala seuraa hiiriosoitinta meressä näin:

```scratch
	kun klikataan LIPPU
	ikuisesti
		osoita kohti hiiriosoitin
		liiku 3 askelta
	(loppu ikuisesti)
```

###Testaa projektisi
__Napsauta vihreätä lippua.__ 
Liikuta hiiriosoitinta ympäri merta. Seuraako kala osoitinta?
Mitä tapahtuu jos et liikuta osoitinta ja kala pääsee siihen kiinni? Miltä se näyttää? Miksi näin tapahtuu?

7. Saat Nälkäisen Kalan hullunkurisen vipattelun loppumaan jos käsket sen liikkumaan vain silloin, kun se ei ole liian lähellä hiiriosoitinta. 
('etäisyys kohteeseen' -lohko on 'Tuntuaisti'-paletissa).


```scratch
	kun klikataan LIPPU
	ikuisesti
		jos etäisyys kohteeseen hiiriosoitin > 10, sitten
		osoita kohti hiiriosoitin
		liiku 3 askelta
		(loppu jos)
	(loppu ikuisesti)
```


###Testaa projektisi

Tallenna projektisi

##Kokeiltavaa

Jos haluat, voit käyttää skriptissä eri numeroita. Miten tämä vaikuttaa Nälkäisen Kalan liikkumiseen? Vaihda etäisyysraja isoksi numeroksi (e.g. 100), tai pieneksi numeroksi (e.g. 1). Vaihda määrä jota kala liikkuu isoksi numeroksi (e.g. 20) tai pieneksi numeroksi (e.g. 1 tai jopa 0).


##VAIHE 2: Lisää saalista

1. Luo uusi hahmo kirjastosta Eläimet/Fish2. 
2. Käytä 'Pienennä' -työkalua (lavan yläpuolella) tehdäksesi hahmosta pienemmän.
3. Luo skripti jolla saali ui ympäriinsä. Haluamme niiden liikkuvan satunnaisesti, joten pistetään ne liikkumaan eteenpäin vähän matkaa, kääntymään satunnaisen määrän vasemmalle tai oikealle ja sitten tekemään saman uudelleen.

```scratch
	kun klikataan LIPPU
	ikuisesti
		liiku 2 askelta
		jos 'valitse satunnaisluku väliltä 0 - 1' = 0, sitten
			käänny (vastapäivää) 20 astetta
		muuten
			käänny (myötäpäivää) 20 astetta
		(loppu jos)
		pomppaa reunasta
	(loppu ikuisesti)
```

###Testaa projektisi
__Napsauta vihreätä lippua__ ja katso kun saalis uiskentelee. Uiko se odotetulla tavalla? Uiko se uskottavasti?

__Tällä hetkellä, Nälkäinen Kala ja saalis eivät vaikuta toisiinsa millään lailla. Tämä korjataan seuraavassa vaiheessa.__

Tallenna projektisi

###Kokeiltavaa

* Kokeile vaihtaa numeroita 'käänny' ja 'liiku'-lohkoissa. Kuinka ne saavat saaliin liikkumaan eri tavalla?
* Mitä 'pomppaa reunasta' -lohko tekee? Poista se ja katso, mitä tapahtuu.

##VAIHE 3: Nälkäinen Kala syö saaliin

__Nyt haluamme Nälkäisen Kalan syövän saaliin!__ Kun Nälkäinen Kala on saanut saaliin suuhunsa, kaksi asiaa pitää tapahtua:
* Nälkäisen Kalan pitäisi sulkea suunsa ja pitää "ahminta" ääntä.
* Saaliin pitää häipyä näkyvistä, sitten ilmestyä uudelleen hetken päästä.

1. Ensin, laitetaan saalis häipymään jos se koskettaa Nälkäistä Kalaa, ja ilmestymään 3 sekuntia myöhemmin. Käytä 'koskettaako'-lohkoa tarkistaaksesi, koskettaako se kalaa.

```scratch
	kun klikataan LIPPU
	ikuisesti
		liiku 2 askelta
		jos 'valitse satunnaisluku väliltä 0 - 1' = 0, sitten
			käänny (vastapäivää) 20 astetta
		muuten
			käänny (myötäpäivää) 20 astetta
		(loppu jos)
		pomppaa reunasta
		jos 'koskettaako Nälkäinen Kala?', sitten
			piilota
			odota 3 sekuntia
			näytä
		(loppu jos)
	(loppu ikuisesti)
```

###Testaa projektisi
__Kokeile peliäsi uudelleen -- huomaatko ongelmia?__ Huomaa, että saalis häipyy näkyvistä vaikka koskettaa Nälkäistä Kalaa missä tahansa kohtaa. Kala voisi myös vain odottaa 3 sekuntia ja syödä saaliin sillä sekunnilla kun se ilmestyy uudelleen -- eipä ole kovin reilu!

2. Miten voisimme varmistaa, että saalis häipyy vain jos se koskettaa Nälkäisen Kalan suuta? Voisimme käyttää 'koskettaako väriä' -lohkoa ja tarkistaa, koskettaako se kalan sinisiä hampaita. Tee tämä korvaamalla skriptisi 'koskettaako'-lohko 'koskettaako väriä' -lohkolla, napsauta lohkon väri-ruutua ja napsauta vielä kalan hampaita.

3. Seuraavaksi pistetään saalis liikkumaan ruudulla satunnaiseen pisteeseen ennen uudelleenilmestymistä käyttämällä 'mene kohtan' -lohko, ja antamalla sille satunnaiset arvot x:ksi ja y:ksi.

```scratch
	kun klikataan LIPPU
	ikuisesti
		liiku 2 askelta
		jos 'valitse satunnaisluku väliltä 0 - 1' = 0, sitten
			käänny (vastapäivää) 20 astetta
		muuten
			käänny (myötäpäivää) 20 astetta
		(loppu jos)
		pomppaa reunasta
		jos 'koskettaako väriä []?', sitten
			piilota
			odota 3 sekuntia
			mene kohtaan x:'valitse satunnaisluku väliltä -220 - 220' y:'valitse satunnaisluku väliltä -170 - 170'
			näytä
		(loppu jos)
	(loppu ikuisesti)
```
###Testaa projektisi

Koeaja peli uudelleen -- häipyykö saalis vain kun koskettaa kalan suuta? Ja ilmestyykö uudelleen satunnaisessa pisteessä eikä aina vaan siinä, mistä sitä on syöty?

4. Kalan pitää tietää, että se on syönyt jotain, jotta se voi toistaa äänen ja vaihtaa asusteensa. Teemme tämän niin, että saalis lähettää viestin syödyksi tulemisesta ennen kuin häipyy näkyvistä.

```scratch
	kun klikataan LIPPU
	ikuisesti
		liiku 2 askelta
		jos 'valitse satunnaisluku väliltä 0 - 1' = 0, sitten
			käänny (vastapäivää) 20 astetta
		muuten
			käänny (myötäpäivää) 20 astetta
		(loppu jos)
		pomppaa reunasta
		jos 'koskettaako väriä []?', sitten
			lähetä napattu
			piilota
			odota 3 sekuntia
			mene kohtaan x:'valitse satunnaisluku väliltä -220 - 220' y:'valitse satunnaisluku väliltä -170 - 170'
			näytä
		(loppu if)
	(loppu ikuisesti)
```
__Nyt haluamme kalan vastaanottavan tämän viestin ja reagoivan siihen pitämällä "ahminta" ääntä ja napsauttamalla leuat kiinni.__

5. Lisää Resurssit/SuuKiinni -asuste ja Resurssit/Ahminta Nälkäisen Kalan hahmolle.
6. Sitten, lisää Nälkäiselle Kalalle uusi skripti, joka vastaanottaa saaliin lähettämän viestin. Skriptillä pistetään kala toistamaan 'ahminta'-äänen, vaihtamaan SuuKiinni-asusteeksi, odottamaan hetken ja sitten vaihtamaan alkuperäiseen.

```scratch
	kun vastaanotan napattu
	soita ääni ahminta
	toista 2 kertaa
		vaihda asusteeksi SuuKiinni
		odota 0.5 sekuntia
		vaihda asusteeksi NälkäinenKala
	(loppu toista)
```

__Nyt Nälkäinen Kalamme on valmis syömään, täytetään meri saaliilla. Oikeanapsauta saaliin hahmoa ja valitse 'kopioi' useamman kerran.__

###Testaa projektisi
Napsauta vihreätä lippua.
Syökö Nälkäinen Kala saaliit? Syökö se yksittäisiä saaliita?

Tallenna projektisi

###Ajateltavaa
Miksi Why do we need to add the show block to the start of the prey’s script? Think about what would happen if the prey is eaten, then the game is stopped before it reappears. What would happen if the game was restarted then?

__Well done you’ve finished the basic game. There are more things you can do to your game though. Are you ready for a challenge?__


##Challenge 1: Make the prey liiku differently

At the moment, all the prey liiku in the same way. __Can you make one of them
liiku differently?__
__Hint:__ Don’t spend too long on this bit without looking at the other activities in this
project.

__Pick one of the prey to experiment on.__ If they have the same costumes, make it a different colour with the __set color effect block__. That way, you can tell it apart from the rest of the prey.

Make this prey liiku slower than the others. __Hint:__ Look at the liiku (2) askelta block.


###Testaa projektisi
Does the prey liiku slower? Does this make the game better?
If you can do that, __try to making one of fish liiku quicker than the others.__


Does the prey still liiku in a sensible way? Do these changes make the game better?
__Hint:__ If your prey swims around in circles, check the values of the pick random block in the turn block.

How about you make each of the prey behave differently, using different combinations of these changes?

Do any of these changes make the game better? Do they make the game more interesting, more fun, harder, or easier? Are any of those “better”?

Tallenna projektisi

##Challenge 2: Make the prey avoid the Nälkäinen Kala

The prey in this game are really stupid! They just swim around randomly until they’re eaten. Real fish swim away from predators. __Let’s make one of the prey swim away from the Nälkäinen Kala.__

There’s no block in Scratch that tells you the direction that another sprite is in. But you can make one sprite point towards another, then make it turn around to face away. The blocks you need are in the __Motion__ palette.

Using that idea, __make one of the prey always point away from the Nälkäinen Kala.__ You might want to make it wiggle as it swims away.

###Testaa projektisi
Does this make the fish harder to catch? Does it make the game better?

Tallenna projektisi

##Challenge 3: Add a score
It’s not enough just to eat fish. How do you know you’re better at the game than your
friends? __You need a way to keep score so lets add a score board.__ Look at the __Keep Score scratch card__ for an idea of how to do it. 

Where should you put the block that changes the score?

Make sure the score goes back to zero at the start of the game. Where should you put that block?

###Testaa projektisi
Does the score go to zero at the start of the game? Does it go up every time you eat prey?

Tallenna projektisi

##Challenge 4: Add a countdown

__Give yourself a time limit in the game.__ How many fish can you eat in thirty
seconds?

Look at the __Timer scratch card__ for how to add a timer to the game. Start with the game lasting thirty seconds.

###Testaa projektisi
Does the timer start at 30?

Does it go down at the right speed?

Can you catch prey while the timer is going?

Does the game stop when the timer reaches zero?

Tallenna projektisi

##Challenge 5: Add a bonus score
Award a large bonus score if you can eat all three fish at the same time. How can
you tell how many fish have been eaten?
__Hint:__ One way to do this __uses a variable to count how many prey are swimming around.__

Tallenna projektisi

##Challenge 6: Change the game: keep a prey alive! Sometimes, you can have great new ideas by taking an existing idea and doing the opposite.

__Modify the game so that, instead of you controlling a fish that tries to eat the others, you control one prey in a sea with lots of Nälkäinen Kala.__ How long can you last before you’re eaten?

Tallenna projektisi

__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!T
