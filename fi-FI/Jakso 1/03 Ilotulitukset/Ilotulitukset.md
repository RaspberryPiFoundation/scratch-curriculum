Taso 1

#Ilotulitukset

__Johdanto:__
Tässä projektissa luodaan kaupungin ylle ilotulitusta.

##VAIHE 1: Luo raketti joka lentää kohti hiiriosoitinta.

__Tuodaan eri kuvia peliä varten__

1. Aloita uusi projekti. Poista kissa hahmo oikeanapsauttamalla sitä ja valitsemalla poista.
2. Korvaa tausta Ulkona/city-with-water
3. Käytä "Lataa hahmo tiedostosta"-ikoni ja lisää raketti-hahmo projektille (käytä Resurssit/raketti.png -asuste). 
4. Piilota raketti silloin kun vihreätä lippua napsautetaan.

Nyt haluamme saada raketti liikkumaan kohti hiiriosoitinta kun hiiriä napsautetaan.

5. Lisää kun painetaan välilyönti -lohko ja tämän alla aseta raketti tulemaan näkyviin ja liukumaan kohti hiiriosoitinta.

```scratch
	kun klikataan LIPPU
	piilota
	kun painetaan välilyönti
	näytä
	liu'u 1 sekuntia kohtaan x: hiiren x-sijainti y: hiiren y-sijainti
```
		
###Testaa projektisi
__Napsauta vihreätä lippua, aseta hiirikohdistin esiintymislavalle ja paina välilyönti.__

Ilmestyykö raketti liikkumaan hiiriosoittimen kohdalle? Mitä tapahtuu jos liikutat hiiriosoitinta ja painat uudelleen välilyönnin?

6. Raketit eivät tyypillisesti lennä sivuttain, joten varmistetaan, että raketti lentää hiirikohdistimen kohdalle ruudun alapuolelta.  Ennen kuin näytetään raketti, käytä mene -lohkoa käskeäksesi sen ruudun alapuolelle, mutta niin, että se pysyy vaakasuunnassa samassa kohtaa.

```scratch
	kun klikataan LIPPU
	piilota
	kun painetaan välilyönti
	mene kohtaan x: hiiren x-sijainti y: -200
	näytä
	liu'u 1 sekuntia kohtaan x: hiiren x-sijainti y: hiiren y-sijainti
```

###Testaa projektisi
__Napsauta vihreätä lippua, aseta hiirikohdistin esiintymislavalle ja paina välilyönti.__

Lentääkö raketti ruudun alapuolelta kohti hiiriosoitinta? Mitä tapahtuu jos liikutat hiiriosoitinta ja painat uudelleen välilyönnin?

7. Nyt pistetään tämä toimimaan käyttäen hiiren napsautusta välilyönnin sijaan. Tämän tehdäksemme, voimme kääriä skriptimme silmukalla __ikuisesti jos onko hiiren nappi painettu__.
Sitten korvataan __kun painetaan välilyönti__ ohjauslohko __kun klikataan lippu__ -lohkolla ja viimeisenä varmista, että raketti on piilossa kun kaikki käynnistyy.

```scratch
	kun klikataan LIPPU
	piilota
	ikuisesti
		jos onko hiiren nappi painettu?
			mene kohtaan x: hiiren x-sijainti y: -200
			näytä
			liu'u 1 sekuntia kohtaan x: hiiren x-sijainti y: hiiren y-sijainti
		(loppu jos)
	(loppu ikuisesti)
```
###Testaa projektisi
__Napsauta vihreätä lippua ja napsauta hiirtä esiintymislavan kohdalla.  Napsauta toista kohtaa.__

###Kokeiltavaa
1. Yritä muuttaa kohtaa, mihin raketti siirtyy ennen liukumista hiiriosoitinta kohti niin, että se kaartuu hieman.
2. Yritä tehdä osan raketeista hieman hitaampia tai nopeampia kuin muita.

Tallena projektisi.

##VAIHE 2: Räjäytä raketti

1. Jotta saadaan raketti räjähtämään, pitää ensiksi saada raketti soittamaan pamauksen ääntä Resurssit/pam ennen kuin se alkaa liikkua ja piilottaa itsensä kun se saavuttaa hiirenkohdistimen. Tuo ääni menemällä Äänet-välilehdelle ja valitsemalla Lataa ääni tiedostosta.

```scratch
	kun klikataan LIPPU
	piilota
	ikuisesti
		jos onko hiiren nappi painettu?
			mene kohtaan x: hiiren x-sijainti y: -200
			soita ääni pam
			näytä
			liu'u 1 sekuntia kohtaan x: hiiren x-sijainti y: hiiren y-sijainti
			piilota
		(loppu jos)
	(loppu ikuisesti)
```
2. Seuraavaksi, pistetään raketti lähettämään uusi viesti kun se räjähtää. Vastaanotamme tämän viestin myöhemmin.

