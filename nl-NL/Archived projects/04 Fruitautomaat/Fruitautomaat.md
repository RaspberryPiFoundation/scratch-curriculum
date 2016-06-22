Niveau 2

#Fruitautomaat

__Inleiding:__Dit is een spel met daarin drie sprites die van uiterlijk veranderen. Je moet er voor zorgen dat ze stoppen wanneer ze het zelfde plaatje laten zien (net zoals bij een fruitautomaat!).
##￼STAP 1: Maak een sprite die van uiterlijk verandert
__We importeren de verschillende plaatjes voor dit spel__1. Open een nieuw scratch-project. Verwijder de kat door er met je rechter muistoets op te klikken en Verwijder te selecteren2. Importeer een nieuwe sprite.3. Kies een plaatje: maakt niet uit uit welke map. Wij hebben things/bananas1 gebruikt, maar je kunt ieder plaatje dat je wilt gebruiken.4. Klik op de tab Uiterlijken en importeer nog twee plaatjes, zodat je er in totaal drie hebt (wij hebben animals/bee1 en things/lego gebruikt, maar jij kunt gebruiken wat je wilt).__We hebben nu een aantal uiterlijken, en nu willen we dat de sprite wisselt tussen deze drie plaatjes.__##STAP 2: Het plaatje laten veranderen

1. Klik op de Scripts-tab.2. Klik Besturen, en sleep een wanneer vlag wordt aangeklikt naar het scripts-scherm. Deze wordt aangezet wanneer we op de groene vlag klikken. 3. Voeg een herhaal toe en klik hem vast onder wanneer vlag wordt aangeklikt. 4. Klik rechtsboven op de groene vlag. Zie je dat er een witte rand om je script komt te staan? Dat betekent dat het script loopt doordat we op de groene vlag hebben geklikt, die dit script bestuurt. 5. Klik nu op Uiterlijken en sleep een volgende uiterlijk in het script 6. Hoe kunnen we dit een beetje vertragen, zodat het niet zo snel verandert? Klik op Besturen en sleep een wacht 1 tellen naar binnen7. Pas de tijd aan tot de plaatjes met een sneller tempo veranderen (0.1 tellen ziet er goed uit). Wat zou er gebeuren als we dat wacht-blok niet hadden? 

```scratch
	wanneer VLAG wordt aangeklikt	herhaal		
		volgende uiterlijk
		wacht 0.1 tellen
	(einde herhaal)
```

###Test Je Project__Klik op de groene vlag.__ 
Veranderen de uiterlijken met een redelijke snelheid?
Sla je project op
###Om te proberen
Verander de tijd in het wacht-blok. Wanneer wordt het spel te makkelijk, of juist te moeilijk?##￼STAP 3: Zorg er voor dat het veranderen stopt als je er op klikt
Hartstikke mooi dat deze sprite steeds van uiterlijk verandert, maar hoe zorgen we er voor dat hij stopt met veranderen als we er op klikken?1. Maak een nieuwe variabele door te klikken op Variabelen en dan een nieuwe variabele maken. Noem hem gestopt en maak hem voor alle sprites. Haal dan het vinkje in het vakje voor gestopt weg, zodat hij niet op je scherm getoond wordt.  2. Nu gaan we er voor zorgen dat de variabele gestopt 1 wordt als iemand op het plaatje klikt. Sleep uit Besturen een wanneer sprite1 wordt aangeklikt op je scripts-scherm. Sleep dan uit Variabelen een maak gestopt 0 op het scherm, en verander de 0 in een 1. 
3. De volgende stap is dat we het plaatje laten ophouden met veranderen op het moment dat de variabele gestopt gelijk is aan 1. Klik op Besturen, en verander de herhaal loop in een herhaal als. Daarna sleep je uit Functies een groene = functie in het herhaal als blok. In het = blok sleep je een gestopt variabele en typ je een 0
4. Laatste stap: voeg een maak gestopt 0 toe onder de wanneer vlag wordt aangeklikt

###Test Je Project__Klik op de groene vlag, wacht even, en klik dan op de sprite.__ 

