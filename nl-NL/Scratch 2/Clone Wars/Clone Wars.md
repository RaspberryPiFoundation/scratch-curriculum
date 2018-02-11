---
title: Clone Wars
level: Scratch 2
language: nl-NL
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leider Bronnen/*"]
beta: true
...

## Community Contributed Project { .challenge .pdf-hidden }
Dit project is ontworpen in samenwerking met Erik. Als jij ook een eigen project wil bijdragen, [neem contact met ons op via Github](https://github.com/CodeClub).

# Introductie { .intro }

In dit project gaan wij je leren een spel te maken, waarin je de planeet Aarde moet beschermen tegen monsters vanuit de ruimte.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/46018140/?autostart=false" frameborder="0"></iframe>
  <img src="invaders-final.png">
</div>

# Stap 1: Maak een ruimteschip { .activity }

Laten we een ruimteschip maken, waarmee we de planeet Aarde kunnen verdedigen!

## Activiteiten Checklist { .check }

+ Begin een nieuw Scratch project en verwijder de kat sprite, zodat je een leeg project hebt. Je kan de online Scratch editor vinden via <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Voeg de 'stars' achtergrond en de 'Spaceship' sprite toe aan jouw project. Laat het ruimteschip krimpen en verplaats het naar de onderkant van het scherm.

	![screenshot](invaders-sprites.png)

+ Voeg nu programma blokken toe aan jouw ruimteschip, waarmeee het ruimteschip naar links beweegt, zodra de pijl naar links toets wordt ingedrukt. Je moet hiervoor de volgende blokken gebruiken:

	```blocks
		wanneer ⚑ wordt aangeklikt
		herhaal
   			als <toets [pijltje naar links v] ingedrukt?> dan
  		    verander x met (-4)
 		  einde
		einde
	```

+ Voeg nu zelf de programma blokken toe, waarmee het schip naar rechts beweegt, zodra de pijl naar rechts toets wordt ingedrukt.

+ Probeer nu jouw programma om te zien of je jouw ruimteschip kan bewegen met de pijtjes toetsen.

## Sla jouw project op. { .save }

# Stap 2: Bliksen Schichten { .activity }

Dan gaan we nu het ruimteschip de mogelijkheid geven bliksem schichten af te vuren!

## Activiteiten Checklist { .check }

+ Voeg de 'Bliksem' (Lightning) sprite toe, vanuit de Scratch bibliotheek. Verander het uiterlijk van de sprite, zodat de bliksem onderste boven komt te staan.

	![screenshot](invaders-lightning.png)

+ Zodra het spel wordt gestart, moet de bliksem worden verborgen, totdat het schip zijn laserkanonnen afvuuurt.

	```blocks
		wanneer ⚑ wordt aangeklikt
		verdwijn
	```

+ Voeg de volgende programma blokken toe **aan het ruimteschip** om en bliksemschicht te maken, zodra de speler op de spatiebalk drukt.


	```blocks
		wanneer ⚑ wordt aangeklikt
		herhaal
   			als <toets [spatiebalk v] ingedrukt?> dan
    		  maak kloon van [Lightning v]
  		 einde
		einde
	```

+ Zodra er een nieuwe kloon wordt gemaakt, zou deze moeten beginnen vanaf de plaats waar het ruimteschip zich op dat moment bevindt. Vervolgens beweegt het naar boven over het speelveld, totdat het de rand van het speelveld bereikt. Voeg het volgende programmablok toe aan **de Bliksem sprite**:

	```blocks
		wanneer ik als kloon start
		ga naar [Spaceship v]
		verschijn
		herhaal tot <raak ik [rand v]?>
		   verander y met (10)
		einde
		verwijder deze kloon
	```

Note: We verplaatsen de nieuwe kloon naar het ruimteschip, terwijl het verborgen is, voordat het in het speelveld zichtbaar wordt. Dit ziet er beter uit.

+ Test het afvuren van bliksems, door op de spatiebalk te drukken.

## Sla jouw project op { .save }

## Uitdaging: Verbeteren van de Bliksem {.challenge}
Wat gebeurd er als je de spatiebalk ingedrukt houdt? Kan je een `wacht` {.blockcontrol} blok gebruiken om dit probleem te verhelpen?

## Sla jouw project op { .save }

# Step 3: Vliegende Ruimte-Nijlpaarden { .activity }

Nu gaan we een heleboel vliegende nijlpaarden toevoegen, die proberen jouw ruimteschip te vernietigen.

## Activiteiten Checklist { .check }

+ Maak een nieuwe sprite van het 'Hippo1' plaatjes in de Scratch bibliotheek.

	![screenshot](invaders-hippo.png)

+ Stel de rotatie in op alleen van links naar rechts, en voeg het volgende progrmma blok toe om de sprite te verbergen aan de begin van het spel:

	```blocks
		wanneer ⚑ wordt aangeklikt
		verdwijn	
	```

+ Maak een nieuwe variabele en noem deze `speed` {.blockdata}, en stel deze in voor alleen de nijlpaard sprite.

	![screenshot](invaders-var.png)

	Je kan zien dat je het goed hebt uitgevoerd, omdat de naam van de sprite wordt weergegeven naast de variablele, zoals dit:

	![screenshot](invaders-var-test.png)

+ Het volgende programma blok zal elke paar seconden een nieuw nijlpaard maken. **Het Speelveld** is een goede plaats om het volgende programma blok te laten werken:

	```blocks
		wanneer ⚑ wordt aangeklikt
		herhaal
		   wacht (willekeurig getal tussen (2) en (4)) sec.
		   maak kloon van [Hippo1 v]
		einde
	```

+ Zodra een nijlpaard kloon start, laat je het over het speelveld bewegen (met een willekeurige snelheid), totdat het wordt geraakt door een bliksemschicht. Voeg het volgende programmablok toe aan de sprite **van het nijlpaard**:

	```blocks
		wanneer ik als kloon start
		maak [speed v] (willekeurig getal tussen (2) en (4))
		ga naar x:(willekeurig getal tussen (-220) en (220)) y:(150)
		verschijn
		herhaal tot <raak ik [lightning v]?>
		   neem (speed) stappen
		   draai ↻ (willekeurig getal tussen (-10) en (10)) graden
		   keer om aan de rand
		einde
		verwijder deze kloon		
	```

+ Test jouw nijlpaard programma. Elke paar seconden, zou er een nieuwe kloon van het nijlpaard moeten verschijnen die een willekeurige snelheid heeft.

	![screenshot](invaders-hippo-test.png)

+ Test jouw laser kanon. Wannneer je een nijlpaard raakt, verdwijnt deze dan?

+ Zodra een nijlpaard jouw ruimteschip raakt, zou deze moeten ontploffen! Om dit te doen, moet je er eerst voor zorgen dat jouw ruimteschip 2 uiterlijken heeft die wij 'normal' and 'hit' zullen noemen.

	![screenshot](invaders-spaceship-costumes.png)

	Het 'hit' uiterlijk van het ruimteschip, kan je maken door het 'Sun' plaatje te importeren uit de Scratch bibliotheek. Vervolgens kan je de kleur veranderen met de "Kleur een vorm" gereedschap.

	![screenshot](invaders-sun.png)

+ Voeg het volgende programma toe aan het ruimteschip zodat het van uiterlijk verandert, zodra het in aanraking komt met een vliegend nijlpaaard:

	```blocks
		wanneer ⚑ wordt aangeklikt
		herhaal
		   verander uiterlijk naar [normal v]
		   wacht tot <raak ik [Hippo1 v]?>
		   verander uiterlijk naar [hit v]
		   zend signaal [hit v]
		   wacht (1) sec.
		einde
	```

+ Is je opgevallen dat je een 'hit' boodschap hebt uitgezonden met bovenstaand programma? Die boodschap kan je bijvoorbeeld gebruiken om alle nijlpaarden te laten verdwijnen, zodra het ruimteschip is geraakt.

	Voeg dit programma toe aan jouw nijlpaard:

	```blocks
		wanneer ik signaal [hit v] ontvang
		verwijder deze kloon
	```

+ Test dit programma door een nieuw spel te starten en jouw ruimteschip te laten botsen met een nijlpaard. 

	![screenshot](invaders-hippo-collide.png)

## Sla jouw programma op { .save }

## Uitdaging: Levens en Score {.challenge}
Kan jij `levens` {.blockdata}, `score` {.blockdata} en misschien ook `highscore` {.blockdata} variabelen aan jouw spel toevoegen? Als je het even niet meer weet, kan je misschien even terugkijken naar het 'Vang de stippen' project om te zien hoe dat gaat.

## Sla jouw project op { .save }

# Stap 4: Fruit Vleermuizen! { .activity }

We maken het spel nog iets leuker door middel van vleermuizen, die sinaasappels naar jouw ruimtevoertuig gooien.

## Activiteiten Checklist { .check }

+ Om te beginnen maken we een nieuwe vleermuis sprite (Bat1 uit de sprite bibliotheek). Deze laten we doormiddel van een `neem ( ) stappen` {.blockmotion} blokje binnen een `herhaal` {.blockcontrol} blok bovenaan het scherm heen en weer bewegen. Vergeet niet om jouw nieuwe programma te testen.

	![screenshot](invaders-bat.png)

+ ALs je kijkt naar de uiterlijkheden van de vleermuis, zal je zien dat deze er al twee heeft:

	![screenshot](invaders-bat-costume.png)

	Gebruik het `volgend uiterlijk` {.blocklooks} blok om de vleermuis met zijn vleugels te laten flapperen, terwijl hij beweegt.

+ Maak een nieuwe 'Orange' sprite vanuit de Scratch bibliotheek.

	![screenshot](invaders-orange.png)


+ Voeg het volgende programma aan jouw vleermuis toe, zodat deze regelmatig een nieuwe kloon van de sinaasappel-sprite maakt.

	```blocks
		wanneer ⚑ wordt aangeklikt
		herhaal
		   wacht (willekeurig getal tussen (5) en (10)) sec.
		   maak kloon van [Orange v]
		einde
	```

+ Klik op jouw snaasappel-sprite en voeg daar het volgende progrmma aan toe om de sprite langs het schrm omlaag te laten vallen in de richting van het ruimteschip:

	```blocks
		wanneer ⚑ wordt aangeklikt
		verdwijn

		wanneer ik als kloon start
		ga naar [Bat1 v]
		verschijn
		herhaal tot <raak ik [rand v]?>
		verander y met (-4)
		einde
		verwijder deze kloon

		wanneer ik signaal [hit v] ontvang
		verwijder deze kloon
	```

+ In het programma van jouw ruimteschip moet je ook een anpassing doen. Verbeter het programma zodat jouw ruimteschip ontploft, zodra deze een nijlpaard of een sinaasappel raakt:

	```blocks
		wacht tot <<raak ik [Hippo1 v]?> of <raak ik [Orange v]?>>
	``` 

+ Test jouw spel. Wat gebeurd er wanneer je geraakt wordt door een vallende sinaasappel?

## Sla jouw project op { .save }

# Stap 5: Game over { .activity }

Nu gaan we een 'game over' boodschap toevoegen aan het eind van het spel.

## Activiteieten Checklist { .check }

+ Als je dat nog niet gedaan hebt, moet je nu eeen nieuwe variabele maken genaamd `levens` {.blockdata}. Jouw ruimteschip moet beeginnen met 3 levens en een leven moeten verliezen, zodra deze in aanraking komt met de vijand. Het spel moet eindigen, zodra jouw levens op zijn. Ook hier geld: weet je het even niet meer, kijk daan terug naar het 'Vang de stippen' project om jouw geheugen op te frissen.

+ Teken zelf een nieuwe sprite 'Game Over' genaamd, door gebruik te maken van het tekst gereedschaptool.

	![screenshot](invaders-game-over.png)

+ In jouw speelveld, zend je een `game over` {.blockevents} signaal uit, net voordat het spel eindigd.

	```blocks
		zend signaal [game over v] en wacht
	```

+ Voeg het volgende programma toe aan jouw 'Game Over' sprite, zodat de boodschap getoond wordt, zodra het spel is afgelopen:

	```blocks
		wanneer ⚑ wordt aangeklikt
		verdwijn

		wanneer ik signaal [game over v] ontvang
		verschijn
	```

	Omdat je gebruik hebt gemaakt van eeen `zend signaal [game over] en wacht` {.blockevents} blok in jouw speelveld, zal het wachten tot de 'Game Over' sprite wordt getoond, voordat het spel wordt beëindigd.

+ test jouw spel. Hoeveel punten kan jij behalen?Kan je zelf nog dingen bedenken om jouw spel te verbeteren als je het te moeilijk of te makkelijk vind?

## Sla jouw project op { .save }

## Uitdaging: Verbeter jouw spel {.challenge}
Welke verbeteringen kan je nog aan het spel toevoegen? Hier volgen een paar voorbeelden:
+ Voeg gezondheidspakketten toe, zodat je extra levens kan verzamelen;

![screenshot](invaders-aid.png)

+ Voeg zwevende rotsblokken toe, die jouw ruimteschip moet vermijden;
	
![screenshot](invaders-rocks.png)

+ Laat meer vijaanden verschijnen, zodra je 100 punten hebt gehaald.

```blocks
	wacht tot <(score) = [100]>
```

## Sla jouw project op { .save }