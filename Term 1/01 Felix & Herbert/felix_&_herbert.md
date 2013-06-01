Level 1

#Felix & Herbert

__Einführung:__
Wir wollen ein Spiel bauen, bei dem __Felix der Kater__ und __Herbert die Maus__ Fangen spielen. Du steuerst Herbert mit der Computer-Maus und versuchst zu verhindern, dass er von Felix gefangen wird. Je länger Du es schaffst, Felix aus dem Weg zu gehen, desto mehr Punkte bekommst Du. Lass Dich nicht fangen, denn dann verlierst Du Punkte.

##Schritt 1: Felix folgt dem Maus-Zeiger

1. Beginne ein neues Projekt.
Behalte Deinen Fortschritt im Auge, indem Du die Kästchen abhakst, wenn Du die Aufgabe erledigt hast:
2. ￼￼￼Klicke auf "Bühne" neben der Figur und wechsle zum Tab "Hintergrund". Importiere von dort den Hintergrund "Indoors/Hall". Lösche den ursprünglichen, leeren Hintergrund.
3. Ändere den Namen der Figur um in "Felix".
4.  Vergewissere Dich, dass Felix nur nach rechts und nach links zeigt, in dem Du auf diesen Knopf klickst:
5. Schreibe dieses Skript:

```scratch

	Wenn FAHNE angeklickt

	wiederhole fortlaufend
		gehe zu Mauszeiger
		gehe 10-er Schritt
		nächstes Kostüm
		spiele Schlagzeug 62 für 0.3 Schläge
	(stoppe alles)
```
		
###Teste Dein Projekt
__Klicke auf die grüne Fahne.__
Folgt Felix dem Maus-Zeiger? Sieht es aus, als ob er wirklich gehen würde, wenn er sich bewegt? Bewegt er sich in der richtigen Geschwindigkeit?

Speichere Dein Projekt.

##Schritt 2: Felix jagt Herbert

__Als nächstes soll Felix Herbert die Maus jagen statt des Maus-Zeigers.__

1. Erzeuge ein neues Objekt indem Du den "neues Objekt aus einer Datei laden"-Knopf benutzt und "animals/Mouse1" auswählst.
2. Ändere den Namen des Objekts um in "Herbert".
3. Bearbeite das Kostüm und mache es kleiner als Felix. Probiere es mit sechs Klicks auf den "Schrumpfen"-Knopf.
4. Vergewissere Dich, dass Herbert nur nach rechts und nach links zeigt. 
5. Erzeuge für Herbert dieses Skript:


```scratch
	
	Wenn FAHNE angeklickt
	wiederhole fortlaufend
		gehe zu Mauszeiger
		zeige auf Felix
	(stoppe alles)
```

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Bewegt sich Herbert mit Deinem Maus-Zeiger? Jagt Felix Herbert hinterher?

Speichere Dein Projekt.

##Schritt 3: Felix sagt Bescheid, wenn er Herbert gefangen hat

__Wir wollen, dass Felix weiß, wenn er Herbert gefangen hat, und dass er es uns sagt.__


1. Ändere das Skript für Felix, dass es so aussieht:

```scratch
	
	Wenn FAHNE angeklickt
	wiederhole fortlaufend
		zeige auf Mauszeiger
		gehe 10-er Schritt
		nächstes Kostüm
		spiele Schlagzeug 62 für 0.3 Schläge
		Falls wird Herbert berührt?
			sage Caught you! für 1 Sek.
		(Ende Falls)
	(stoppe alles)
```

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Sagt Felix, wenn er Herbert gefangen hat?

Speichere Dein Projekt.

##Schritt 4: Herbert verwandelt sich in ein Gespenst, wenn er gefangen wird

__Jetzt soll Herbert sich in ein Gespenst verwandeln, wenn er gefangen wird, anstatt dass Felix uns Bescheid sagt.__

1. Ändere das Skript für Felix so, dass es diese Botschaft schickt, wenn er Herbert gefangen hat.

```scratch
	
	Wenn FAHNE angeklickt
	wiederhole fortlaufend
		zeige auf Mauszeiger
		gehe 10-er Schritt
		nächstes Kostüm
		spiele Schlagzeug 62 für 0.3 Schläge
		Falls wird Herbert berührt?
			sende caught an alle
			spiele Schlagzeug 58 für 0.2 Schläge
			warte 1 Sek.
		(Ende Falls)
	(stoppe alles)
```
2. Importiere bei Herbert ein neues Kostüm aus fantasy/ghost2-a.
3. Verkleinere das Kostüm. Sechs Klicks auf den "Schrumpfen"-Knopf sollten genügen.
4. Ändere die Namen von Herberts Kostümen, so dass das "Maus"-Kostüm den Namen ‘alive’ und das "Gespenst"-Kostüm den Namen ‘dead’ hat.
5. Erzeuge ein neues Skript für Herbert, das ihn in ein Gespenst verwandelt:

```scratch
	
	wenn ich caught empfange
	ziehe Kostüm dead an
	warte 0.5 Sek
	ziehe Kostüm alive an
```
	
###Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Verwandelt sich Herbert in ein Gespenst, wenn er gefangen wird? 
Macht Felix die richtigen Geräusche zur richtigen Zeit? 
Bleibt Felix lange genug still stehen, so dass Herbert davonlaufen kann?

Speichere Dein Projekt

##￼Schritt 5: Zähle Deine Punkte

__Jetzt möchten wir sehen, wie gut es uns gelingt, Herbert zu schützen, indem wir die Punkzahl anzeigen. Wir beginnen mit null Punkten und zählen pro Sekunde einen Punkt dazu. Wenn Felix Herbert fängt ziehen wir einhundert Punkte ab.__

1. Erzeuge eine Variable für alle Objekte, die Du "Score" nennst: Klicke im obersten Menü auf "Variablen" und erzeuge eine neue Variable. Nenne sie "Score".
2. Erzeuge diese beiden neuen Skripte:

```scratch
	
	Wenn FAHNE angeklickt
	setze score auf 0
	wiederhole fortlaufend
		ändere score um 1
		warte 1 Sek
	(stoppe alles)
	
	wenn ich caught empfange
	ändere score um -100
```
	
###Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Wird die Punktzahl jede Sekunde um einen Punkt höher? 
Werden einhundert Punkte abgezogen, wenn Herbert gefangen wird? 
Was passiert, wenn Herbert gefangen wird, bevor die Punktzahl 100 erreicht hat? 
Wird die Punktzahl auf "0" gestellt, wenn Du ein neues Spiel beginnst?

Speichere Dein Projekt.

__Gut gemacht! Du bist fertig. Viel Spaß mit Deinem Spiel.__
Nicht vergessen: Du kannst Dein Spiel mit Deinen Freunden und Deiner Familie teilen, wenn Du in der Menüleiste auf  __Teilen__ klickst.