Verandert hij van uiterlijk voordat je er op klikt? 
Stopt hij met veranderen als je er op klikt?
__Start de sprite nog een keer.__ Stopt hij als je met je muis over het plaatje gaat, zonder te klikken? Stopt de sprite als je op een andere plaats op het scherm klikt? Als je ergens anders in Scratch klikt? Of buiten Scratch?
Sla je project op
##Stap 4: De andere sprites maken
__Nu moeten we de andere sprites maken, zodat we ons spel kunnen spelen!__1. Maak een kopie van de sprite (Sprite1) door er met je rechter muistoets op te klikken rechtsonder.2. Kopieer hem nog een keer zodat je 3 sprites op het scherm hebt. 3. Verplaats de sprites zodat ze op een rijtje naast elkaar staan. Maak ze iets kleiner als je niet genoeg plaats hebt.
###Test Je Project__Klik op de groene vlag.__ Als het goed is veranderen alle sprites van uiterlijk. Probeer ze allemaal op het zelfde plaatje te stoppen!
Sla je project op
###Om te proberen
Als je het spel start terwijl je het net geladen hebt, laten alle sprites het zelfde uiterlijk zien en veranderen ze tegelijk. Hoe kun je er voor zorgen dat ze een willekeurige plaatje gebruiken om op te starten als je op de groene vlag klikt? Hint: probeer een willekeurig uiterlijk voor iedere sprite te kiezen wanneer het spel begint. __Goed gedaan als je de basis van het spel voor elkaar hebt gekregen. Maar er is meer wat je kunt doen met dit spel. Probeer deze uitdagingen eens! __
##Uitdaging 1: Maak het spel moeilijker
Verander de moeilijkheid van het spel. De makkelijkste manier om dat te doen is de uiterlijken sneller laten veranderen. Probeer of je iets spannenders kunt bedenken. Een paar ideeen die je kunt proberen:1. Verander het aantal uiterlijken dat iedere sprite heeft.2. Geef sommige sprites een uiterlijk dat zij alleen hebben.3. Verander de snelheid waarmee iedere sprite van uiterlijk wisselt.4. Laat iedere sprite naar een willekeurig uiterlijk springen, niet steeds naar de volgende. 
__Veel plezier met je eigen dingen bedenken!__Denk er iedere keer als je iets verandert over na of deze verandering het spel makkelijker of moelijker maakt. Is het spel nu te makkelijk of te moeilijk? Hoe kun je de moeilijkheid zo aanpassen dat het precies goed is?
##Uitdaging 2: Maak het spel makkelijker en moeilijker als je langer speeltAls verschillende mensen je spel spelen, zullen ze andere dingen goed of minder goed kunnen.   __Hoe kun je er voor zorgen dat je spel zich in moeilijkheid aanpast aan het niveau van je spelers?__Een manier waarop je dat kunt doen is om __de snelheid aan te passen waarmee de uiterlijken wisselen__. Je kunt hiervoor een variabele die __vertraag__ heet gebruiken, om het wacht-blok van iedere sprite aan te passen. Als de speler de ronde wint, kan vertraag een beetje verkleind worden (om het spel moeilijker te maken). Als de speler de ronde verliest, kun je vertraag iets groter maken (om het spel makkelijker te maken).
##￼Uitdaging 3: Controleer of alle sprites gestopt zijn op het zelfde uiterlijk
__Het doel van het spel is om alle sprites te laten stoppen op het moment dat ze het zelfde uiterlijk hebben. Het zou mooi zijn als het scherm kon controleren of alle sprites op het zelfde uiterlijk gestopt zijn toen je klikte, en je dan kon laten weten of je gewonnen of verloren had.__
De eerste stap is dat dat het scherm moet weten of de speler klaar is. We kunnen dit doen door het scherm te laten checken of alle sprites opgehouden zijn met bewegen als we op een van de sprites geklikt hebben. Ga al je sprites langs en verander bij allemaal de wanneer sprite# wordt aangeklikt blokken zodat ze een nieuwe zend signaal bevatten, checkForEnd.Het Scherm kan op dit signaal reageren en controleren of het spel voorbij is door te controleren of de gestopt-variabelen van alle drie de sprites op 1 gezet zijn. Dat doen ze door een x-positie van Sprite blok te gebruiken en de "x positie" in gestopt te veranderen. Als alle drie de sprites een gestopt-waarde van 1 hebben, weten we dat het spel voorbij is en kunnen we checken of de speler gewonnen heeft. Om dit te doen, kunnen we het zelfde x positie van Sprite blok gebruiken, maar in plaats van te kijken naar de variabele gestopt, kijken we naar het uiterlijk # en checken we of Sprite1 het zelfde uiterlijk heeft als Sprite2 en of Sprite2 het zelfde uiterlijk heeft als Sprite3. Om dit te doen, heb je een blok nodig dat iedere gestopte variabele controleert, met daarin een  als … anders blok om te kijken of de speler gewonnen of verloren heeft door alle uiterlijken te vergelijken. 
Vanaf dit punt kun je het resultaat van het spelletje laten weten met zend signaal, en hierop reageren met een andere sprite. Misschien kun je Felix gebruiken om de speler te feliciteren of te troosten? 
__Goed gedaan als je klaar bent, nu kun je lekker gaan spelen! __En vergeet niet dat je het spel ook kun delen met je vrienden en je familie door op de  __Publiceren__ knop op de menubalk te klikken!