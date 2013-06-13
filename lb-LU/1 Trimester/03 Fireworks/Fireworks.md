Niveau 1

#Freedefeier

__Aleedung:__
An dësem Projet erstelle mer e Freedefeier dat iwwert enger Stad ugewise gëtt.
##￼SCHRËTT 1: Erstell eng Rakéit déi a Richtung vun der Maus flitt

__Looss eis déi verschidde Biller fir d'Spill importéieren__

1. Start en neie Scratch-Projet. Läsch d'Kaz andeem s du mat der rietser Maustast drop klicks an "Löschen" wiels
2. Ersetz den Hannergrond mat outdoor/city-with-water
3. Benotz den __new sprit from file__ Knäppchen fir d'Rakéite-Figur bei de Projet dobäizesetzen (benotz de Kostüm Resources/Rocket.png).
4. Maach dass d'Rakéit verstoppt gëtt wann de grénge Fändel ugeklickt gëtt.

Elo wëlle mer dass d'Rakéit sech a Richtung vun der Maus beweegt wann déi geklickt gëtt.

5. Setz een "when space key pressed" Kontroll-Block dran, an looss d'Rakéit erschéngen an a sech a Richtung under vun der Maus beweegen.

```scratch

	when FLAG clicked

	hide

	
	when space key pressed
	show
	glide 1 secs to x: mouse x y: mouse y
```
		
###Test däi Projet
__Klick op de grénge Fänel, plazéier deng Maus op d'Bühn an dréck d'Space-Tast.__

Erschéngt d'Rakéit a beweegt se sech a Richtung vun der Maus?
Wat geschitt wann s du d'Maus beweegs an d'Space-Tast nach eng Kéier drécks?

6. Freedefeier beweegt sech net vu Säit zu Säit, also looss eis sécherstellen dass et sech ëmmer vun ënnen erop a Richtung vun der Maus beweegt. Bevir mer d'Rakéit uweisen, benotz den "go to"-Block fir hir ze soen sech ënnert den ënneschte Rand vum Schierm ze deplazéieren, awer horizontal op der selweschter Plaz ze bleiwen.

```scratch

	when FLAG clicked

	hide

	
	when space key pressed
	go to x: mouse x y: -200
	show
	glide 1 secs to x: mouse x y: mouse y
```

###Test däi Projet
__Klick op de grénge Fändel, plazéier deng Maus iwwert der Bühn an dréck d'Space-Tast.__ 
Flitt d'Rakéit vun ënnen erop a Richtung vun der Maus? Wat geschitt wann s du d'Maus beweegs an nach eng Kéier d'Space-Tast drécks?

7. Fir ofzeschléissen, looss eis d'Freedefeier mat der Maus ausléisen amplaz mat der Space-Tast. Fir dat ze maachen kënne mer de Script an e __forever if mouse down__ Block abannen.
Tausch duerno den __when space key pressed__ Kontroll-Block mat engem __when flag clicked__ aus maach zu gudder Lescht dass d'Rakéiet verstoppt ass wann alles start.

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		show
		glide 1 secs to x: mouse x y: mouse y
	(end forever)
```
###Test däi Projet
__Klick op de grénge Fändel, an dréck d'Maustast iwwert der Bühn. Klick nach eng Kéier op enger anerer Plaz.__ 

###Saache fir auszeprobéieren
1. Versich ze verännere wou d'Rakéit sech hibeweegt bevir se a Richtung vun der Maus flitt fir dass se sech an engem klenge Bou beweegt.
2. Versich verschidde Rakéite méi lues oder méi séier ze maache wéi anerer.

Späicher däi Projet.

##SCHRËTT 2: Looss d'Rakéit explodéieren

￼1. Den éischte Schrëtt fir d'Rakéiet explodéieren ze loossen ass fir se e Knall-Toun ofspillen ze loossen (Resources\bang) bevir se ufänkt sech ze beweegen, a sech dann nees selwer ze verstoppen esoubal se d'Maus erreecht. Fir en Toun ze importéieren, géi bei de "Sounds"-Tab a klick op "Import".

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		play sound bang
		show
		glide 1 secs to x: mouse x y: mouse y
		hide
	(end forever)
```
2. Als nächst, looss d'Rakéiert e Message schécke wann se explodéiert. Mir lauschtere méi spéit op dëse Message.

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		play sound bang
		show
		glide 1 secs to x: mouse x y: mouse y
		hide
		broadcast explode
	(end forever)
