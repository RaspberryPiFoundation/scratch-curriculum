Taso 1

#Felix & Hessu

__Johdanto:__
Tehdään hippa-peli jossa pelaajina ovat __Felix-kissa__ ja __Hessu-hiiri__ . Ohjaat Hessua käyttäen tietokoneen hiirtä ja yrität välttää joutumasta Felixin kynsiin. Mitä pitempään välttelet Felixiä, sitä enemmän saat pisteitä, mutta älä jää kiinni, koska silloin tuloksesi laskee!

##VAIHE 1: Felix seuraa hiiriosoitinta

1. Aloita uusi projekti.
2. Napsauta esiintymislava Hahmot-ikkunan vieressä, vaihda Taustat-välilehdelle ja tuo uusi tausta napsauttamalla "Uusi tausta kirjastosta"-ikoni (vasemman puoleisin) ja valitsemalla: Sisällä->hall->OK. Poista alkuperäinen tyhjä tausta.
3. Vaihda hahmon nimeksi Felix.
4. Varmista, että Felix suuntaa vain vasemmalle ja oikealle napsauttamalla: (kuva jossa vasen/oikea-nuolet)
5. Luo seuraava skripti:

```scratch

	kun klikataan LIPPU
	ikuisesti
		osoite kohti hiiriosoitin
		liiku 10 askelta
		seuraava asuste
		soita rumpua 62 0.3 iskun ajan
	(loppu ikuisesti)
```
		
###Testaa Projektisi
__Napsauta vihreä lippu.__
Seuraako Felix hiiriosoitinta?  Näyttääkö siltä, että se kävelee liikkuessaan?  Liikkuuko se oikealla nopeudella?

Tallenna projektisi.

##VAIHE 2: Felix jahtaa Hessua

__Seuraavaksi halutaan Felixin jahtaavan Hessu-hiirtä, hiiriosoittimen sijaan.__

1. Luo toinen hahmo napsauttamalla "Uusi hahmo kirjastosta"-ikoni (vasemman puoleisin) ja valitsemalla Eläimet->Mouse1->OK
2. Vaihda hahmon nimeksi Hessu.
3. Varmista, että Hessu suuntaa vain vasemmalle ja oikealle.
4. Muokkaa asuste ja tee siitä pienempi kuin Felix. Kokeile 6 napsautusta pienennä-työkalulla asusteen päällä: (kuva pienennä-työkalusta)
5. Anna Hessulle seuraava skripti:


```scratch
	
	kun klikataan LIPPU
	ikuisesti
		mene hiiriosoitin
		osoite kohti Felix
	(loppu ikuisesti)

```

###Testaa Projektisi
__Napsauta vihreä lippu.__

Liikkuuko Hessu hiirikohdistimen mukana?  Jahtaako Felix Hessua?

Tallenna projektisi.

##VAIHE 3: Felix kertoo kun on saanut Hessun kiinni

__Halutaan Felixin tietävän milloin on saanut Hessun kiinni, ja että hän kertoo meille asiasta.__


1. Muuta Felixin skripti tällaiseksi:

```scratch

	kun klikataan LIPPU
	ikuisesti
		osoite kohti hiiriosoitin
		liiku 10 askelta
		seuraava asuste
		soita rumpua 62 0.3 iskun ajan
		jos koskettaako Hessu
			sano Sainpas kiinni! 1 sekunnin ajan
		(loppu if)
	(loppu ikuisesti)
```

###Testaa Projektisi
__Napsauta vihreä lippu.__

Kertooko Felix kun se nappaa Hessun?

Tallenna projektisi.

##VAIHE 4: Hessu muuttuu haamuksi kun se jää kiinni

__Sen sijaan, että Felix sanoo jotain kun se nappaa Hessun, halutaan Hessun muuttuvan haamuksi kun se jää kiinni.__

1. Muuta Felixin skripti lähettämään viestin kun se nappaa Hessun.

```scratch
	
	kun klikataan LIPPU
	ikuisesti
		osoite kohti hiiriosoitin
		liiku 10 askelta
		seuraava asuste
		soita rumpua 62 0.3 iskun ajan
		jos koskettaako Hessu
			lähetä napattu
			soita rumpua 58 0.2 iskun ajan
			odota 1 sekuntia
		(loppu if)
	(ikuisesti loppu)

```

2. Tuo uusi asuste Hessulle kirjastosta Fantasy/ghost2-a.
3. Muokkaa asuste pienemmäksi. 6 napsautusta pienennä-työkalulla riittänee.
4. Muuta Hessun asusteiden nimet niin, että hiiriasusteen nimi on ‘elossa’ ja haamuasusteen nimi on ‘kuollut’.
5. Luo uusi skripti Hessulle jolla hän muuttuu haamuksi:

```scratch
	
	kun vastaanotan napattu
	vaihda asusteeksi kuollut
	odota 0.5 sekuntia
	vaihda asusteeksi elossa
```
	
###Testaa Projektisi
__Napsauta vihreä lippu.__

Muuttuuko Hessu haamuksi kun se jää kiinni?
Soittaako Felix oikeat äänet oikeaan aikaan?
Pysyykö Felix vielä paikallaan riittävän kauan, jotta Hessu voi paeta?

Tallenna projektisi.

##VAIHE 5: Laske Tulos
__Lisätään tulos, jotta tiedetään kuinka hyvin pärjätään tehtävässä Hessun henkivartijana.
Aloitetaan tuloksella 0 ja lisätään 1 piste joka sekunti.  Jos Felix nappaa Hessun, vähennetään tuloksesta sata pistettä.__

1. Tee muuttuja nimeltä Tulos, joka on sitten kaikille hahmoille. (Tieto -> Tee muuttuja)
2. Esiintymislavalla, luo 2 skriptiä

```scratch
	
	kun klikataan  LIPPU
	aseta Tulos arvoon 0
	ikuisesti
		muuta Tulos by 1
		odota 1 sekuntia
	(loppu ikuisesti)
	
	kun vastaanotan napattu
	muuta Tulos by -100
```
	
###Testaa Projektisi
__Napsauta vihreä lippu.__

Nouseeko tulos yhdellä joka sekunti?
Laskeeko tulos sadalla kun Hessu jää kiinni?
Mitä tapahtuu kun Hessu jää kiinni ennen kuin tulos pääsee sataan pisteeseen?
Nollaantuuko tulos kun aloitat uuden pelin?

Tallenna projektisi.

__Hienoa! Peli on valmis - nyt voit nauttia siitä!__
Muista - voit jakaa pelisi ystäviesi ja perheesi kanssa napsauttamalla __Jaa__ valikkopalkissa