```scratch
	kun klikataan LIPPU
	piilota
	ikuisesti
		jos onko hiiren nappi painettu?
			mene kohtaan x: hiiren x-sijainti y: -200
			soita ääni pam
			näytä
			liu'u 1 sekuntia kohtaan x: hiiren x-sijainti y: hiiren y-sijainti
			piilota
			lähetä räjähdä
		(loppu jos)
	(loppu ikuisesti)
```
###Testaa projektisi
__Napsauta vihreätä lippua.__
Varmista, että raketti soittaa äänen ja piiloutuu kun saavuttaa hiirenosoittimen.

3. Tuo uusi hahmo käyttäen Resurssit/ilotulitus1.png
4. Kun hahmo vastaanottaa räjähdä-viestin, sen kuuluu piilottaa itsensä, siirtyä mene-lohkolla raketin kohtaan, näyttäytyä ja piiloutua uudelleen sekunti myöhemmin.

```scratch
	kun vastaanotan räjähdä
	piilota
	mene kohtaan x: x-sijainti of raketti y: y-sijainti of raketti
	näytä
	odota 1 sekuntia
	piilota
```
###Testaa projektisi
__Laita toinen raketti ilmaan.__ 
Tuleeko sen tilalle räjähde-kuva kun se räjähtää?
Mitä tapahtuu jos pidät hiiren napin alhaalla samalla kun siirrät hiirtä? (Ei hätää, korjaamme tämän myöhemmin.)

Tallena projektisi

##VAIHE 3: Tee räjähteistä yksilöllisiä

1. Nyt voimme tehdä jokaisen räjähdyksen enemmän yksillölliseksi käyttämällä aseta tehoste väri -lohkoa, ja käskemällä sen valita satunnaisväri välillä 1 ja 200 ennen sen näyttämistä.

```scratch
	kun vastaanotan räjähdä
	piilota
	aseta tehoste väri kohteeseen pick random 1 to 200
	mene kohtaan x: x-sijainti of raketti y: y-sijainti of raketti
	näytä
	odota 1 sekuntia
	piilota
```

###Testaa projektisi
__Napsauta vihreätä lippua.__

Onko jokaisella räjähdyksellä eri väri?

2. Lisätään enemmän vaihtoehtoisia räjähdyskuvia asusteina, käyttäen Resurssit/ilotulitus2.png ja Resurssit/ilotulitus3.png, ja valitaan näiden välillä, edelleen, ennen sen näyttämistä.

###Testaa projektisi
__Napsauta vihreätä lippua.__

Onko jokaisella räjähdyksellä eri räjähdyskuva?

3. Lopuksi pistetään räjähdys kasvamaan ajan mittaan sen sijaan, että se vain ilmestyy. Sen sijaan, että odotetaan sekunti, aseta hahmon koko 5%:ksi ennen kuin se näytetään, ja kun se on näytetty, kasvatetaan sen kokoa kahdella 50 kertaa, käyttäen toista-lohkoa.

```scratch
	kun vastaanotan räjähdä
	piilota
	aseta tehoste väri kohteeseen pick random 1 to 200
	mene kohtaan x: x-sijainti of raketti y: y-sijainti of raketti
	aseta koko arvoon 5%
	näytä
	toista 50
		muuta kokoa määrällä 2
	(loppu toista)
	piilota
```
###Testaa projektisi
__Napsauta vihreätä lippua.__

Leviääkö räjähdyskuva raketin keskeltä ja kasvaako se hitaasti isommaksi?

###Kokeiltavaa
Miksei yrittäisi tehdä jokaisestä räjähdyksestä vielä yksilöllisemmän muuttamalla sen kokoa ja kasvun nopeutta?

Tallena projektisi

##VAIHE 4: Lähetys-bugin korjaaminen
Muistatko kun meillä oli aikaisemmin bugi koskien hiiren napin alhaalla pitämistä?

Näin käy, koska sen jälkeen kun raketti lähettää räjähdyksensä, se toistaa heti jos-silmukan ja lähettää toisen räjähdys-viestin, ennen kuin edellinen on ehtinyt täysin näkyä.


1. Tämän korjataksemme, voimme korvata lähetä-lohkon lähetä ja odota -lohkolla. Tällä tavalla, silmukka ei toistu ennen kuin räjähdys on räjähtänyt loppuun.

```scratch
	kun klikataan LIPPU
	piilota
	ikuisesti
		jos onko hiiren nappi painettu?
			mene kohtaan x: hiiren x-sijainti y: -200
			soita ääni pam
			näytä
			liu'u 1 sekuntia kohtaan x: hiiren x-sijainti y: hiiren y-sijainti
			piilota
			lähetä räjähdä ja odota
	(loppu ikuisesti)
```
###Testaa projektisi
__Napsauta vihreätä lippua, pidä hiiren nappi painettuna ja liikuta hiirenosoitin ympäri esiintymislavaa.__

Ilmestyykö räjähdyskuva oikeassa paikassa oikeaan aikaan?

Tallena projektisi
