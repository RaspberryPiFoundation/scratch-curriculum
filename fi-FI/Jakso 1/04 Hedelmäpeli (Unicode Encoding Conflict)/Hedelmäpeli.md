Taso 2

#Hedelmäpeli

__Johdanto:__
Tässä pelissä on kolme hahmoa, joiden asusteet vaihtuvat. Pelaajan pitää pysäyttää ne silloin, kun niillä on sama kuva näkyvissä (aivan kuten hedelmäpelissä!).

##VAIHE 1: Luo hahmo jonka asusteet vaihtuu

__Tuodaan pelin eri kuvat__

1. Aloita uusi projekti. Poista kissa hahmo oikeanapsauttamalla sitä ja valitsemalla 'poista'.
2. Tuo uusi hahmo.
3. Valitse kuva mistä tahansa kansiosta. Me valitsimme kirjastosta 'Asiat/Bananas', mutta voit käyttää mitä tahansa kuvaa.
4. Napsauta 'Asusteet'-välilehteä ja tuo 2 lisää kuvaa niin, että niitä on yhteensä kolme (me valitsimme 'Eläimet/beetle' and 'Asiat/donut', mutta voit käyttää mitä tahansa kuvia).

__Nyt meillä on asusteita ja halutaan, että hahmo vaihtaa niiden välillä.__

##VAIHE 2: Pistetään kuva muuttumaan

1. Napsauta 'Skriptit'-välilehteä.
2. Napsauta 'Tapahtumat' ja raahaa 'kun klikataan LIPPU' -lohko skriptien alueelle. Tämä laukaistaan kun napsautetaan vihreätä lippua.
3. Lisää 'ikuisesti' niin, että se liimautuu edellisen lohkon pohjaan.
4. Napsauta vihreätä lippua esiintymislavan oikeassa ylänurkassa. Huomaa, että skriptimme ympärille ilmestyy vaalea reunus.  Skripti ajetaan parhaillaan, koska napsautettiin vihreätä lippua, joka laukaisee skriptin.
5. Nyt napsauta 'Ulkonäkö' ja raahaa 'seuraava asuste' skriptiin.
6. Kuinka hidastetaan se niin, ettei se vaihda kuvaa noin nopeasti? Napsauta 'Ohjaus' ja raahaa 'odota 1 sekuntia'.
7. Säädä aika kunnes se vaihtuu nopeammin (0.1s näyttää hyvältä). Mitä tapahtuisi jos 'odota'-lohkoa ei olisi olemassa?

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

Hienoa! Saadaan hahmo vaihtamaan asusteita ikuisesti, mutta miten saadaan pysähtymään kun sitä napsautetaan?

1. Tee uusi muuttuja napsauttamalla 'Tieto' ja 'Tee muuttuja'. Nimeä se 'pysäytetty':ksi ja tee se kaikille hahmoille.  Kun se on luotu, ota puumerkki pois muuttujan edestä, niin sitä ei näytetä esiintymislavalla.
2. Aseta pysäytetty arvoon 1 kun joku napsauttaa kuvaa käyttäen 'kun tätä hahmoa klikataan' ja 'aseta pysäytetty arvoon 0', ja katsokin, että muutat 0:n 1:ksi.
3. Nyt pitää saada kuvan vaihtamisen pysähtymään kun muuttuja 'pysäytetty' on yhtä kuin 1. Napsauta 'Ohjaus' ja lisää 'ikuisesti'-silmukan sisälle 'jos, ... sitten' -silmukan. 'Jos'-silmukan tyhjään kohtaan pitää laittaa yhtäsuuruus-vertailu (... = ...) ja tarkistaa, onko 'pysäytetty' yhtä suuri kuin 0.
4. Lopuksi lisää 'aseta pysäytetty arvoon 0' -lohko 'kun klikataan LIPPU' -lohkon alle.


###Testaa projektisi
__Napsauta vihreätä lippua, odota hetki, sitten napsauta hahmoa.__ 

Vaihtuuko asuste ennen kuin napsautat hahmoa?
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
__Napsauta vihreätä lippua.__ Kaikkien hahmojen kuuluisi vaihtaa asusteensa.  Yritä pysäyttää ne kaikki saman kuvan kohdalla!

Tallena projektisi

###Kokeiltavaa

Kun käynnistät pelin heti latauksen jälkeen, kaikilla hahmoilla on sama asuste ja ne muuttuu samanaikaisesti. Mitä jos saisit hahmot muuttumaan satunaiseen asusteeseen kun virheätä lippua napsautetaa?
Vinkki: yritä valita satunainen asuste kullekin hahmolle kun peli alkaa.

