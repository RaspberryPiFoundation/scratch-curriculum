Niveau 2

#Wüstecourse

__Aleedung:__
Dëst Spill ass ee Spill fir 2 Spille wou ee Papagei an ee Léif eng Course duerch d'Wüst maachen. All Spiller soll eng Taste esou schnell wéi méiglech drécken fir säin Deier virun ze bewegen. Den éischten Spiller deen um Bord vun der Bühn ass huet gewonnen.

##1. SCHRATT: D'Bühn erschafen an d'Figuren dobäisetzen

1. Wiel d'Bühn aus an setz de Wüstenhannergrond dobäi a kräizt d'Këscht heirënner un:
2. Setz eng nei Figur dobäi, wiel de Léif aus deen s du am Déiere Dossier fënns.3. Setz eng aner Figur dobäi, wiel de Papagei aus deen s de am Déiere Dossier fënns.##2. Schratt: D'Figuren bewegen
Mir wëllen d'Figur bewegen wa mer eng Taste drécken.1. T éischt wiel d'Figur vum Léif aus a stell et esou an dass de Léif sech 4 Schrëtt beweegt wann s de d'L' Taste drécks.
```scratch

	Wenn Taste l gedrückt
	gehe 4er-Schritt
```
2. Wiel als nächst de Papagei aus a setz hien esou op dass 4 Schrëtt gemeet gi wann s de d'A' Taste drécks.

```scratch

	Wenn Taste a gedrückt
	gehe 4er-Schritt
```

###Test däi Projet__Klick op de grénge Fändel__ 
Bewegen sech de Léif an den Papagei iwwer de Bildschierm wann s de den 'A' an den 'L' drécks?
Späicher däi Projet
##3. Schratt: D'Course starte
Mir brauchen ee Wee fir d'Course ze Starte an ze wësse ween gewonnen huet.  __T éischt erschafe mer ee Startknapp.__
1. Setz eng nei Figur vun enger Datei. Wiel d'Figur vum Knäppchen deen am "things"/"Saachen" ass.2. Veränner de Kostüme vum Knäppchen, füg den Text 'Start' dobäi a klick OK. Réckel d'Figur an d'Mëtt vun der Bühn.3. Setz ee Skript dobäi deen d'Figur uweist wann de Projet gestart gëtt:
```scratch

	Wenn FLAG angeklickt
	zeige dich
```4. Elo wëlle mer dass de Knäppchen erof zielt vun 3 op 0 a GO uweist a verschwënnt wann en geklickt gëtt. Setz een anere Skript wéi dëse bäi:
```scratch

	Wenn StartRace angeklickt
	sage 3 für 1 Sek.
	sage 2 für 1 Sek.
	sage 1 für 1 Sek.
	sage GO! für 1 Sek.
	verstecke dich
```
###Test däi Projet__Klick op de grénge Fändel__ 
Wann s de den Startknapp drécks, zielt en erof a start d'Course befiert en verschwënnt?
Späicher däi Projet

Mir wëllen nëmmen dass eis Figuren sech bewegen nodeems d'Course gestart ginn ass a mir wëllen wëssen wéini d'Course fäerdeg ass, dofir brauche mer eng Variabel fir dës Informatiounen ze späicheren.
5. Sëtz eng Variabel fir all Figur dobäi déi *Course* heescht. Klick d'Kräiz ewech wat nieft der Figur ass esou dass se net op der Bühn ugewise gëtt.
6. Setz elo d'Variabel *Course* op 0 wann de Projet fir t éischt gestart gëtt. Veränner d'Variabel wann de Fändel geklickt gëtt wéi follegt:
```scratch

	Wenn FLAG angeklickt
	zeige dich
	setze racing auf 0
```
7. Als nächst, setz d'Variabel *Course* op 1 wann de start Countdown fäerdeg ass.
8. Elo soll den Léif an de Papagei sech nëmme bewegen wann d'Variabel *Course* op 1 gesat ass. Klick op d'Figur vum Papagei. __Sëtz ee Kontrollblock bei de Skript__ wat et nëmmen dem Papagei erlaabt sech ze beweegen wann __Course = 1__.
```scratch

	Wenn Taste a gedrückt
	if racing = 1
		gehe 4er-Schritt
	(end if)
```
9. Mach elo dat nämlecht mam Léif.
###Test däi Projet__Klick op de grénge Fändel__ 
Beweegt de Léif oder de Papagei sech eréischt nodeems de Countdown fäerdeg ass?Mir wëllen wësse ween d'Course gewënnt an alles zerécksetzen wann et fäerdeg ass esou dass ee nees ka frësch spille.##4. Schratt: D'Courss ophale