```
###Test däi Projet
__Klick op de grénge Fändel.__ 
Stell sécher dass d'Rakéit e Geräich ofspillt a verstoppt gëtt wa se bei der Maus ukënnt.

3. Importéier eng Nei Figur mat Resources/firework1.png
4. Wa se den "explode"-Message kritt soll se sech selwer verstoppen a sech dann op d'Positioun vun der Rakéit mat engem "go to"-Block beweegen, sech selwer uweisen a sech dann no enger Sekonn nees verstoppen.

```scratch

	when I receive explode

	hide

	go to x: x position of rocket y: y position of rocket

	show

	wait 1 sec

	hide
```
###Test däi Projet
__Schéiss eng aner Rakéit an d'Loft.__
Gëtt se vun der Explosiouns-Grafik ersat wa se explodéiert?
Wat geschitt wann s du d'Maustast gedréckt häls während s de d'Maus beweegs? (Keng Angscht, mir korrigéieren dat e bësse méi spéit).

Späicher däi Projet

##￼STEP 3: Maach all Explosioun eenzegaarteg

1. Elo kënne mer all Explosioun nach méi eenzegaarteg maachen andeem s mer en "set color effect"-Block benotzen an e virum uweisen eng Zoufalls-Fuerf tëscht 1 an 200 wiele loossen.

```scratch

	when I receive explode

	hide

	set colour effect to pick random 1 to 200

	go to x: x position of rocket y: y position of rocket

	show

	wait 1 sec

	hide
```

###Test däi Projet
__Klick op de grénge Fändel.__ 

Huet all Explosioun eng aner Fuerf?

2. Looss eis eng Rei verschidde méiglech Explosiouns-Grafiken als "Kostümer" dobäisetzen. An zwar mat de Biller Resources/firework2.png a Resources/firework3.png. Duerno kënne mer fir all Rakéit tëscht hinne wiesselen, bevir se ugewise ginn.

###Test däi Projet
__Klick op de grénge Fändel.__ 

Huet all Rakéit eng aner Explosiouns-Grafik?

3. Fir ofzeschléissen looss eis d'Explosioun mat der Zäit wuesse loossen amplaz dass se just erschéngt. Amplaz eng Sekonn ze waarden, setzt d'Gréisst vun der Figur op 5% bevir mer se weisen, an esoubal se gewise gëtt, incrementéier d'Gréisst mat engem "Repeat"-Block 50 mol ëm 2.

```scratch

	when I receive explode

	hide

	set colour effect to pick random 1 to 200

	go to x: x position of rocket y: y position of rocket

	set size to 5%

	show
	
	repeat 50
		change size by 2
	(end repeat)

	hide
```
###Test däi Projet
__Klick op de grénge Fändel.__ 

Vergréissert sech d'Explosiouns-Grafik vum Zentrum vun der Rakéit aus a wiisst da lues a lues?

###Saache fir auszeprobéieren
Firwat net probéieren all Explosioun nach méi eenzegaarteg ze maachen, andeem s de d'Gréisst, d'Vitesse an d'Wuesstumsvitess vun all Explosioun veränners?

Späicher däi Projet

##SCHRËTT 4: De Broadcast-Problem korrigéieren
Erënners de dech drun dass mer virdrun e Problem mam gedréckt hale vun der Maustast haten?
Dat geschitt well wann d'Rakéit d'Explosioun als Message schéckt, gëtt d'If-Schläif direkt widderholl an een aneren "explosion"-Message schéckt, bevir dee leschte fäerdeg ugewise gouf.


1. Fir dat ze korrigéiere kënne mer de "broadcast"-Block mat engem "broadcast and wait"-Block ersetzen. Op dës Manéier widderhëlt d'Schläif sech net bis d'Explosioun fäerdeg explodéiert ass.

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		play sound bang
		show
		glide 1 secs to x: mouse x y: mouse y
		hide
		broadcast explode and wait
	(end forever)
```
###Test däi Projet
__Klick de grénge Fändel, hal d'Maustast gedréckt a beweeg d'Maus ronderëm d'Bühn.__ 

Erschéngt d'Explosiouns-Grafik op der richteger Plaz an zur richteger Zäit?

Späicher däi Projet