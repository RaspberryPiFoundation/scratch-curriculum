Level 1

#Sla-een-heks

__Introductie:__
Dit project is gebaseerd op het spelletje __whack-a-mole__. Je krijgt punten als je de heksen die op het scherm verschijnen kan slaan. Bedoeling van het spelletje is om zoveel mogelijk punten te scoren in 30 seconden!

##￼STAP 1: Maak een vliegende heks
1. Maak een nieuw scratch project.
2. Verwijder de kat sprite en vervang de achtergrond door de Nature/forest achtergrond.
3. Gebruik de nieuwe sprite knop om een nieuwe heks sprite toe te voegen aan het project (gebruik het Fantasy/witch1 kostuum). Nu willen we onze heks nog laten bewegen.
4. Voeg een variabele toe voor deze sprite genaamd snelheid. Op de Stage zou de stage monitor voor deze variabele “Sprite1 snelheid” moeten tonen. Als er gewoon “snelheid” zou staan, verwijderen dan de variabele en maak ze opnieuw aan, enkel voor deze sprite. Vink het vakje af naast de snelheid blok in het Variabelen palet, zodat het niet op de Stage te zien is. De snelheid variabele zal controleren hoe snel de heks beweegt. We gebruiken hier een variabele voor, zodat we de snelheid van de heks kunnen aanpassen naargelang het spelletje verder gaat.
5. We willen dat de heks begint te bewegen wanneer het spel start, dus maak een script zoals het volgende:

```scratch
	wanneer VLAG wordt aangeklikt
	maak snelheid 5
	herhaal
		neem snelheid stappen
	(einde herhaal)
```
		
### Test Je Project
__Klik op het groene vlaggetje__ en kijk wat je heks doet. Waarom zit ze vast aan de rand van het scherm?
6. Om de heks niet vast te laten zitten moeten we haar laten terugkeren wanneer ze de rand van het scherm raakt. Voeg onder je neem snelheid stappen blok een keer om aan de rand blok toe.
```scratch
	wanneer VLAG wordt aangeklikt
	maak snelheid 5
	herhaal
		neem snelheid stappen
		keer om aan de rand
	(einde herhaal)
```
7. Om de heks niet ondersteboven te doen kantelen pas je de draaistijl aan in de sprite samenvatting.

### Test Je Project
__Klik op het groene vlaggetje__
Beweegt de heks van de ene kant van het scherm naar de andere kant?

Sla je project op

### Om te proberen
__Probeer de waarde van de snelheid variabele aan te passen om haar sneller of trager te laten vliegen.__

__Hoe zou je er voor zorgen dat de heks sneller wordt naargelang ze sneller vliegt?__
(Dit is niet meteen voor de hand liggend, dus maak je geen zorgen als je niet meteen ziet hoe je het zou doen. Je zal nog meer hints krijgen als je verder aan dit project werkt.)

## STAP 2: Zorg er voor dat de heks willekeurig verschijnt en verdwijnt
Om het spelletje leuker te maken willen we er voor zorgen dat de heks willekeurig verschijnt en verdwijnt. We doen dat met een ander script dat op dezelfde tijd loopt als het script dat de heks beweegt. Dit nieuwe script moet de heks verbergen voor een willekeurige tijd, en haar daarna weer laten zien voor een willekeurige tijd. Dat wordt dan oneindig herhaald (of tot het spelletje gedaan is).
Maak dit script voor de heks:
```scratch
	wanneer VLAG wordt aangeklikt
	herhaal
		verbergen
		wacht willekeurig getal tussen 2 en 5 tellen
		toon
		wacht willekeurig getal tussen 3 en 5 tellen
	(einde herhaal)
```
### Test Je Project
__Klik op het groene vlaggetje__ 
Beweegt de heks van de ene kant van het scherm naar de andere kant terwijl ze willekeurig verdwijnt en verschijnt?

Sla je project op

### Om te proberen
__Probeer het bereik van de willekeurige getallen aan te passen. Wat gebeurt er als je heel hoge of heel lage getallen kiest?__
(Begrijp je al beter hoe je er voor kan zorgen dat de heks sneller kan laten vliegen naargelang het spelletje langer duurt?)

