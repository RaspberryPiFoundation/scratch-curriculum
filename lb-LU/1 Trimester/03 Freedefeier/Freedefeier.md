Niveau 1

#Freedefeier

__Aleedung:__
An dësem Projet stelle mer e Freedefeier op, wat iwwert enger Stad ass.

##￼SCHRËTT 1: Stell eng Rakéit op, déi a Richtung vun der Maus flitt

__Looss eis déi verschidde Biller fir d'Spill importéieren__

1. Start en neie Scratch-Projet. Läsch d'Kaz, andeem s du mat der rietser Maustast drop klicks an "Löschen" wiels
2. Ersetz den Hannergrond mat outdoor/city-with-water
3. Benotz den __Neue Figur aus Datei laden__ Knäppchen fir d'Rakéite-Figur bei de Projet dobäizesetzen (benotz de Kostüm Resources/Rocket.png).
4. Maach, dass d'Rakéit verstoppt gëtt wann de grénge Fändel ugeklickt gëtt.

Elo wëlle mer, dass d'Rakéit sech a Richtung vun der Maus beweegt wann s du klicks.

5. Setz een "Wenn Taste Leertaste gedrückt" Kontroll-Block dran, a looss d'Rakéit erschéngen a sech a Richtung vun der Maus beweegen.

```scratch

	Wenn FLAG angeklickt

	verstecke dich

	
	Wenn Taste Leertaste gedrückt
	zeige dich
	gleite 1 Sek. zu x: Maus x-Position y: Maus y-Position
```
		
###Test däi Projet
__Klick op de grénge Fänel, setz deng Maus op d'Bühn an dréck d'Space-Tast.__

Erschéngt d'Rakéit a beweegt se sech a Richtung vun der Maus?
Wat geschitt wann s du d'Maus beweegs an d'Space-Tast nach eng Kéier drécks?

6. Freedefeier beweegt sech net vu Säit zu Säit, also looss eis sécherstellen dass et sech ëmmer vun ënnen erop a Richtung vun der Maus beweegt. Iert mer d'Rakéit uweisen, benotz den "go to"-Block fir hir ze soen sech ënnert den ënneschte Rand vum Schierm ze deplazéieren, awer horizontal op der selwechter Plaz ze bleiwen.

```scratch

	Wenn FLAG angeklickt

	verstecke dich

	
	Wenn Taste Leertaste gedrückt
	gehe zu x: Maus x-Position y: -200
	zeige dich
	gleite 1 Sek. zu x: Maus x-Position y: Maus y-Position
```

###Test däi Projet
__Klick op de grénge Fändel, plazéier deng Maus iwwert der Bühn an dréck d'Space-Tast.__ 
Flitt d'Rakéit vun ënnen erop a Richtung vun der Maus? Wat geschitt wann s du d'Maus beweegs an nach eng Kéier d'Space-Tast drécks?

7. Fir ofzeschléissen, looss eis d'Freedefeier mat der Maus ausléisen amplaz mat der Space-Tast. Fir dat ze maachen kënne mer de Script an e __wiederhole fortlaufend, falls mouse down__ Block abannen.
Tausch duerno den __Wenn Taste Leertaste gedrückt__ Kontroll-Block mat engem __Wenn flag angeklickt__ aus a maach zu gudder Lescht dass d'Rakéiet verstoppt ass wann alles start.

```scratch

	Wenn FLAG angeklickt
	verstecke dich
	wiederhole fortlaufend, falls Maustaste gedrückt??
		gehe zu x: Maus x-Position y: -200
		zeige dich
		gleite 1 Sek. zu x: Maus x-Position y: Maus y-Position
	(Ende wiederhole fortlaufend)
```
###Test däi Projet
__Klick op de grénge Fändel, an dréck d'Maustast iwwert der Bühn. Klick nach eng Kéier op enger anerer Plaz.__ 

###Saache fir auszeprobéieren
1. Versich ze verännere wou d'Rakéit sech hibeweegt iert se a Richtung vun der Maus flitt fir dass se sech an engem klenge Bou beweegt.
2. Versich verschidde Rakéite méi lues oder méi séier ze maache wéi anerer.

Späicher däi Projet.

##SCHRËTT 2: Looss d'Rakéit explodéieren

￼1. Den éischte Schrëtt fir d'Rakéit explodéieren ze loossen ass, fir se e Knall-Toun ofspillen ze loossen (Resources\bang) iert se ufänkt sech ze beweegen, a sech dann nees selwer ze verstoppen esoubal se d'Maus erreecht. Fir en Toun ze importéieren, géi bei de "Klänge"-Tab a klick op "Importieren".

```scratch

	Wenn FLAG angeklickt
	verstecke dich
	wiederhole fortlaufend, falls Maustaste gedrückt??
		gehe zu x: Maus x-Position y: -200
		spiele Klang bang
		zeige dich
		gleite 1 Sek. zu x: Maus x-Position y: Maus y-Position
		verstecke dich
	(Ende wiederhole fortlaufend)
```
2. Als nächst, looss d'Rakéit e Message schécke wann se explodéiert. Mir lauschtere méi spéit op dëse Message.

