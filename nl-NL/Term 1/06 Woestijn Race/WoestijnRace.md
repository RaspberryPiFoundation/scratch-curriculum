Level 2

#Woestijn Race

__Introductie:__ 
Dit is een spel voor twee spelers, waarbij je een papegaai en een leeuw laat racen. Elke speler moet zo veel mogelijk op een bepaalde toets drukken om zijn dier zo snel mogelijk te laten gaan. De eerste die de rand van het scherm bereikt, is gewonnen.


##￼STAP 1: Maak de omgeving en voeg sprites toe

1. Selecteer je Stage en plaats de achtergrond van de woestijn. En vink de onderstaande vakjes uit. 
2. Voeg een nieuwe sprite toe, selecteer de leeuwen sprite die je in de map dieren vindt
3. Voeg nog een sprite toe, selecteer de papegaaien sprite die je in de map dieren vindt.



##STAP 2: Laat de leeuw en de papegaai bewegen


Je wil dat de sprite beweegt als je een toets indrukt.


1. Eerst selecteer je de sprite van de leeuw en laat die 4 stappen bewegen als je de ‘L’ toest indrukt.

```scratch
	wanneer l wordt ingedrukt
	neem 4 stappen
```

2. Vervolgens Next, selecteer je de sprite van de papegaai en laat die 4 stappen bewegen als je de 'A' toest indrukt.

```scratch
	wanneer a wordt ingedrukt
	neem 4 stappen
```

###Test Je Project
__Klik op het groene vlaggetje__ 
Bewegen de leeuw en de papegaai als je de 'L' en 'A' toetsen indrukt?

Sla je project op.


##￼STAP 3: De race laten beginnen

Je moet natuurlijk een manier hebben om de race te laten beginnen en je moet kunnen zien wie gewonnen heeft.
__Eerst maken we een start knop.__

1. Voeg een nieuwe sprite toe, selecteer de leeuwen sprite die je in de map "dingen" vindt.
2. Pas het uiterlijk aan van de knop, voeg de tekst 'start' toe en klik op OK. Verplaats de sprite naar het midden van de stage.
3. Nu voeg je een script toe dat de sprite laat zien vanaf dat het programma loopt:

```scratch
	wanneer VLAG wordt aangeklikt
	verschijn
```
4. Nu wil je nog dat de knop aftelt vanaf 3 en ga zegt. En de knop moet verdwijnen als je erop klikt. Voeg dit script toe:

```scratch
	als StartRace wordt aangeklikt
	zeg 1 tellen 3
	zeg 1 tellen 2
	zeg 1 tellen 1
	zeg 1 tellen Ga!
	verdwijn
```
###Test Je Project
__Klik op het groene vlaggetje__ 

Als je de start knop aanklikt, begint het dan af te tellen tot aan de start van de race, alvorens te verdwijnen?

Sla je project op.

Je wil enkel dat de racers beginnen te bewegen nadat de race is gestart. En je wil weten wanneer de race is beëindigd, dus je hebt een variabele nodig om die informatie bij te houden.

5. Voeg een variabele toe voor alle sprites. Deze noem je racing. Vink het vakje ernaast uit, zodat deze niet zichtbaar is op de stage.
6. Laat nu racing op nul zetten bij aanvang van het project. Pas nu je wanneer VLAG wordt aangeklikt script aan naar het onderstaande:

```scratch

	wanneer VLAG wordt aangeklikt
	verschijn
	maak racing 0
```
7. Vervolgens zet je de racing variabele op 1 als het aftellen voor de start is beëindigd.
8. Nu moet je ervor zorgen dat de leeuw en de papegaai niet bewegen, tenzij de varialbele racing 1 bedraagt.

Klik op de sprite van de papegaai. __Voeg een Besturen blok toen aan het script__ dewelke enkel toelaat dat de papegaai beweegt indien __racing = 1__.

```scratch

	wanneer a wordt ingedrukt
	als racing = 1
		neem 4 stappen
	(eindig als)
```
9. Doe nu hetzelfde voor de sprite van de leeuw.

###Test Je Project
__Klik op het groene vlaggetje__

Bewegen de leeuw en de papegaai enkel nadat het aftellen is beëindigd?

