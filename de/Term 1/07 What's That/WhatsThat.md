Level 3

#Was ist das?

__Einführung__
Auf der Tafel wird zufällig eines der Objekte gezeigt, ganz verpixelt. Du musst erraten, was es ist, indem Du unten in der Reihe auf das richtige Bild klickst. Je schneller Du es errätst desto mehr Punkte bekommst Du!

##Schritt 1: Lasse verschiedene Dinge auf der Tafel auftauchen.

Wir wollen, dass sich verschiedene Bilder auf der Tafel zeigen.

1. Beginne ein neues Scratch-Projekt und lösche den Katzen-Sprite.
2. Klicke auf die Bühne und dann auf den "Hintergründe"-Tab. Importiere den "indoors/chalkboard"-Hintergrund.
3. Importiere einen neuen Sprite und suche ihm ein Kostüm aus. Du könntest Dir etwas aus dem "things"-Verzeichnis auswählen.
4. Platziere den neuen Sprite in der Mitte der Tafel. Vergrößere ihn oder lasse ihn schrumpfen, je nachdem, wie Du es brauchst.
5. Klicke den "Kostüme"-Tab an und importiere vier weitere Dinge. Du kannst Dir die vier aussuchen, die Dir am besten gefallen.
Jetzt wollen wir, dass ein beliebiges Bild erscheint. 
6. Erzeuge dieses Skript:

```scratch

	wenn FAHNE angeklickt
	wiederhole Zufallszahl von 1 bis 5		
		nächstes Kostüm
	(ende wiederhole)
```

###Teste Dein Projekt
__Klicke die grüne Fahne an.__

Zeigt der Sprite verschiedene Kostüme?

__Klicke noch ein paar Mal drauf.__
 Bekommst Du jedes Mal ein anderes Kostüm? Manchmal bekommst Du vielleicht dasselbe Kostüm zweimal hintereinander, aber das ist in Ordnung. Du siehst auch, dass der Sprite flackert, wenn er das Kostüm wechselt. Wir werden das im nächsten Schritt in Ordnung bringen.
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼
Speichere Dein Projekt

##Schritt 2: Lasse die Bilder verpixeln

__Wir wollen das Bild jetzt verpixelt zeigen, wenn es erscheint, und es innerhalb einiger Sekunden deutlicher werden lassen.__

Wir können eine Punktzahl-Variable benutzen um zu steuern, wie stark das Bild verpixelt wird. Wenn die Punktzahl hoch ist ist es stark verpixelt. Je mehr die Punktzahl sinkt, desto schwächer wird die Verpixelung. Die Punktzahl wird auch als Zeitnehmer benutzt, wie es auf der __Timer Scratch-Karte__ erklärt wird.

1. Gehe zur "Variablen"-Palette und erzeuge eine Variable namens "score". 

2. Ändere Dein Skript, so dass es so aussieht:

```scratch

	wenn FAHNE angeklickt
	verstecke dich
	wiederhole Zufallszahl von 1 bis 5		
		nächstes Kostüm
	(ende wiederhole)
	setze score auf 110
	wiederhole bis score = 0
		ändere score um -10
		setze Pixel-Effekt auf score
		setze Farbe-Effekt auf score
		zeige dich
		warte 1 Sek.
	(ende wiederhole)
```

Du solltest den "verstecke dich"-Block ganz nach oben setzen und den "setze score auf 110"-Block auch. Alles andere wird darunter angebaut.

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Erscheint ein zufälliges und verpixeltes Bild?

Wird die Verpixelung schrittweise weniger?

Sinkt die Punktzahl während das Bild deutlicher zu sehen ist?

Ist das Bild klar wenn die Punktzahl Null erreicht?

Kommt immer noch jedes Mal ein neues Bild wenn Du die grüne Fahne anklickst?

Speichere Dein Projekt.

##Zum Ausprobieren