```scratch

	Wenn FLAG angeklickt
	verstecke dich
	wiederhole fortlaufend, falls Maustaste gedrückt??
		gehe zu x: Maus x-Position y: -200
		spiele Klang bang
		zeige dich
		gleite 1 Sek. zu x: Maus x-Position y: Maus y-Position
		verstecke dich
		sende explode an alle
	(Ende wiederhole fortlaufend)
```
###Test däi Projet
__Klick op de grénge Fändel.__ 
Iwwerpréif dass d'Rakéit e Geräich ofspillt a verstoppt gëtt wa se bei der Maus ukënnt.

3. Importéier eng Nei Figur mat Resources/firework1.png
4. Wa se den "explode"-Message kritt, soll se sech selwer verstoppen a sech dann op d'Positioun vun der Rakéit mat engem "go to"-Block beweegen, sech selwer uweisen a sech dann no enger Sekonn nees verstoppen.

```scratch

	Wenn ich explode empfange

	verstecke dich

	gehe zu x: x-Position von rocket y: y-Position von rocket

	zeige dich

	wait 1 sec

	verstecke dich
```
###Test däi Projet
__Schéiss eng aner Rakéit an d'Loft.__
Gëtt se vun der Explosiouns-Grafik ersat wa se explodéiert?
Wat geschitt wann s du d'Maustast gedréckt häls wann s de d'Maus beweegs? (Keng Angscht, mir korrigéieren dat e bësse méi spéit).

Späicher däi Projet

##￼SCHRËTT 3: Maach all Explosioun eenzegaarteg

1. Elo kënne mer all Explosioun nach méi eenzegaarteg maachen andeem s mer en "Setze Farbe-Effekt"-Block benotzen an e virum Uweisen eng Zoufalls-Fuerf tëscht 1 an 200 wiele loossen.

```scratch

	Wenn ich explode empfange

	verstecke dich

	setze colour-Effekt auf wähle zufällig aus 1 bis 200

	gehe zu x: x-Position von rocket y: y-Position von rocket

	zeige dich

	wait 1 sec

	verstecke dich
```

###Test däi Projet
__Klick op de grénge Fändel.__ 

Huet all Explosioun eng aner Fuerf?

2. Looss eis eng Rei verschidde méiglech Explosiouns-Grafiken als "Kostümer" dobäisetzen. An zwar mat de Biller Resources/firework2.png a Resources/firework3.png. Duerno kënne mer fir all Rakéit tëscht hinne wiesselen, iert se ugewise ginn.

###Test däi Projet
__Klick op de grénge Fändel.__ 

Huet all Rakéit eng aner Explosiouns-Grafik?

3. Fir ofzeschléissen, looss eis d'Explosioun mat der Zäit wuesse loossen amplaz dass se just erschéngt. Amplaz eng Sekonn ze waarden, setzt d'Gréisst vun der Figur op 5% iert mer se weisen, an esoubal se gewise gëtt, setz d'Gréisst mat engem "Repeat"-Block 50 mol ëm 2 erop.

```scratch

	Wenn ich explode empfange

	verstecke dich

	setze colour-Effekt auf wähle zufällig aus 1 bis 200

	gehe zu x: x-Position von rocket y: y-Position von rocket

	setze Größe auf 5%

	zeige dich
	
	wiederhole 50 mal
		ändere Größe um 2
	(Ende repeat)

	verstecke dich
```
###Test däi Projet
__Klick op de grénge Fändel.__ 

Vergréissert sech d'Explosiouns-Grafik vum Zentrum vun der Rakéit aus a wiisst da lues a lues?

###Saache fir auszeprobéieren
Firwat net probéieren all Explosioun nach méi eenzegaarteg ze maachen, andeem s de d'Gréisst, d'Vitesse an d'Wuesstumsvitess vun all Explosioun veränners?

Späicher däi Projet

##SCHRËTT 4: De Broadcast-Problem korrigéieren
Erënners de dech drun, dass mer virdrun e Problem mam Gedréckt hale vun der Maustast haten?
Dat geschitt well wann d'Rakéit d'Explosioun als Message schéckt, gëtt d'Falls-Schläif direkt widderholl an een aneren "explosion"-Message schéckt, iert dee leschte fäerdeg ugewise gouf.


1. Fir dat ze korrigéiere kënne mer de "broadcast"-Block mat engem "sende und an alle wait"-Block ersetzen. Op dës Manéier widderhëlt d'Schläif sech net bis d'Explosioun fäerdeg explodéiert ass.

```scratch

	Wenn FLAG angeklickt
	verstecke dich
	wiederhole fortlaufend, falls Maustaste gedrückt??
		gehe zu x: Maus x-Position y: -200
		spiele Klang bang
		zeige dich
		gleite 1 Sek. zu x: Maus x-Position y: Maus y-Position
		verstecke dich
		sende explode an alle und wait
	(Ende wiederhole fortlaufend)
```
###Test däi Projet
__Klick de grénge Fändel, hal d'Maustast gedréckt a beweeg d'Maus ronderëm d'Bühn.__ 

Erschéngt d'Explosiouns-Grafik op der richteger Plaz an zur richteger Zäit?

Späicher däi Projet