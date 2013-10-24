Taso 2

#Hedelmäpeli

__Johdanto:__
Tässä pelissä on kolme hahmoa, joiden asusteet vaihtuvat. Pelaajan pitää pysäyttää ne silloin, kun niillä on sama kuva näkyvissä (aivan kuten hedelmäpelissä!).

##VAIHE 1: Luo hahmo jonka asusteet vaihtuu

__Tuodaan pelin eri kuvat__

1. Aloita uusi projekti. Poista kissa hahmo oikeanapsauttamalla sitä ja valitsemalla poista.
2. Tuo uusi hahmo.
3. Valitse kuva mistä tahansa. Me valitsimme Asiat/Bananas, mutta voit käyttää mitä tahansa kuvaa.
4. Napsauta Asusteet-välilehteä ja tuo 2 lisää kuvaa niin, että niitä on yhteensä kolme (me valitsimme Eläimet/beetle and Asiat/donut, mutta voit käyttää mitä tahansa kuvia).

__Nyt meillä on asusteita ja halutaan, että hahmo vaihtaa niiden välillä.__

##VAIHE 2: Pistetään kuva muuttumaan

1. Napsauta Skriptit-välilehteä.
2. Napsauta Tapahtumat ja raahaa kun klikataan lippu -lohko skriptien alueelle. Tämä laukaistaan kun napsautetaan vihreätä lippua.
3. Lisää ikuisesti niin, että liittyy edellisen lohkon pohjaan.
4. Napsauta vihreätä lippua oikealla ylhäällä. Huomaa, että skriptimme ympärille ilmestyy vaalea reunus.  Se ajetaan, koska napsautettiin vihreätä lippua, joka laukaisee tämän.
5. Nyt napsauta Ulkonäköä ja raahaa seuraava asuste
6. Kuinka hidastetaan se niin, ettei se vaihda kuvaa noin nopeasti? Napsauta Ohjausta ja raahaa odota 1 sekuntia.
7. Säädä aika kunnes se vaihtuu nopeammin (0.1s näyttää hyvältä). Mitä tapahtuisi jos odota-lohkoa ei olisi olemassa?

```scratch
	kun klikataan LIPPUA
	ikuisesti		
		seuraava asuste
		odota 0.1 sekuntia
	(loppu ikuisesti)
```

###Testaa projektisi
__Napsauta vihreätä lippua.__ 
Vaihtuuko asuste järkevällä nopeudella?

Tallena projektisi

###Kokeiltavaa

Säädä odota-lohkon aikaa. Millä numeroilla peli olisi liian helppo, tai liian vaikea?

##VAIHE 3: Pysäytä se kun sitä napsautetaan

Hienoa! Saadaan hahmo vaihtamaan asusteita ikuisesti, mutta miten saadaan se pysähtymään kun sitä napsautetaan?

1. Tee uusi muuttuja napsauttamalla tieto ja tee muuttuja. Nimeä se pysäytetyksi ja tee se kaikille hahmoille, sitten ota rasti pois sen viereisestä laatikosta, niin se ei näy esiintymislavalla.
2. Aseta pysäytetty arvoon 1 kun joku napsauttaa kuvaa käyttäen "kun tätä hahmoa klikataan".
3. Nyt pitää saada kuvan vaihtamisen pysähtymään kun muuttuja pysäytetty on yhtä kuin 1. Napsauta Ohjaus ja lisää ikuisesti silmukan sisälle jos, sitten -silmukan.  Laita jos:n ehdoksi yhtäsuuruus-vertailu, toiselle puolelle pysäytetty ja toiselle puolelle 0

###orig###
3. Now we need to make the image stop changing when the variable stopped equals 1. Click Control and change the forever loop to a forever if and use a new equals operator to check if stopped equals 0


4. Lopuksi lisää aseta pysäytetty arvoon 0 -lohko kun klikataan LIPPU -lohkon alle.


###Testaa projektisi
__Napsauta vihreätä lippua, odota hetken, sitten napsauta hahmoa.__ 

Vaihtuuko asuste ennen kuin napsautat sitä?
Pysähtyykö kun napsautat sitä?

__Käynnistä hahmo uudelleen.__ Pysähtyykö se kun siirrät hiiriosoittimen sen päälle, napsauttamatta? 
Pysähtyykö hahmo kun napsautat jossain muualla esiintymislavalla? Jossain muualla Scratch-ikkunassa? Jossain muualla Scratch-ikkunan ulkopuolella?

Tallena projektisi

##VAIHE 4: Toisten hahmojen luonti
__Nyt meidän pitää luoda muut hahmot, jotta voimme pelata pelimme!__

1. Kopioi hahmo oikeanapsautamalla sitä ja valitsemalla kopioi.
2. Kopioi se vielä kerran niin, että ruudulla on yhteensä kolme hahmoa.
3. Liikuta jokainen hahmo niin, että ne ovat suorassa rivissä. Pienennä ne hieman jos on tarvetta.

###Testaa projektisi
__Napsauta vihreätä lippua.__ Kaikkien hahmojen kuuluisi vaihtaa asusteensaAll the sprites should change. Try to stop them all on the same picture!

Tallena projektisi

###Kokeiltavaa

When you start the game just after you’ve loaded it, all the sprites show the same costume and change in unison. How about you make the sprites change to a random costume when the green flag is clicked?
Hint: try picking a random costume for each sprite when the game is started.

__Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at these Haastes!__


##Haaste 1: Make the game harder

Change the difficulty of the game somehow. Just making the costumes change quicker is easy. Try and do something more imaginative. Some ideas you might like to try:

1. Change the number of costumes each sprite has.
2. Make some sprites have unique costumes.
3. Have different times between costume changes.
4. Have each sprite move to a random costume rather than the next one. 

__Have fun coming up with your own things!__

Every time you make a change, think about whether it make the game easier or harder. Is the game too easy or too hard? How can you adjust the difficulty so it’s just right?


##Haaste 2: Make the game get harder and easier over time

Different people will have different skills at playing the game. __How could you make the game adjust its difficulty depending on the player?__

One way you could do it is to __adjust the speed the costumes change at__. You can use a variable, called __delay__, to give the duration of each sprite’s wait block. If the player wins the round, the delay can be reduced a little (to make the game harder). If the player loses the round, the delay can be increased a little (to make the game easier).

##Haaste 3: Detect when all the sprites have stopped on the same costume

__The aim of the game is click on the sprites so they’re stopped while showing the same costume. It would be nice if the stage detected when you’d finished playing and then told you if you had won or lost by checking to see if each sprite had the same costume.__

First, the stage needs to know when the player has finished. We can do this by having the stage check to see if all sprites have stopped moving when we click on one of them. Go back and modify each of the sprite# clicked blocks to broadcast a new message, checkForEnd

The Stage can respond to this message and check if the game is over by seeing if all three sprites’ stopped variables are set to 1, by using the x position of Sprite block for each sprite, and changing “x position” to stopped If all three sprites have a stopped value of 1, we know the game is over and we can check to see if the player has won.

To do this, we can use the same x position of Sprite block, but instead of looking at the stopped variable, we can look at the costume # and see if Sprite1 has the same costume as Sprite2, and if Sprite2 has the same costume as Sprite3.

To do this, you’ll need an if block to check each stopped variable, and inside that an if... else block to see if the player has won or lost by comparing each
costume #.

From this point on, you could announce the result of the game using a broadcast and respond to this with another sprite. Maybe get Felix back to congratulate or commiserate the player?


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
