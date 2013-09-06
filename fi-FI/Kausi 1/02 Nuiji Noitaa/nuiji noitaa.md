Taso 1

#Nuiji Noitaa

__Johdanto:__
Tämä projekti on kuin peli __Mätki myyrää__. Saat pisteitä kun lyöt ruudulla ilmestyviä noitia. Tavoite on saada mahdollisimman monta pistettä 30 sekunnissa!

##VAIHE 1: Luo lentävä noita

1. Aloita uusi projekti.
2. Poista kissa hahmo ja korvaa tausta Luonto/woods-taustalla.
3. Käytä "uusi tausta kirjastosta"-ikoni ja lisää uusi noita hahmo projektille (käytä Fantasia/Witch-hahmo). 

Nyt halutaan saada noita liikkumaan

4. Lisää muuttuja vain tälle hahmolle ja nimeä se nopeudeksi.
Esiintymislavalla, tämän muuttujan tilaindikaattorissa pitää lukea "Witch: nopeus".
Jos siinä lukee pelkkä "nopeus", poista muuttuja ja luo se uudestaan, vain tälle hahmolle.  Muuttuja-paletissa ota puumerkki pois "nopeus" muuttujan edestä, jotta sitä ei näytetä esiintymislavalla.
Nopeus-muuttuja määrää kuinka nopeasti noita liikkuu. Käytetään muuttujaa, jotta voidaan muuttaa noidan nopeuden sitä mukaan kun peli jatkuu.
5. Halutaan noidan alkavan liikkumista kun peli käynnistyy, joten tee tällainen skripti:

```scratch

	kun klikataan LIPPU
	aseta nopeus arvoon 5
	ikuisesti
		liiku nopeus askelta
	(loppu ikuisesti)
```
		
###Testaa projektisi
__Napsauta vihreä lippu__ ja katso miten noitasi käyttäytyy. Miksi hän jää jumiin ruudun reunaan?

6. Jotta noita ei jäisi jumiin, meidän pitää saada hänet liikkumaan toiseen suuntaan kun hän koskettaa ruudun reunaa.  "liiku nopeus askelta"-lohkon alle lisää "pomppaa reunasta"-lohko

```scratch

	kun klikataan LIPPU
	aseta nopeus arvoon 5
	ikuisesti
		liiku nopeus askelta
		pomppaa reunasta
	(end ikuisesti)
```
7. Jotta noita ei lentäisi ylösalaisin, napsauta  __suunta vain vasemmalle-oikealle -näppäintä__ hahmon yleisasetukset -alueella

###Testaa projektisi
__Napsauta vihreä lippu.__ 
Liikkuuko noita ruudulla reunasta toiseen?

Tallenna projektisi

###Kokeiltavaa
__Kokeile vaihtaa nopeus muuttujan arvoa niin, että noita lentää nopeammin tai hitaamin.__

__Miten saisit noita lentämään nopeammin, sitä kauemmin hän lentää?__
(Tämä on melko kinkkinen, joten älä murehdi jos et keksi miten se voisi tehdä.  Saat lisää vinkkejä edetessäsi projektin kanssa.)

##VAIHE 2: Pistä noita ilmestymään ja hävimään satunnaisesti

Jotta peli olisi hauskempi, halutaan noidan ilmestyvän ja häviävän satunnaisesti.  Tämä tehdään toisella skriptillä joka pyöriin samaan aikaisesti sen kanssa, joka liikuttaa noitaa.  Tämä uusi skripti piilottaa noidan satunnaisen ajan, näyttää satunnaisen ajan, ja toistaa tämän ikuisesti (tai kunnes peli loppuu).

Luo tällainen skripti noidalle:

```scratch

	kun klikataan LIPPU
	ikuisesti
		piilota
		odota valitse satunnaisluku väliltä 2 - 5 sekuntia
		näytä
		odota valitse satunnaisluku väliltä 3 - 5 sekuntia
	(end ikuisesti)
```
###Testaa projektisi
__Napsauta vihreä lippu.__ 
Liikkuuko noita ruudun reunasta toiseen ilmestyen ja häipyen satunnaisesti?

Tallenna projektisi

###Kokeiltavaa
__Kokeile vaihtaa satunnaislukujen skaala. Mitä tapahtuu jos valitset hyvin isoja numeroita tai hyvin pieniä numeroita?__
(Saitko tästä lisää vinkkiä kuinka saisit noita lentämään nopeammin, sitä kauemmin peli pelataan?)

##VAIHE 3: Noita häipyy näkyvästä kun se napsautetaan

Jotta tästä tulisi peli, meidän pitää antaa pelaajalle jotain tekemistä.  Pelaajan pitää napsauttaa noitaa ja saada tämä häipymään näkyvästä.  Kun noita napsautetaan, haluamme hänen häipyvän näkyvästä ja soittavan äänen.

1. Äänet välilehdessä Valitse uusi ääni kirjastosta: Sähköinen/fairydust. 

2. Lisää tämä skripti noidalle:

```scratch

	kun tämä hahmo napsautetaan

	piilota

	soita ääni fairydust
```
###Testaa projektisi
__Napsauta vihreä lippu.__ 

Häipyykö noita näkymästä ja soittaako äänen kun se napsautetaan?

Tallenna projektisi

##VAIHE 4: Lisää pisteet ja ajastin

Meillä on noita, mutta nyt haluamme tehdä pelin! Haluamme We want to score points every time we click on the witch but we also want to have a time limit on the game. We can use a variable for the score and the timer.


1. Create a new Variable for all sprites called score, and alter the script for the witch to increase this variable by one when she is clicked.

```scratch

	when sprite1 clicked

	hide

	play sound Fairydust

	change score by 1
```
2. Switch to the Stage and create a new variable (this time just for the stage) called timer. Add a new script that occurs when the green flag is clicked to set timer to 30 and reset the score to 0. Then use a repeat until block to wait a second and then reduce timer by
one. This should repeat until timer is 0, at which point use stop all to stop the game.

```scratch

	kun klikataan LIPPU

	set timer to 30

	set score to 0

	repeat until timer = 0

		wait 1 secs

		change timer by -1

	(end repeat)

	stop all
```


###Testaa projektisi
__Napsauta vihreä lippu.__ 

Tallenna projektisi

###Things to try
__How might you make the witch speed up as the game goes on?__


__Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at this challenge!__

##Challenge: add more witches

If one witch is good, more must be better! Let’s have three witches flying around.
1. Duplicate the witch by right-clicking it in the sprite list.
2. For each witch adjust the size of the sprite so the witches are different sizes.
3. For each witch change the speed variable so that they fly at different speeds.
4. Move the witches around the canvas so that they are not all together.

###Testaa projektisi
__Napsauta vihreä lippu.__ 

Do you have three witches that move from side to side across the screen, randomly appear and disappear, and disappear when you click on them?

Tallenna projektisi

###Things to try
1. How many witches is a good number for the game?
2. Can you make the witches look different? You could either edit their costumes, or use some blocks from the Looks palette to change them.
3. Can you make the witches be worth different points? How about making the fastest (and smallest) witch worth 10 points?


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
