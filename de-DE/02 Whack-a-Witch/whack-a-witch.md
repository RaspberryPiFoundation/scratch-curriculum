Level 1

#Schlag-die-Hexe

__Einführung:__
Dieses Projekt ist ähnlich wie das Spiel __Whack-a-Mole__. Du bekommst Punkte, wenn Du auf die Hexen klickst, die auf dem Bildschirm erscheinen. Das Ziel ist, in 30 Sekunden so viele Punkte wie möglich zu bekommen!

##Schritt 1: Erzeuge eine fliegende Hexe

1. Öffne ein neues Scratch-Projekt.
2. Entferne den Katzen-Sprite und ersetze den Hintergrund durch den Hintergrund "nature/woods".
3. Benutze den "neues Objekt aus Datei laden"-Knopf um eine neue Hexe zu laden (Wähle das "fantasy/witch1"-Kostüm). 

Jetzt soll sich unsere Hexe bewegen

4. Füge zu diesem Objekt eine Variable hinzu, die Du "speed" nennst.
Auf der Bühne sollte die Anzeige für diese Variable lauten “Sprite1 speed”.
Falls nur “speed” angezeigt wird, lösche die Variable und erzeuge eine neue Variable, nur für dieses Objekt (sprite1).
Die Geschwindigkeits-Variable "speed" soll steuern, wie schnell die Hexe sich bewegt. Wir benutzen hier eine Variable, so dass wir im Laufe des Spiels die Geschwindigkeit der Hexe leicht verändern können.
5. Wir möchten, dass die Hexe sich bewegt, sobald das Spiel beginnt. Erzeuge dafür dieses Skript:

```scratch

	wenn FAHNE angeklickt

	setze speed auf 5

	wiederhole fortlaufend

		gehe speed-er Schritte

	(stoppe alles)
```
		
###Teste Dein Peojekt
__Klicke auf die grüne Fahne__ und schaue, was Deine Hexe tut. Warum bleibt sie am Rand des Bildschirms hängen?

6. Um zu verhindern, dass die Hexe hängen bleibt, müssen wir dafür sorgen, dass sie sich in die entgegengesetzte Richtung bewegt, sobald sie den Rand des Bildschirms berührt. Ergänze unter Deinem "gehe speed-er Schritte" einen "pralle vom Rand ab"-Block.

```scratch

	wenn FAHNE angeklickt

	setze speed auf 5

	wiederhole fortlaufend

		gehe speed-er Schritte

		pralle vom Rand ab

	(stoppe alles)
```
7. Um zu verhindern, dass die Hexe sich auf den Kopf stellt, klicke in der Sprite-Übersicht oben auf den __kann sich nur nach rechts/links drehen__ -Knopf.

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 
Bewegt sich die Hexe auf dem Bildschirm von einer Seite zur anderen?

Speichere Dein Projekt.

###Zum Ausprobieren
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼__Versuche, den Wert der "speed" Variablen zu ändern, um sie schneller oder langsamer fliegen zu lassen.__

__Wie würdest Du die Hexe immer schneller werden lassen, je länger sie fliegt?__
(Das ist kniffelig; mache Dir also keine Gedanken, wenn Du nicht gleich verstehst, wie Du es lösen kannst. Du bekommst im Verlauf des Projekts noch mehr Hinweise dazu.)

##SCHRITT 2: Lasse die Hexe zufällig erscheinen und verschwinden

Damit das Spiel mehr Spaß macht, wollen wir, dass die Hexe zufällig erscheint und verschwindet. Wir erreichen das mit einem anderen Skript das zur gleichen Zeit abläuft wie das, das die Hexe bewegt. Dieses neue Skript soll die Hexe für einen zufällig erzeugten Zeitraum verstecken und sie dann wieder für einen zufällig erzeugten Zeitraum erscheinen lassen. Das wird dann immer wiederholt (oder bis das Spiel vorbei ist).

Erzeuge dieses Skript für die Hexe:

```scratch

	wenn FAHNE angeklickt

	wiederhole fortlaufend

		verstecke Dich

		warte Zufallszahl von 2 bis 5 Sek.

		zeige Dich

		warte Zufallszahl von 3 bis 5 Sek.

	(stoppe alles)
```
###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 
Bewegt sich die Hexe von einer Seite zur anderen über den Bildschirm und verschwindet und erscheint zufällig wieder?

Speichere Dein Projekt

###Zum Ausprobieren
__Versuche, den Bereich der Zufallszahlen zu ändern. Was passiert, wenn Du sehr große oder sehr kleine Zahlen aussuchst?__
(Gibt Dir das weitere Hinweise dazu, wie Du erreichen kannst, dass die Hexe schneller wird, je länger Du spielst?)

