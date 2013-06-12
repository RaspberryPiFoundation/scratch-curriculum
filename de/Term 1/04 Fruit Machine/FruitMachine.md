Level 2

#Spielautomat

__Einführung:__
Bei diesem Spiel gibt es drei Objekte, die das Kostüm wechseln. Du musst sie anhalten, wenn sie alle gleich aussehen (wie bei einem Spielautomaten).

##￼Schritt 1: Erzeuge ein Objekt, das das Kostüm wechselt

__Zuerst müssen wir die verschiedenen Bilder für das Spiel importieren__

1. Öffne ein neues Scratch-Projekt. Lösche die Katze, indem Du sie mit der rechten Maustaste anklickst und "Löschen" auswählst.
2. Lade ein neues Objekt aus einer Datei.
3. Suche Dir ein Bild aus einem Verzeichnis aus. Wir haben "things/bananas1" benutzt, aber Du kannst jedes Bild nehmen, das Dir gefällt.
4. Klicke auf den Kostüme-Tab in der Mitte und importiere zwei weitere Kostüme, so dass Du am Ende drei Kostüme hast. (Wir haben uns für "animals/bee1" und "things/lego" entschieden, aber Du kannst auch andere Bilder benutzen).

__Nachdem wir jetzt verschiedene Kostüme haben, möchten wir, dass der Sprite sie wechselt.__

##Schritt 2: Das Bild soll sich ändern

1. Klicke auf den "Skripte"-Tab.
2. Gehe zu "Steuerung" und ziehe mit der Maus ein "Wenn FAHNE angeklickt" auf das Feld für das Skript. Das wird angesprochen, wenn wir später auf die grüne Fahne klicken.
3. Suche die "wiederhole fortlaufend"-Schleife und hänge es unten an das Feld mit der grünen Fahne an, so dass es einrastet.
4. Klicke oben rechts auf die grüne Fahne. Siehst Du, dass unser Skript jetzt einen weißen Rand hat? Es läuft jetzt, weil wir auf die grüne Fahne geklickt haben. Das löst den Start aus.
5. Gehe jetzt zu "Aussehen" und suche "nächstes Kostüm". Ziehe es mit der Maus in Dein Skript.
6. Wie können wir dafür sorgen, dass die Kostüme nicht so schnell wechseln? Gehe zu "Steuerung" und hole Dir das Element "warte 1 Sek.".
7. Passe die Zeit an, bis es in kürzeren Abständen wechselt (0.1s ist ein guter Rhythmus). Was würde passieren, wenn wir den "warte"-Block nicht hätten?

```scratch

	wenn FAHNE angeklickt
	wiederhole fortlaufend		
		nächstes Kostüm
		warte 0.1 Sek.
	(stoppe alles)
```

###Teste Dein Projekt
__Klicke die grüne Fahne an.__ 
Wechseln die Kostüme in einem gutenTempo, nicht zu schnell und nicht zu langsam?

Speichere Dein Projekt

###Zum Ausprobieren

Passe die Zeit im "Warte"-Block an. Welche Zahlen würden das Spiel zu einfach machen? Wann wird es zu schwierig?

##￼Schritt 3: Anhalten lassen sobald wir klicken

Toll! Das Objekt wechselt ständig das Kostüm. Aber wie erreichen wir, dass es damit aufhört, sobald wir es anklicken?

1. Erzeuge eine neue Variable, indem Du "Variablen" auswählst und "Neue Variable" anklickst. Nenne Deine Variable "angehalten" und erzeuge sie für alle Sprites. Entferne das Häkchen links von der Variablen, so dass sie nicht auf der Bühne erscheint.
2. Setze "angehalten" auf 1 wenn jemand auf das Bild klickt. Benutze dafür "wenn Sprite1 angeklickt" und setze "angehalten" auf 0. Damit stellst Du sicher, dass der Wert von 0 auf 1 wechselt.
3. Jetzt sorgen wir dafür, dass das Bild aufhört, sich zu ändern, sobald die Variable "angehalten" gleich 1 ist.
Gehe zu "Steuerung" und tausche die "wiederhole fortlaufend"-Schleife gegen eine "wiederhole fortlaufend, falls"-Schleife aus. Suche bei "Operatoren" ein "=" und prüfe damit, ob "angehalten" = 0.
4. Zum Schluss ergänzt Du bei Sprite1 "setze angehalten auf 0" direkt unter "Wenn FAHNE angeklickt".

###Teste Dein Projekt
__Klicke auf die grüne Fahne, warte einen Moment und klicke dann auf den Sprite.__ 

Wird das Kostüm ausgetauscht bevor Du es anklickst?
Stoppt es wenn Du es anklickst?
__Starte es noch einmal.__ Hört es auf, wenn Du den Mauszeiger darauf richtest, ohne dass Du klickst? Stoppt es, wenn Du irgendwo auf die Bühne klickst? Was passiert, wenn Du irgendwo auf das Scratch-Fenster klickst? Und wenn Du irgendwo außerhalb des Scratch-Fensters klickst?

Speichere Dein Projekt

##Schritt 4: Weitere Sprites erzeugen
__Jetzt wollen wir die anderen Sprites erzeugen, so dass wir das Spiel spielen können!__

