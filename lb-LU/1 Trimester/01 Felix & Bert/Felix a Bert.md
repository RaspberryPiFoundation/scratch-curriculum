Niveau 1

#De Felix & de Bert

__Aleedung:__
Mir programméieren e Fänkches-Spill mat der Kaz Felix an der Maus Bert. Du steiers de Bert mat denger Maus a versichs net vum Felix gefaangen ze ginn. Wat s du dech méi laang net vun him erwësche léis, wat s du méi Punkte kriss. Mä pass op dass hien dech net fänkt, soss verléiers du Punkten!

##￼1. SCHRATT: De Felix verfollegt de Mauszeiger
1. Fänk en neie Projet un. Kräiz u wat s du scho gemeet hues:
￼￼￼2. Klick op d'Bühn nieft de Figuren a wiessel dann an der Haaptfënster an den Tab mat den Hannergrënn. Klick op d'Ikon mat der Landschaft fir en neien Hannergrond ze lueden a wiel deen aus, deen "hall" heescht. Läsch duerno de wäissen Hannergrond.
3. Änner den Numm vun der Figur a _Felix_
4. Vergewësser dech, dass de Felix sech just riets a lénks dréie kann, andeems du dëse Knäppchen drécks:
5. Erstell dëse Skript (Oflaf):

```scratch
	Wenn FLAG angeklickt
	wiederhole fortlaufend
		zeige zu Mauszeiger
		gehe 10er-Schritt
		nächstes Kostüm
		spiele Schlagzeug 62 für 0.3 Schläge
	(Ende wiederhole fortlaufend)
```

###Test däi Projet
__Klick op de grénge Fändel.__
Verfollegt de Felix de Mauszeiger? Gesäit et aus wéi wann hie géing goe, wann hien sech beweegt? Beweegt e sech mat der richteger Geschwindegkeet?
Späicher däi Projet of.
##2. SCHRATT: De Felix leeft dem Bert no
__Elo wëlle mir, dass de Felix dem Bert noleeft, an net méi dem Mauszeiger.__

1. Erstell eng nei Figur andeem s du de Knäppchen _Figur aus der Bibliothek wählen_ klicks, dann op _Tiere_ an do d'Maus erauswiels.
2. Änner den Numm vun der Figur op _Bert_.
3. Änner dem Bert säi Kostüm a kuck, dass hie méi kleng ausgesäit wéi de Felix.
Probéier sechs mol op de Knäppchen _Schrumpfen_ ze klicken:
4. Vergewësser dech, dass de Bert vu lenks no riets weist. 5. Erstell dëse Skript fir de Bert:


```scratch

	Wenn FLAG angeklickt
	wiederhole fortlaufend
		gehe zu Mauszeiger
		zeige zu Felix
	(Ende wiederhole fortlaufend)
```

###Test däi Projet
__Klick op de grénge Fändel.__
Beweegt sech de Bert mat denger Maus mat? Leeft de Felix dem Bert no?
Späicher däi Projet of.
##3. SCHRATT: De Felix rifft, wann hien de Bert gefaangen huet
__De Felix soll mierke, wann hien de Bert gefaangen huet, an eis et soen.__

1. Änner dem Felix säi Skript op dëst:

```scratch

	Wenn FLAG angeklickt
	wiederhole fortlaufend
		zeige zu Mauszeiger
		gehe 10er-Schritt
		nächstes Kostüm
		spiele Schlagzeug 62 für 0.3 Schläge
		falls wird Bert berührt?
			sage Gefangen! für 1 Sek.
		(Ende falls)
	(Ende wiederhole fortlaufend)
```

### Test däi Projet
__Klick op de grénge Fändel.__
Rifft de Felix, wann hien de Bert gefaangen huet?
Späicher däi Projet of.

##4. SCHRATT: ￼De Bert verwandelt sech an ee Geescht, wann hie gefaange gouf

__Amplaz dass de Felix riff, soll sech dës Kéier de Bert an ee Geescht verwandele wann hie gefaange gouf.__

1. Veränner dem Felix säi Skript, esou dass hien eng Noriicht verschéckt wann hien de Bert fänkt.

```scratch

	Wenn FLAG angeklickt
	wiederhole fortlaufend
		zeige zu Mauszeiger
		gehe 10er-Schritt
		nächstes Kostüm
		spiele Schlagzeug 62 für 0.3 Schläge
		falls wird Bert berührt?
			sende gefangen an alle
			spiele Schlagzeug 58 für 0.2 Schläge
			warte 1 Sek.
		(Ende falls)
	(Ende wiederhole fortlaufend)
```
2. Lued en neie Kostüm fir de Bert aus dem Dossier _fantasy/ghost2-a_
3. Änner de Kostüm, fir e méi kleng ze man.
Sechs mol op de _Schrumpfen_ Knäppchen drécke sollt duergoen.
4. Änner d'Bezeechnunge vum Bert senge Kostümer, esou dass de Maus-Kostüm ‘lieweg’ heescht, an de Geescht-Kostüm ‘dout’.
5. Erstell en neie Skript fir de Bert an e Geescht ze verwandelen:
```scratch

	Wenn ich gefangen empfange
	ziehe Kostüm dout an
	warte 0.5 Sek.
	ziehe Kostüm lieweg an
```

### Test däi Projet
__Klick op de grénge Fändel.__
Verwandelt de Bert sech an e Geescht, wann e gefaange gouf?
Spillt de Felix déi passend Geräischer zur richteger Zäit?
Bleift de Felix ëmmer nach laang genuch stoen, esou dass de Bert fortlafe kann?
Späicher däi Projet of.
##￼5. SCHRATT: Punkten zielen
__Looss eis e Punkte-System dobäi setzen, fir ze kucke wéi laang mir de Bert um Liewen hale kënnen.
Mir fänke bei Null un an erhéijen d'Punkten all Sekonn ëm 1. Wann de Felix de Bert fänkt, zéie mir 100 Punkten of.__
1. Erstell eng Variabel, fir all d'Figuren, an nenn se _Punkten_: Klick op _Variablen_ am Haaptmenü, klick op _Neue Variable_ a nenn se _Punkten_
2. Erstellt dës zwee nei Skripten op der Bühn:
```scratch

	Wenn FLAG angeklickt
	setze Punkten auf 0
	wiederhole fortlaufend
		ändere Punkten um 1
		warte 1 Sek.
	(Ende wiederhole fortlaufend)

	Wenn ich gefangen empfange
	ändere score um -100
```

###Test däi Projet
__Klick op de grénge Fändel.__
Erhéicht sech de Punktestand all Sekonn ëm 1?
Geet de Punktestand ëm 100 Punkten erof wann de Bert gefaange gëtt?
Wat geschitt, wann de Bert gefaange gëtt iert mir 100 Punkten hunn? Ginn d'Punkten zeréck op 0 wann s du en neit Spill ufänks?
Späicher däi Projet of.
__Bravo! Elo bass du fäerdeg an du kanns dech mat dengem neie Spill ameséiren!__
Vergiess net, dass du däi Spill all denge Kollegen an denger Famill weise kanns. Klick dozou op __Veröffentlichen!__ ganz uewen am Menü.