__Versuche, die Start-Punktzahl zu ändern und wie sehr sie sich jedes Mal in der Schleife ändert.__ Wie verändert das, wie das Bild aussieht? Wird es damit schwieriger oder leichter herauszufinden, was sich hinter dem Bild verbirgt?

__Probiere ein paar andere graphische Effekte aus den Listen aus.__ Wie verändern sie den Schwierigkeitsgrad?

##Schritt 3: Erlaube dem Spieler, das Bild zu erraten

Bisher erscheint unser Zufalls-Bild langsam und die Punktzahl sinkt mit der Zeit. Aber wie können wir das Spiel gewinnen? Wir fügen unten am Bildschirm ein paar Sprites hinzu, auf die der Spieler klicken kann. Wenn Du den richtigen anklickst gewinnst Du das Spiel. Wenn Du den falschen anklickst verschwindet der Sprite und das Spiel geht weiter.

Erst einmal müssen wir wissen, was die richtige Antwort ist.

1. Erzeuge eine neue Variable, die Du __antwort__ nennst. Vergewissere Dich, dass sie für alle Sprites gilt.
2. Ändere das Skript, das Du geschrieben hast, um die richtige Antwort zu sichern. Füge den "setze [antwort] auf Kostüm-Nr."-Block direkt hinter der ersten "wiederhole"-Schleife ein:

```scratch

	wenn FAHNE angeklickt
	verstecke dich
	wiederhole Zufallszahl von 1 bis 5		
		nächstes Kostüm
	(ende wiederhole)
	setze antwort auf Kostüm-Nr.
	setze score auf 110
	wiederhole bis score = 0
		ändere score um -10
		setze Pixel-Effekt auf score
		setze Farbe-Effekt auf score
		zeige dich
		warte 1 Sek.
	(ende wiederhole)
	
```
__Jetzt müssen wir die Sprites ergänzen, so dass der Spieler sie anklicken kann.__

3. Dupliziere den Haupt-Sprite und ziehe das Duplikat in die untere linke Ecke der Bühne.
￼￼4. Benenne den Sprite in __antwort1__ um. (Auf diese Weise ist es leichter zu erklären.)
5. Lösche das Skript von __antwort1__ und alle Kostüme bis auf das erste.
6. Wiederhole die letzten drei Schritte noch einmal und setze den  __antwort2__ Sprite neben __antwort1.__ Behalte nur das zweite Kostüm.
7. Wiederhole das noch dreimal für __antwort3__, __antwort4__, und __antwort5.__
Am Ende solltest Du fünf Antwort-Sprites am unteren Rand der Bühne sitzen haben. Jeder von ihnen sollte ein anderes Kostüm zeigen, das der Haupt-Sprite annehmen kann. __Keiner der Antwort-Sprites sollte ein Skript haben.__

Jetzt soll jeder Sprite auf das Angeklickt-Werden reagieren, abhängig davon, ob es die richtige Antwort ist oder nicht.

8. Erzeuge für den antwort1-Sprite dieses Skript:

```scratch

	wenn antwort1 angeklickt
	falls antwort=1
		sende gewonnen an alle
	sonst
		verstecke dich
	(ende falls)
```

9. Ziehe dieses Skript zu jedem der Antwort-Sprites. __Ändere bei jedem Sprite die 1 in die 2, 3 und so weiter.__
10. Nun müssen wir etwas ergänzen, das auf die "gewonnen"-Nachricht antwortet. Gehe wieder zu Sprite1, dem auf der Tafel. Erzeuge dieses zusätzliche Skript:

```scratch

	wenn ich gewonnen empfange
	sage verbinde Gratuliere! Du hast score
```

￼￼###Teste Dein Projekt
__Klicke die grüne Fahne an.__

Wenn Du das Spiel testest, kannst Du die __antwort Anzeige__ auf der Bühne benutzen, um zu sehen, was die richtige Antwort ist. Das ist praktisch um das Spiel zu testen.