1. Dupliziere den Sprite (Sprite1), indem Du ihn im Feld rechts unten mit der rechten Maustaste anklickst.
2. Dupliziere ihn nochmal, so dass Du dann drei Sprites auf dem Bildschirm hast.
3. Verschiebe die drei so, dass sie in einer Reihe stehen. Wenn nötig, verkleinere sie ein bisschen.

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ Alle Sprites sollten sich verändern. Versuche, sie zu stoppen, wenn sie alle das gleiche Bild zeigen.

Speichere Dein Projekt

###Zum Ausprobieren

Wenn Du das Spiel startest gleich nachdem Du es geladen hast zeigen alle Sprites das gleiche Kostüm und wechseln gemeinsam. Wie könntest Du erreichen, dass die Sprites das Kostüm zufällig wählen, sobald die grüne Fahne angeklickt wird?
Hinweis: Versuche, das Kostüm gleich beim Start zufällig auszuwählen.

__Gut gemacht! Du hast das Basis-Spiel gebaut. Es gibt jetzt noch einige Möglichkeiten, wie Du Dein Spiel noch verbessern kannst. Probiere doch diese Aufgaben zu lösen!__


##Aufgabe 1: Mache das Spiel schwieriger

Ändere irgendwie den Schwierigkeitsgrad. Einfach die Geschwindigkeit zu ändern ist leicht. Fällt Dir etwas Fantasievolleres ein?  Hier sind ein paar Vorschläge:

1. Ändere die Anzahl der Kostüme, die jedem Sprite zur Verfügung stehen.
2. Gib einem Sprite ein besonderes Kostüm, das nur er hat.
3. Lasse die Kostüme mit verschiedenen Zeitintervallen wechseln.
4. Lasse jeden Sprite bei jedem Kostüm-Wechsel ein beliebiges Kostüm auswählen, statt sie der Reihe nach zu tauschen. 

__Denke Dir noch mehr Möglichkeiten aus!__

Überlege bei jeder Veränderung, ob das Spiel dadurch einfacher oder schwieriger wird. Ist das Spiel jetzt zu einfach oder zu schwer? Wie kannst Du es anpassen, damit es genau den richtigen Schwierigkeitsgrad hat?


##Aufgabe 2: Lass das Spiel im Laufe der Zeit schwieriger und einfacher werden.

Verschiedene Menschen sind unterschiedlich gut darin, dieses Spiel zu spielen. __Wie kannst Du erreichen, dass das Spiel sich den Fähigkeiten des Spielers anpasst?__

Eine Möglichkeit wäre, __die Geschwindigkeit anzupassen, in der die Kostüme wechseln__. Du kannst eine Variable benutzen, die Du __delay__ (Verzögerung) nennst, um die Zeit des "warte"-Blocks jedes Sprites zu beeinflussen. Wenn der Spieler die Runde gewinnt, kann die Verzögerung ein wenig reduziert werden, um das Spiel schwieriger zu machen. Wenn der Spieler die Runde verliert kann die Verzögerung etwas länger werden, um das Spiel einfacher zu machen.

##￼Aufgabe 3: Erkenne, wenn alle Sprites beim selben Kostüm stehen geblieben sind.

__Das Ziel des Spiels ist es, die Sprites anzuklicken, wenn sie alle das gleiche Bild zeigen. Es wäre schön, wenn die Bühne erkennen könnte, dass Du fertig gespielt hast und Dir dann sagen würde, ob Du gewonnen oder verloren hast. Dazu muss geprüft werden, ob alle Sprites das gleiche Kostüm zeigen.__

Zuerst muss die Bühne erkennen, wenn der Spieler fertig gespielt hat. Das erreichen wir, indem wir prüfen, ob alle Sprites aufgehört haben, die Kostüme zu wechseln, nachdem wir einen angeklickt haben. Gehe zurück und passe bei jedem Sprite die "Wenn Sprite angeklickt"-Schleife an. Du kannst hier ein Element einbauen, das eine Nachricht sendet: "sende CheckForEnd an".

Die Bühne kann auf diese Nachricht antworten und prüfen, ob das Spiel zu Ende ist. Dafür schaut sie, ob bei allen Sprites die Variable "angehalten" = 1 gesetzt ist. Das passiert, indem sie die x-Position jeden Sprite-Blocks nimmt und x-Position in "angehalten" ändert.
Wenn alle drei Sprites einen "angehalten"-Wert = 1 haben, ist das Spiel vorbei und wir können prüfen, ob der Spieler gewonnen hat. 

Dafür können wir ebenfalls die x-Position des Sprite-Blocks benutzen. Statt allerdings auf die "angehalten"-Variable zu schauen, betrachten wir die Kostüm-Nummer. Wir können nun vergleichen, ob Sprite1 die gleiche Kostüm-Nummer hat wie Sprite2 und Sprite2 die gleiche wie Sprite3.

Jetzt brauchen wir eine "falls"-Schleife um alle "angehalten"-Variablen zu prüfen. Innerhalb der "falls"-Schleife können wir eine "falls... sonst..."-Schleife einbauen, die die Kostüm-Nummern vergleicht.

An dieser Stelle kannst Du das Ergebnis ausgeben, indem Du einen "sende"-Block benutzt. Darauf könntest Du mit einem anderen Sprite antworten. Vielleicht magst Du hier Felix einbauen, der dem Spieler gratuliert oder tröstet?


__Gut gemacht! Du bist fertig. Viel Spaß mit dem Spiel!__
Nicht vergessen: Du kannst Dein Spiel mit Deinen Freunden und Deiner Familie teilen, indem Du in der Menüleiste auf __Teilen__ klickst!