##￼SCHRITT 3: Lass die Hexe verschwinden, sobald sie angeklickt wurde

Um jetzt ein Spiel daraus zu machen, müssen wir den Spielern etwas zu tun geben. Sie müssen die Hexe anklicken, um sie verschwinden zu lassen. Wenn die Hexe angeklickt wurde soll sie verschwinden und ein Geräusch machen.

1. Importiere im "Klang"-Bereich das Geräusch "electronic/fairydust". 

2. Ergänze bei der Hexe dieses Skript:

```scratch

	wenn sprite1 angeklickt

	verstecke Dich

	spiele Klang Fairydust
```
###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 

Verschwindet die Hexe und spielt das Geräusch, wenn Du sie anklickst?

Speichere Dein Projekt

##Schritt 4: Füge Spielstand und Zeit hinzu

Wir haben eine Hexe, jetzt möchten wir ein Spiel daraus machen. Wir wollen jedes Mal Punkte bekommen, wenn wir auf die Hexe klicken, aber wir wollen auch ein bestimmte Spielzeit haben. Wir können eine Variable benutzen für den Spielstand (score) und die Zeit (timer).


1. Erzeuge eine neue Variable für alle Sprites, die Du "score" nennst. Ändere das Skript für die Hexe so, dass der Spielstand um eins erhöht wird, wenn die Hexe angeklickt wird.

```scratch

	wenn sprite1 angeklickt

	verstecke Dich

	spiele Klang Fairydust

	ändere score um 1
```
2. Wechsle zur Bühne und erzeuge eine neue Variable (dieses Mal nur für die Bühne), die Du "timer" nennst. Ergänze ein neues Skript, das läuft, sobald die grüne Fahne angeklickt wird. Es setzt die Zeit, "timer", auf 30 und die Punktzahl, "score", auf 0. 
Benutze dann einen "wiederhole bis"-Block um eine Sekunde zu warten und "timer" um eins zu verringern. Das sollte sich wiederholen, bis "timer" gleich null ist. Jetzt setzt Du "stoppe alles" ein, um das Spiel zu beenden.

```scratch

	wenn FAHNE angeklickt

	setze timer auf 30

	setze score auf 0

	wiederhole bis timer = 0

		warte 1 Sek.

		ändere timer um -1

	(Ende wiederholen)

	stoppe alles
```


###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 

Speichere Dein Projekt

###Zum Ausprobieren
__Wie könntest Du erreichen, dass die Hexe schneller wird, je länger das Spiel dauert?__


__Gut gemacht, das grundlegende Spiel ist jetzt fertig. Es gibt noch einige Dinge, die Du an Deinem Spiel verändern kannst. Probiere doch einmal diese Aufgabe!__

##Aufgabe: baue mehr Hexen ein

Wenn es mit einer Hexe Spaß macht, macht es mit mehr Hexen sicher noch mehr Spaß! Lass drei Hexen herumfliegen.

1. Dupliziere die Hexe, in dem Du sie in der Liste mit der rechten Maustaste anklickst.

2. Passe für jede Hexe die Größe an, so dass die Hexen unterschiedlich groß sind.

3. Ändere bei jeder Hexe die Geschwindigkeit ("speed"), so dass jede Hexe mit einer anderen Geschwindigkeit fliegt.

4. Verschiebe die Hexen auf dem Bild, so dass sie nicht alle an derselben Stelle sind.

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 

Gibt es drei Hexen, die sich auf dem Bildschirm von einer Seite zur anderen bewegen? Erscheinen und verschwinden sie zufällig? Verschwinden sie, wenn Du sie anklickst?

Speichere Dein Projekt

###Zum Ausprobieren
1. Mit wie vielen Hexen macht das Spiel am meisten Spaß?
￼￼2. Kannst Du die Hexen unterschiedlich aussehen lassen? Du könntest ihre Kostüme bearbeiten oder Blöcke aus der "Aussehen"-Palette benutzen, um sie zu verändern.
3. Kannst Du es so einrichten, dass man für verschiedene Hexen unterschiedlich viele Punkte bekommt? Man könnte für die schnellste (und kleinste) Hexe zum Beispiel 10 Punkte bekommen?


__Gut gemacht! Du bist fertig. Viel Spaß mit Deinem Spiel!__
Nicht vergessen: Du kannst Dein Spiel mit Deinen Freunden und Deiner Familie teilen, wenn Du im Menü auf __Teilen__ klickst!