1. Füg ee Block bei dem Papagei sengem Skript bäi dee d'Variabel *Course* op 0 setzt wann d'Figur de Rand vum Bildschierm beréiert.```scratch

	Wenn Taste a gedrückt
	if racing = 1
		gehe 4er-Schritt
		falls wird  berührt?edge?
			setze racing auf 0
		(end if)
	(end if)
```
2. Elo wëlle mer dass de Papagei eis Bescheed seet wann hien d'Course gewonnen huet. Huel ee neien Toun fir d'Figur vum Papagei op dee mir ofspille wann de Papagei gewonnen huet. Klick __sounds__ an huel den Toun vum Papagei dee gewënnt op.
3. Setz elo d'Bléck déi den Toun ofspillen déi mer opgeholl hunn an déi de Papagei seet wann hie gewonnen huet:
```scratch

	Wenn Taste a gedrückt
	if racing = 1
		gehe 4er-Schritt
		falls wird  berührt?edge?
			setze racing auf 0
			spiele Klang recording1
			say The Parrot Wins! for 3 secs
		(end if)
	(end if)
```
4. Widderhuelt dës Schrëtt fir de Léif
###Test däi Projet__Klick op de grénge Fändel__ 

Kanns du de Start Knäppchen drécken a mat den 'A' an 'L' Tasten d'Figure bewegen?
Maachen d'Figuren di richteg Téin wann se gewannen a weisen se der dat och un wann d'Course fäerdeg ass?Späicher däi Projet
##5. Schratt: Spill zerécksetzen
Nodeems d'Course fäerdeg ass musse mer den aneren Figuren soen dass mer gewonnen hunn an d'Spill zerécksetzen esou dass mer nees frësch spille kënnen.
__D'Gewënner Figur soll verbreeden dass se gewonnen huet.__1. Klick op d'Figur vum Papagei.
Setz de Block deen "finished" verbreet nodeems d'Figur gesot huet dass se gewonnen huet.
```scratch

	Wenn Taste a gedrückt
	if racing = 1
		gehe 4er-Schritt
		falls wird  berührt?edge?
			setze racing auf 0
			spiele Klang recording1
			say The Parrot Wins! for 3 secs
			sende finished an alle
		(end if)
	(end if)
```
2. Elo brauche mer nach ee Skript deen nolauschtert wann d'Iwwerdroung erakënnt an de Papagei zeréck un den Depart schéckt. Wat geschitt wann s de de wäert vun x änners?

```scratch

	Wenn ich finished empfange
	setze x auf -175
```
3. Setze elo de nämmlechten Skript fir de Leif dobäi. Test di verschidde Wäerter vun x fir sécher ze sinn dass de Leif an de Papagei op der nämmlechter héicht beim Depart sinn.
4. Mir wëllen ausserdeem all béid an der nämmlechter Positioun hunn wann de Projet leeft, fléck ee neien Skript bei deng Figuren dobäi deen se zeréck un den Depart bréngt wa mer op de Fändel klicke.
```scratch

	Wenn FLAG angeklickt
	setze x auf -175
```
5. Klick elo op de Knäppchen "sprite" a setz ee Skript dobäi deen der weist wann et de Message "finished" krut.
###Test däi Projet__Klick op de grénge Fändel__ 
Kanns de eng Course géint ee Kolleg maachen wou den een den 'L' fir de Leif benotzt an deen aneren den 'A' fir de Papagei? 
Späicher däi Projet
##Erausfuerderung: Ee Booster dobäi setzen

* __Versich ee Booster dobäizesetzen__ deen s du ee mol pro Course benotzen kanns an deen de Léif oder de Papagei __30 Schrëtt an engem Coup__ beweegt.
* __Sëtz ee neien Kostüme dobäi__ wou feier hannert all Figur eraus kënnt an ugewisen gëtt wann de Booster aktiv ass.
* __Erstell een aneren Toun__ dee beim Booster benotzt gëtt.
###Test däi ProjetSpäicher däi Projet
__Bravo! Elo bass du fäerdeg an du kanns dech mat dengem neie Spill ameséieren!__
    Vergiess net, dass du däi Spill all denge Kollegen an denger Famill weise kanns. Klick dozou op __Veröffentlichen!__ ganz uewen am Menü.