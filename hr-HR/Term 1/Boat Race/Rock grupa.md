---
title: Rock Bend
level: Scratch 1
language: hr-HR

stylesheet: scratch
embeds: "*.png"

materials: ["Club Leader Resources/*"]
...


# Uvod { .intro }

U ovom projektu naučit ćeš kako programirati vlastite glazbene instrumente!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26741186/?autostart=false" frameborder="0"></iframe>
  <img src="band-final.png">
</div>


# Korak 1: Likovi { .activity }

Prije samog dodavanja naredbi potrebno je dodati objekt na koji će se one odnositi. U Scratchu se takvi objekti nazivaju 'likovi'.


## Zadatci { .check }

+ Za početak, otvori program Scratch. Možeš ga pronaći i na internetu na adresi <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>. 
	
	Izgleda ovako:

	![screenshot](band-scratch.png)

+ Mačka koju vidiš je maskota Scratcha. Ukloni ju tako da na nju klikneš desnom tipkom miša. Iz izbornika kojeg dobiješ odaberi naredbu 'obriši'.

	![screenshot](band-delete.png)

+ Za dodavanje novog lika potrebno je kliknuti na ikonu 'Odaberi lik iz knjižnice' kako bi se otvorio popis svih Scratch likova.

	![screenshot](band-sprite-library.png)

+ Listaj dolje dok ne pronađeš bubanj. Klikni na njega, a zatim na gumb 'OK' kako bi se bubanj dodao u projekt.

	![screenshot](band-sprite-drum.png)

+ Klikni na ikonu 'umanji', zatim nekoliko puta na bubanj da se smanji.

	![screenshot](band-shrink.png)


## Spremi projekt { .save }

Daj svom programu ime tako što ćeš ga upisati u okvir za tekst u gornjem lijevom kutu. Zatim iz izbornika 'Datoteka' odaberi naredbu 'Spremi'.

![screenshot](band-save.png)


# Korak 2: Pozornica { .activity }

Pozornica je prostor na lijevoj strani i tamo će tvoj projekt oživjeti. Zamisli da je to prostor za izvedbu, kao prava pozornica!


## Zadatci { .check }

+ Trenutno je pozornica bijela i izgleda prilično dosadno! Dodajmo joj pozadinu klikom na 'Odaberi pozadinu iz knjižnice'	![screenshot](band-stage-choose.png)

+ U izbornicima koji se nalaze na lijevoj strani odaberi 'Unutarnji prostor', pronađi i odaberi pozadinu pozornice i klikni na gumb 'OK'	![screenshot](band-backdrop.png)

+ Tvoja pozornica bi sada trebala izgledati ovako:

	![screenshot](band-stage.png)

# Korak 3: Stvaranje bubnja { .activity }

Sada ćemo programirati bubanj tako da proizvede zvuk svaki puta kada ga se udari.

## Zadatci { .check }

+ Blokove naredbi možeš pronaći na kartici 'Skripte'. Primjeti kako su razdvojeni u skupine koje su različito obojane! 
	
	Klikni na lik bubnja, zatim prenesi ova dva bloka s naredbama u prostor za unos naredbi koji se nalazi na desnoj strani prozora. Vodi računa o tome da su povezani (kao Lego kockice):

	![screenshot](band-code.png)

+ Klikni na bubanj i isprobaj svoj novi instrument! 
+ Stvarajući novi kostim možeš promijeniti izgled bubnja kada se na njega klikne. Odaberi karticu 'Kostimi' i vidjet ćeš sliku bubnja.

	![screenshot](band-drum-costume.png)

+ Klikni desnim klikom na kostim i klikni 'Kloniraj'. Napravit će se kopija kostima.

	![screenshot](band-drum-duplicate.png)

+ Klikni na novi kostim, odaberi alat za crtanje linija i nacrtaj linije tako da izgleda kao da bubanj proizvodi zvuk.

	![screenshot](band-drum-hit.png)

+ Imena kostima sada baš i nisu od velike pomoći. Preimenuj ih u 'nije udaren' i 'udaren' tako što ćeš upisati novo ime svakog kostima u okvir za tekst.

	![screenshot](band-drum-name.png)

+ Sada kada imaš dva različita kostima za svoj bubanj, možeš odabrati koji kostim će se prikazati u kojem trenutku! Dodaj ove dvije naredbe svom bubnju:

	![screenshot](band-looks.png)

	Naredba za promjenu kostima nalazi se u kartici 'Izgled' {.blocklooks}

+ Isprobaj svoj bubanj. Kada se na njega klikne, trebao bi izgledati kao da je udaren!


## Spremi promjene u projektu { .save }


##Izazov: Poboljšaj svoj bubanj. { .challenge }

+ Možeš li promijeniti zvuk kojeg proizvodi bubanj kada ga se klikne?

![screenshot](band-drum-sound.png)

+ Možeš li postići da bubanj proizvede zvuk kada se pritisne razmaknica? Trebat će ti naredba {.blockevents}:

```blocks
	kada je tipka [razmaknica v] pritisnuta
```

Umjesto prenošenja možeš kopirati već postojeći kôd - klikni na njega desnom tipkom miša i odaberi naredbu 'kloniraj'.

![screenshot](band-duplicate-code.png)


## Spremi promjene u projektu { .save }


# Korak 4: Stvaranje pjevačice { .activity .new-page }

Dodajmo bendu i pjevačicu!


## Zadatci { .check }

+ Na pozornicu dodaj još dva lika: pjevačicu i mikrofon.

	![screenshot](band-singer-mic.png)

+ Kako bi pjevačica zapjevala, liku treba dodati zvuk. Označi lik pjevačice, odaberi karticu 'Zvukovi' i ikonu 'Odaberi zvuk iz knjižnice':

	![screenshot](band-import-sound.png)

+ Prikladan zvuk nađi u izborniku 'Glasovi'.

	![screenshot](band-choose-sound.png)

+ Nakon dodavanja zvuka na kartici 'Skripte' dodaj sljedeći kôd:

```blocks
	kada je lik kliknut
	sviraj zvuk [singer1 v] do kraja
```

+ Klikni na pjevačicu i provjeri pjeva li.


## Spremi promjene u projektu { .save }


##Izazov: Promjena kostima pjevačice { .challenge }

+ Možeš li napraviti da tvoja pjevačica izgleda kao da pjeva kada ju se klikne? Ako trebaš pomoć, možeš koristiti upute za stvaranje bubnja iznad.

![screenshot](band-singer-final.png)


Sjeti se testirati kako tvoj novi kod radi!


## Spremi promjene u projektu { .save }


##Izazov: Napravi svoj vlastiti bend { .challenge }
Iskoristi sve prethodno naučeno za izradu svog vlastitog benda! Možeš stvoriti bilo koji instrument, a možeš i pregledati raspoložive zvukove i instrumente da dobiješ ideje.

![screenshot](band-ideas.png)

Tvoji instrumenti ne moraju predstavljati ono što jesu. Na primjer, možeš napraviti klavir od muffina!

![screenshot](band-piano.png) 

Kao što koristiš već postojeće likove, možeš nacrtati i vlastite.

![screenshot](band-draw.png) 

Imaš li mikrofon, možeš snimiti svoje vlastite zvukove. Također možeš koristiti i web kameru!

![screenshot](band-io.png)


## Spremi projekt { .save }
