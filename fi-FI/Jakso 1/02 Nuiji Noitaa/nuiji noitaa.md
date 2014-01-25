Taso 1

#Nuiji Noitaa

__Johdanto:__
Tämä projekti on kuin peli __Mätki myyrää__. Saat pisteitä kun lyöt ruudulla ilmestyviä noitia. Tavoite on saada mahdollisimman monta pistettä 30 sekunnissa!

##VAIHE 1: Luo lentävä noita

1. Aloita uusi projekti.
2. Poista kissa hahmo ja korvaa tausta Luonto/woods-taustalla.
3. Käytä "Valitse hahmo kirjastosta"-ikoni ja lisää uusi noita hahmo projektille (käytä Fantasia/Witch-hahmo). 

Nyt halutaan saada noita liikkumaan

4. Lisää muuttuja vain tälle hahmolle ja nimeä se nopeudeksi.
Esiintymislavalla, tämän muuttujan tilaindikaattorissa pitää lukea "Witch: nopeus".
Jos siinä lukee pelkkä "nopeus", poista muuttuja ja luo se uudestaan, vain tälle hahmolle.  Muuttuja-paletissa ota puumerkki pois "nopeus" muuttujan edestä, jotta sitä ei näytetä esiintymislavalla.
Nopeus-muuttuja määrää kuinka nopeasti noita liikkuu. Käytetään muuttujaa, jotta voidaan muuttaa noidan nopeuden sitä mukaan kun peli etenee.
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
	(loppu ikuisesti)
```
###Testaa projektisi
__Napsauta vihreä lippu.__ 
Liikkuuko noita ruudun reunasta toiseen ilmestyen ja häipyen satunnaisesti?

Tallenna projektisi

###Kokeiltavaa
__Kokeile vaihtaa satunnaislukujen skaala. Mitä tapahtuu jos valitset hyvin isoja numeroita tai hyvin pieniä numeroita?__
(Saitko tästä lisää vinkkiä kuinka saisit noita lentämään nopeammin, sitä kauemmin peli pelataan?)

##VAIHE 3: Noita häipyy näkyvästä kun sitä napsautetaan

Jotta tästä tulisi peli, meidän pitää antaa pelaajalle jotain tekemistä.  Pelaajan pitää napsauttaa noitaa ja saada tämä häipymään näkyvästä.  Kun noitaa napsautetaan, haluamme hänen häipyvän näkyvästä ja soittavan äänen.

1. Äänet välilehdessä tuo uusi ääni kirjastosta: Sähköinen/fairydust. 

2. Lisää tämä skripti noidalle:

```scratch
	kun tätä hahmoa klikataan
	piilota
	soita ääni fairydust
```
###Testaa projektisi
__Napsauta vihreä lippu.__ 

Häipyykö noita näkymästä ja soittaako äänen kun sitä napsautetaan?

Tallenna projektisi

##VAIHE 4: Lisää pisteet ja ajastin

Meillä on noita, mutta nyt haluamme tehdä pelin! Haluamme saada pisteitä joka kerta kun napsautetaan noitaa, mutta haluamme myös pelille aikarajan. Voimme käyttää muuttujia tulokselle ja ajastimelle.

1. Tee uusi muuttuja kaikille hahmoille ja nimeä se tulokseksi. Muuta noidan skripti niin, että tämä muuttuja kasvaa yhdellä kun sitä napsautetaan.

```scratch
	kun tätä hahmoa klikataan
	piilota
	soita ääni fairydust
	muuta muuttujan tulos arvoa 1
```
2. Valitse esiintymislava, ja tee uusi muuttuja ja nimeä se ajastimeksi. Lisää uusi skripti joka tapahtuu kun vihreätä lippua napsautetaan.  Skripti asettaa ajastimen arvoon 30 ja nollaa tuloksen arvon.  Käytä sitten toista kunnes -lohkoa odottaakseen sekunnin ja sitten vähentääkseen ajastimen yhdellä. Tämän kuuluu toistua kunnes ajastin on nollassa. Tässä vaiheessa käytetään pysäytä kaikki pysäyttääkseen pelin.

```scratch
	kun klikataan LIPPU
	aseta ajastin arvoon 30
	aseta tulos arvoon 0
	toista kunnes ajastin = 0
		odota 1 sekuntia
		muuta muuttujan timer arvoa -1
	(loppu toista)
	pysäytä kaikki
```


###Testaa projektisi
__Napsauta vihreä lippu.__ 

Tallenna projektisi

###Kokeiltavaa
__Miten saisit noita lentämään nopeammin, sitä kauemmin peli kestää?__


__Hienoa! Olet tehnyt peruspelin loppuun. Mutta vielä on muutoksia, mitä voit tehdä. Kokeile tätä haastetta!__

##Haaste: lisää noitia

Jos yksi noita on hyvä, enemmän on varmasti vielä parempi! Pistetään kolme noitaa lentelemään ympäriinsä.
1. Kopioi noita oikea-napsauttamalla sitä hahmolistassa.
2. Muuta jokaisen noitahahmon kokoa niin, että ne ovat kaikki erikokoisia.
3. Muuta jokaisen noidan nopeus-muuttujaa niin, että ne kaikki lentävät eri nopeudella.
4. Siirrä noidat ympäri taustaa niin, etteivät ole kaikki yhdessä.

###Testaa projektisi
__Napsauta vihreä lippu.__ 

Liikkuuko kolme noitaa ruudun reunasta toiseen ilmestyen ja häipyen satunnaisesti, ja jotka häipyvät kun napsautat niitä?


Tallenna projektisi

###Kokeiltavaa
1. Montako noitaa on hyvä määrä tälle pelille?
2. Saatko noidat näyttämään erilaisilta? Voit joko muokata heidän asusteita tai käyttää Ulkonäkö-paletin lohkoja muuttaaksesi niitä.
3. Saatko noidat eriarvoisiksi? Mitä jos nopeimmasta (ja pienimmästä) noidasta saisi 10 pistettä?


__Hienoa, olet tehnyt harjoituksen, nyt voit nauttia pelistä!__
Muista, että voit jakaa pelisi kavereitesi ja perheesi kanssa valitsemalla  __Jaa__ valikkopalkista!