##￼STEP 3: Zorg er voor dat de heks verdwijnt wanneer je op haar klikt
Om hier een spelletje van te maken, moeten we de speler iets om te doen geven. Ze moeten op de heks klikken om haar te laten verdwijnen. Wanneer er op de heks geklikt wordt, willen we haar laten verdwijnen en een geluidje afspelen.
1. In de Geluiden tab, importeer het geluid electronisch/fairydust.
2. Voeg dit script toe aan de heks:
```scratch
	wanneer op deze sprite wordt geklikt
	verbergen
	start geluid fairydust
```
### Test Je Project
__Klik op het groene vlaggetje__ 
Verdwijnt de heks en wordt het geluid afgespeeld als je op haar klikt?
Sla je project op

##Stap 4: Voeg een score en een timer toe
We hebben een heks, maar nu willen we er een echt spelletje van maken! We willen punten scoren telkens we op de heks klikken, maar we willen ook een tijdslimiet instellen voor ons spelletje. We kunnen een variabele gebruiken voor de score en de timer.

1. Maak een nieuwe Variabele voor alle sprites, genaamd score. Pas dan het script voor de heks aan om deze variabele te laten toenemen wanneer er op geklikt is.
```scratch
	wanneer op deze sprite wordt geklikt
	verbergen
	start geluid fairydust
	verander score met 1
```
2. Ga naar de Stage en maak een nieuwe variabele aan (deze keer enkel voor de Stage) genaamd timer. Voeg een nieuw script toe dat loopt wanneer er op het groene vlaggetje is geklikt om de timer op 30 en de score op 0 te zetten. Gebruik dan een herhaal tot blok om een seconde te wachten en de timer met 1 te verminderen. Dit zou moeten herhalen tot timer gelijk is aan 0. Op dat moment gebruiken we stop alle om het spell te stoppen.
```scratch
	wanneer VLAG wordt aangeklikt
	maak timer 30
	maak score 0
	herhaal tot timer = 0
		wacht 1 tellen
		verander timer met -1
	(einde repeat)
	stop alle
```


### Test Je Project
__Klik op het groene vlaggetje__ 
Sla je project op

### Om te proberen
__Hoe zou je de heks sneller laten vliegen naar mate het spelletje verder gaat?__

__Goed zo, je bent klaar met de basis van het spelletje. Er zijn echter nog een aantal dingen die je kan veranderen aan je spel. Probeer deze uitdaging eens!__
## Uitdaging: voeg meer heksen toe
Als één heks goed is, zijn meer heksen zeker beter! Laten we eens proberen om drie heksen rond te laten vliegen.
1. Dupliceer de heks door er rechts op te klikken in de sprite lijst.
2. Pas voor elke heks de grootte van de sprite aan, zodat de heksen verschillende groottes hebben.
3. Pas voor elke heks de snelheid variabele aan, zodat de heksen rondvliegen aan verschillende snelheden.
4. Verspreid de heksen over het canvas zodat ze niet allemaal op dezelfde plaats vliegen.
### Test Je Project
__Klik op het groene vlaggetje__ 
Bewegen er drie heksen van de ene kant van het scherm naar de andere kant terwijl ze willekeurig verdwijnen en verschijnen én die verdwijnen als je er op klikt?
Sla je project op
### Om te proberen
1. Hoeveel heksen zouden goed zijn voor het spelletje?
2. Kan je de heksen er anders laten uitzien? Je kan ofwel hun kostuums aanpassen, of blokken gebruiken uit het Uiterlijken palet om ze aan te passen.
3. Kan je ervoor zorgen dat de heksen een verschillend aantal punten waard zijn? Wat als we nu eens de snelste (en kleinste) heks 10 punten laten waard zijn?

__Goed zo, je bent klaar, nu kan je genieten van je spelletje!__
Vergeet niet dat je je spelletje kan delen met al je vrienden en je familie door op __Publiceren__ in de menu balk te klikken!