__Hienoa, olet tehnyt peruspelin. On kuitenkin vielä muutoksia, mitä voit pelillesi tehdä. Kokeile näitä haasteita!__


##Haaste 1: Tee pelistä vaikeampi

Muuta pelin vaikeutta jotenkin. Asusteiden vaihdon nopeuttaminen on helppo.  Yritä tehdä jotain vielä mielikuvituksellisempaa. Tässä joitakin ideoita:

1. Muuta kunkin hahmon asusteiden määrä.
2. Tee joillekin hahmoille yksilölliset asusteet.
3. Käytä eri aikoja asusteiden vaihtojen välillä.
4. Laita kukin hahmo vaihtamaan satunaiseen asusteeseen eikä vain aina seuraavaan.

__Keksi omia ideoita ja pidä hauskaa!__

Joka kerta kun teet muutoksen, mieti, tekeekö se pelistä helpomman vai vaikeamman? Onko peli liian helppo tai liian vaikea?  Miten voit säätää vaikeustason niin, että se on juuri sopiva?


##Haaste 2: Tee pelistä vaikeampi ja helpompi ajan myötä

Eri ihmisillä on eri taitoja peliä pelatessa. __Miten saisit peli muuttamaan vaikeustasonsa pelaajan perusteella?__

Yksi tapa olisi __säätää nopeutta, jolla hahmot vaihtavat asusteensa__. Voisit käyttää muuttujaa, __odotusaika__, joka ilmoittaa kunkin hahmon 'odota'-lohkon ajan. Jos pelaaja voittaa kierroksen, odotusaikaa voidaan pienentää hieman (tehdään pelistä vaikeamman). Jos pelaaja häviää kierroksen, odotusaikaa voidaan pidentää hieman (tehdään pelistä helpomman).

##Haaste 3: Havaitse kun kaikilla kolmella hahmolla on pysäytettynä sama asuste

__Pelin tarkoitus on napsauttaa hahmoja niin, että ne pysähtyy saman asusteen kohdalla. Olisi kiva kun esiintymislava aistisi, milloin olet lopettanut pelaamisen ja kertoisi, oletko voittanut vai hävinnyt, tarkistamalla hahmojen asusteet.__

Ensiksi, lavan pitää tietää, milloin pelaaja on pelannut loppuun. Tämä tehdään laittamalla lavan tarkistamaan onko kaikki hahmot pysäytetty, joka kerta kun napsautetaan yhtäkin niistä. Muuta jokaisen hahmon 'kun tätä hahmoa klikataan' -koodin pätkää niin, että se lähettää viestin 'lopputarkistus'

Esiintymislava voi vastaanottaa tämän viestiin ja tarkistaa, onko peli jo pelattu, tarkistamalla onko kaikki kolmen hahmon 'pysäytetty'-muuttujat arvossa 1. Tämä tehdään käyttämällä 'x-sijainti of ...'-lohkoa kunkin hahmon kohdalla ja vaihtamalla x-sijainnin 'pysäytetty':ksi. Jos kaikki kolmen hahmon 'pysäytetty' arvo on 1, tiedetään pelin olevan ohi, ja voimme nyt tarkistaa, onko pelaaja voittanut.

Tämä tehdään käyttämällä samaa 'x-sijainti of ...'-lohkoa, mutta sen sijaan, että tarkistamme 'pysäytetty'-muuttujaa, voimme tarkistaa 'asusteen #' ja katsoa, onko hahmolla 1 sama asuste hahmon 2 kanssa ja onko hahmolla 2 sama asuste hahmon 3 kanssa.

Jotta tämä onnistuu, tarvitset 'jos'-lohkon tarkistamaan jokaista 'pysäytetty'-muuttujaa ja tämän sisälle 'jos ... muuten'-lohkon tarkistamaan, onko pelaaja voittanut tai hävinnyt, vertaamalla jokaista 'asusteen #'.

Tässä kohtaa voisit kertoa pelin tuloksen lähettämällä viestin ja tekemällä neljännen hahmon, joka vastaanottaa sen viestin. Ehkä Felix voisi palata ja onnitella (tai piikittelemään) pelaajaa?

__Hienoa, olet tehnyt harjoituksen, nyt voit nauttia pelistä!__
Muista, että voit jakaa pelisi kavereitesi ja perheesi kanssa valitsemalla  __Jaa__ valikkopalkista!