Je wil weten wie de race wint en je wu-il dit ook kunnen wissen om opnieuw te kunnen racen..

##￼STAP 4: De race beëindigen

1. Voeg een blok toe aan het script van de papegaai dewelke de varialbele racing op 0 zet eens de sprite de rand van het scherm raakt.

```scratch

	wanneer a wordt ingedrukt
	als racing = 1
		neem 4 stappen
		als raak ik rand?
			maak racing 0
		(eindig als)
	(eindig als)
```
2. Nu wil je nog dat de papegaai laat weten of hij de race wint. Neem een geluid op voor de sprite van de papegaai dat zal worden afgespeeld indien de papegaai wint.
Klik op __geluiden__ en neem vervolgens het geluid op van de winnende papegaai!
3. Nu voeg je blokken toe die het geluid afspelen van de winnende papegaai:

```scratch

	wanneer a wordt ingedrukt
	als racing = 1
		neem 4 stappen
		als raak ik rand?
			maak racing 0
			start geluid neemt op1
			zeg 3 tellen De papegaai wint!
		(eindig als)
	(eindig als)
```
4. Herhaal deze stappen voor de leeuw.

###Test Je Project
__Klik op het groene vlaggetje__

Kan je op de start knop drukken en vervolgens racen met de ‘A’ en ‘L’ toetsen?
Spelen de sprites hun overwinningsgeluid? En vertellen ze dat ze de race hebben gewonnen als ze het einde hebben bereikt?

Sla je project op.

##￼STAP 5: Het spel resetten

Nadat de race is beëindigd, moeten we de andere sprites vertellen dat er gewonnen is en het spel terugzetten zodat er opnieuw gespeeld kan worden.

__Je moet de winnende sprite laten zenden dat die gewonnen is.__

1. Klik op de sprite van de papegaai.
Voeg een blok toe die “einde” zendt nadat de sprite heeft laten weten dat die gewonnen is.

```scratch

	wanneer a wordt ingedrukt
	als racing = 1
		neem 4 stappen
		als raak ik rand?
			maak racing 0
			start geluid neemt op1
			zeg 3 tellen De papegaai wint!
			send signaal einde
		(eindig als)
	(eindig als)
```
2. Nu moet je nog een nieuw script toevoegen dat controleert of einde wordt uitgezonden en dat ervoor zorgt dat de papegaai terug naar de start wordt verplaatst. Wat gebeurt er nu als je waarde van x wijzigt?

```scratch

	wanneer ik signaal einde ontvang
	maak x -175
```
3. Voeg nu ook een script toe aan de leeuw. Test dit met verschillende x waarden om zo zeker te zijn dat de leeuw en de papegaai mooi uitgelijnd staan aan de start.
4. Je wil ook dat de leeuw en de papegaai op dezelfde positie staan als het project begint af te spelen, dus voeg nog een script toe dat ze naar de start brengt als je op het vlaggetje klikt.

```scratch

	wanneer VLAG wordt aangeklikt
	maak x -175
```
5. Klik nu op de sprite van de knop en voeg een script toe dat verschijnt als het signaal einde wordt ontvangen.
￼￼￼￼￼￼￼￼￼￼
###Test Je Project
__Klik op het groene vlaggetje__


Tracht eens te racen tegen een vriend. Eén van julie zal de papegaai laten racen door op de ‘A’ te drukken en de andere laat de leeuw racen door op de ‘L’ te drukken. Lukt dit??

Sla je project op.

##￼Uitdaging: Voeg een extra boost toe

* __Tracht boost functie toe te voegen__ één die je maar één keer per race kan gebruiken en die de papegaai of de leeuw __30 stappen in 1 keer__ laat bewegen.
* __Voeg een nieuw uiterlijk toe__ één waarbij er vuur uit de sprite komt en laat dit verschijnen als de boost wordt ingedrukt.
* __Creëer een nieuw geluid__ dat afspeelt als de boost functie wordt ingedrukt.
￼

###Test Je Project

Sla je project op.


__Goed gedaan! Je bent klaar en je kan nu je eigen spel spelen!__
Vergeet niet dat je je spel kan delen met al je vrienden en familie door te klikken op __Publiceren__ in de menubalk!