Was passiert, wenn Du auf die __richtige Lösung__ klickst?

Was passiert, wenn Du eine __falsche Antwort__ gibst?

Was passiert mit der falschen Antwort, wenn Du __ein neues Spiel beginnst?__

Durch den Test erkennen wir zwei Probleme: Erstens erscheinen die Bilder der falschen Antworten nicht wieder auf der Bühne, wenn man ein neues Spiel beginnt. Und zweitens stoppt die Punktzahl nicht, wenn man die richtige Antwort gefunden hat.

11. Das erste Problem kannst Du lösen, indem Du bei den fünf antwort-Sprites dieses Skript erzeugst:

```scratch

	wenn FAHNE angeklickt
	zeige dich
```

Um das zweite Problem zu lösen, müssen wir die "wiederhole bis"-Schleife des __Frage-Sprites__ stoppen sobald der Spieler die richtige Antwort anklickt. Dafür werden wir eine neue Variable einführen. Wir setzen sie auf __null__ wenn das Spiel beginnt und setzen sie auf __eins__ wenn der Spieler gewonnen hat. Die "wiederhole bis"-Schleife muss beendet werden, wenn entweder die Punktzahl __null__ erreicht ODER der __Spiel-gewonnen-Merker__ gleich __eins__ gesetzt wurde.

12. Erzeuge eine neue Variable, die Du "gewonnen?" nennst.
13. Ändere die Skripte, so dass sie so aussehen:

```scratch

	wenn FAHNE angeklickt
	verstecke dich
	wiederhole Zufallszahl von 1 bis 5		
		nächstes Kostüm
	(ende wiederhole)
	setze antwort auf Kostüm-Nr.
	setze score auf 110
	setze gewonnen? auf 0
	wiederhole bis score = 0 oder gewonnen =1
		ändere score um -10
		setze Pixel-Effekt auf score
		setze Farbe-Effekt auf score
		zeige dich
		warte 1 Sek.
	(ende wiederhole)
	
	Wenn ich gewonnen empfange
	setze gewonnen auf 1
	schalte Graphikeffekte aus
	sage verbinde Gratuliere! Du hast score
```

Speichere Dein Projekt

__Gut gemacht! Das Basis-Spiel ist jetzt fertig.__

Es gibt viele Möglichkeiten, wie Du das Spiel verändern kannst. Versuche Dich an diesen Herausforderungen!


##￼￼￼Herausforderung 1: Mache das Spiel schwieriger oder leichter

Ändere den Schwierigkeitsgrad des Spiels.

* Verändere die Geschwindigkeit, in der das Bild aufgedeckt wird und wie schnell die Punktzahl sinkt.
* Verändere die Art und Weise, wie das Bild verfälscht wird.
* Versuche, die Bilder, die man erraten muss, auzutauschen. Wähle Bilder aus, die sich relativ ähnlich sind oder Bilder, die sehr verschieden sind. Falls Du Dich daran versuchst, vergiss' nicht, auch das Kostüm der Antwort-Sprites zu ändern.
￼￼￼￼￼￼￼

Speichere Dein Projekt
￼￼￼

##Herausforderung 2: Verfälsche das Bild in jedem Spiel auf unterschiedliche Weise

Im Moment wird bei jeder Runde des Spiels dieselbe Art der Verfälschung benutzt. In Schritt 2 hast Du vielleicht andere Arten der Verfälschungen ausprobiert, die mindestens genauso gut funktionieren wie die Farb- und Pixeleffekte, die wir benutzt haben.

Finde ein paar andere Arten der Verfälschung, die gut funktionieren. 

Verändere das Spiel so, dass in jeder Runde eine andere Art der Verfälschung in der "wiederhole bis"-Schleife ausgewählt wird.

