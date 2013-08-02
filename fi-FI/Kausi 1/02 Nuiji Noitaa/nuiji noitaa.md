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
Jos siinä lukee pelkkä "nopeus", poista muuttuja ja luo se uudestaan, vain tälle hahmolle.  Muutuja-paletissa ota puumerkki pois "nopeus" muuttujan edestä, jotta sitä ei näytetä esiintymislavalla.
Nopeus-muuttuja määrää kuinka nopeasti noita liikkuu. Käytetään muuttujaa, jotta voidaan muuttaa noidan nopeuden sitä mukaan kun peli jatkuu.
5. Halutaan noidan alkavan liikkumista kun peli käynnistii, joten tee tällainen skripti:

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
7. Jotta noita ei lentäisi ylösalaisin, napsauta  __suunta vain vasemmalle-oikealle -näppäintä__ hahmo yleisasetukset -alueella

###Testaa projektisi
__Napsauta vihreä lippu.__ 
Liikkuuko noita ruudulla reunasta toiseen?

Tallenna projektisi

###Things to try
__Try changing the value of the speed variable to make her fly faster or slower.__

__How would you make the witch get faster the longer she flies?__
(This is a tricky one, so don’t worry if you can’t see how to do it. You’ll get more clues as you work through the project.)

##VAIHE 2: Make the witch appear & vanish randomly

To make the game more fun, we want the witch to appear and vanish randomly. We’ll do that with another script that runs at the same time as the one that moves the witch. This new script needs to hide the witch for a random time, then show her for a random time, and repeat that ikuisesti (or until the game finishes).

Create this script for the witch:

```scratch

	kun klikataan LIPPU

	ikuisesti

		hide

		wait pick random 2 to 5 secs

		show

		wait pick random 3 to 5 secs

	(end ikuisesti)
```
###Testaa projektisi
__Napsauta vihreä lippu.__ 
Does the witch move from side to side across the screen and vanish and appear again randomly?

Tallenna projektisi

###Things to try
__Try changing the range of the random numbers. What happens if you pick very big numbers or very small numbers?__
(Does this give you any more clues for how to make the witch speed up the longer the game is played?)

##VAIHE 3: Make the witch disappear when she’s clicked

To turn this into a game, we need to give the player something to do. They need to click on the witch to make her disappear. When the witch is clicked, we want her to disappear and play a sound.

1. In the Sounds tab, import the sound electronic/fairydust. 

2. Add this script to the witch:

```scratch

	when sprite1 clicked

	hide

	play sound Fairydust
```
###Testaa projektisi
__Napsauta vihreä lippu.__ 

Does the witch disappear and play the sound when you click it?

Tallenna projektisi

##Step 4: Add a score and timer

We’ve got a witch, but now we want to make a game! We want to score points every time we click on the witch but we also want to have a time limit on the game. We can use a variable for the score and the timer.


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