__Hinweis:__ Versuche, eine neue Variable namens verfaelschung zu erzeugen. Weise ihr zu Beginn des Spiels einen zufälligen Wert zu. Benutze if-Schleifen innerhalb der "wiederhole .. bis"-Schleife um die richtige Verfälschung für dieses Spiel zu benutzen.
￼￼￼￼￼
Speichere Dein Projekt

##Herausforderung 3: Das Spiel soll aus mehreren Runden bestehen

Im Moment steht jedes Spiel für sich alleine. Ändere das so, dass der Spielablauf über mehrere Runden verläuft. Lasse ein Spiel beispielsweise aus drei Runden bestehen, so dass der Spieler drei Bilder erraten muss und bis zu 300 Punkte erzielen kann.

__Hinweis:__ Du brauchst eine zusätzliche Variable um die Gesamtpunktzahl über alle Runden zu speichern. Außerdem wirst Du eine Schleife brauchen um mehrere Runden innerhalb eines Spiels zu durchlaufen.

__Hinweis:__ Du musst am Anfang jeder Runde die Bilder, die fälschlicherweise angeklickt worden sind, wieder auftauchen lassen. Vielleicht könntest Du dafür eine Sende-Nachricht benutzen?
￼￼￼￼￼
Speichere Dein Projekt
￼￼￼

##Herausforderung 4: Sorge dafür, dass das Spiel mit den Runden schwieriger wird.

Wenn Du in einem Spiel mehrere Runden spielst soll es in jeder Runde schwieriger werden.

Muss man in jeder Runde dieselbe Punktzahl erreichen können? Sollte man in den schwierigeren Runden mehr Punkte bekommen, wenn man die Lösung schnell errät?

__Hinweis:__ Woher weißt Du, in welcher Runde Du grade bist? Wie kannst Du das benutzen, um den Schwierigkeitsgrad und die Punktzahl zu ändern?

Speichere Dein Projekt
￼￼

##Herausforderung 5: Lass' den Spieler raten, bis er einen Fehler macht.

Statt eine feste Anzahl von Runden vorzugeben, kann man so lange spielen, bis der Spieler ein Bild nicht errät. Das funktioniert wahrscheinlich nur, wenn das Spiel mit jeder Runde ein bisschen schwieriger wird.

Speichere Dein Projekt

##Herausforderung 6: Lasse das Spiel schwieriger oder einfacher werden, je nachdem, wie gut der Spieler ist.

Statt das Spiel immer schwerer zu machen, kannst Du den Schwierigkeitsgrad auch den Fähigkeiten des Spielers anpassen. Falls sie das richtige Bild sehr schnell erraten, könnte das nächste Spiel ein bisschen schwieriger sein. Wenn sie es nicht erraten oder erst sehr spät erraten könnte das Spiel beim nächsten Mal etwas einfacher werden.

Dieser Ansatz funktioniert nur, wenn man nicht die Punktzahl eines Spielers über mehrere Runden addiert.

Speichere Dein Projekt

##Herausforderung 7: Behalte den Überblick über die höchste Punktzahl

Halte die höchste Punktzahl fest. Falls es jemandem gelingt, sie zu schlagen, kannst Du sie nach ihrem Namen fragen und die neue höchste Punktzahl speichern. Sorge dafür, dass die höchste Punktzahl und der Name der Person, die sie erzielt hat, angezeigt werden.
￼￼￼￼￼

Speichere Dein Projekt


##￼￼￼Herausforderung 8: Lasse falsche Antworten "teuer" werden

Im Moment gibt es keine Strafe dafür, dass man einfach so schnell wie möglich auf alle Sprites klickt. Verändere das Spiel so, dass die Punktzahl mit jeder falschen Antwort ein wenig sinkt.

Wird das Spiel dadurch besser?
￼￼￼￼￼

Speichere Dein Projekt


__Toll gemacht! Du bist fertig. Jetzt kannst Du das Spiel genießen!__
Denke daran: Du kannst das Spiel mit Deinen Freunden und Deiner Familie teilen, indem Du in der Menüleiste __Teilen__ anklickst!
