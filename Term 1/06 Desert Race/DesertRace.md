Level 2

#Wüstenrennen

__Einführung:__
Dieses Spiel ist ein Spiel für zwei Spieler, bei dem Ihr einen Papagei und einen Löwen ein Rennen durch die Wüste austragen lasst. Um das Tier zu bewegen, muss jeder Spieler eine Taste so schnell wie möglich drücken. Wer als Erster den Bildschirmrand erreicht hat gewonnen.


##￼Schritt 1: Erzeuge die Umgebung und ergänze die Sprites 

1. Wähle die Bühne aus und ergänze den Hintergrund "desert".
Schaue, wie Du mit den Aufgaben voran kommst, indem Du die Kästchen abhakst, sobald Du die Aufgabe erledigt hast:
￼￼2. Füge einen neuen Sprite hinzu. Wähle dafür den "lion"-Sprite im "animals"-Verzeichnis.
3. Füge einen zweiten Sprite hinzu, indem Du den "parrot"-Sprite im  "animals"-Verzeichnis öffnest.



##Schritt 2: Lasse den Löwen und den Papageien sich bewegen


Wir wollen, dass die Tiere sich bewegen, wenn Du eine Taste drückst.


1. Wähle zuerst den Löwen-Sprite und lasse ihn 4 Schritte gehen, wenn Du die "L"-Taste drückst.

```scratch

	wenn Taste l gedrückt
	gehe 4-er Schritt
```

2. Wähle jetzt den Papagei aus und erzeuge das Skript so, dass er vier Schritte gehen soll, wenn Du die "A"-Taste drückst.

```scratch

	wenn Taste a gedrückt
	gehe 4-er Schritt
```

###Teste Dein Projekt
__Klicke auf die grüne Fahne__ 
Bewegen sich Dein Löwe und Dein Papagei über den Bildschirm, wenn Du die "A"- und die "L"-Taste drückst?

Speichere Dein Projekt


##￼Schritt 3: Das Rennen starten

Wir müssen wissen, wie wir das Rennen starten und wie wir wissen, wer gewonnen hat. __Als Erstes erzeugen wir einen Start-Knopf.__

1. Ergänze einen neuen Sprite aus einer Datei. Wähle dafür den "button"-Sprite im “things”-Verzeichnis.
2. Bearbeite das Kostüm des "button"-Sprites, gib ihm den Text "Start" and klicke OK. Platziere den Sprite mitten auf der Bühne.
3. Erzeuge jetzt ein Skript das den Sprite erscheinen lässt wenn das Projekt gestartet wird:

```scratch

	wenn FAHNE angeklickt
	zeige dich
```
4. Wir wollen, dass der Knopf von drei rückwärts zählt, dann "Go" sagt und verschwindet, sobald er angeklickt wird.Now we want the button to count down from 3 and then say go and then hide when it is clicked. Add another script like this one:

```scratch

	wenn Start angeklickt
	sage 3 für 1 Sek.
	sage 2 für 1 Sek.
	sage 1 für 1 Sek.
	sage GO! für 1 Sek.
	verstecke dich
```
###Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Zählt der Start-Knopf rückwärts bis zum Start, sobald er angeklickt wird? Verschwindet er danach?

Speichere Dein Projekt

Die Läufer sollen sich erst bewegen wenn das Rennen begonnen hat. Wir wollen außerdem wissen, wann das Rennen vorbei ist. Wir brauchen also eine Variable, um diese Informationen zu speichern.

5. Erzeuge eine Variable für alle Sprites, die Du "racing" nennst.  Sie soll auf der BÜhne nicht gezeigt werden, entferne also das Häkchen neben der Variablen.
6. Setze "racing" auf 0 wenn das Projekt gestartet wird. Ändere Dein "wenn FAHNE angeklickt"-Skript. Es soll so aussehen:

```scratch

	wenn FAHNE angeklickt
	zeige dich
	setze racing auf 0
```
7. Im nächsten Schritt müssen wir die Variable "racing" gleich 1 setzen, sobald der Start-Countdown vorbei ist.
8. Jetzt müssen wir dafür sorgen, dass der Löwe und der Papagei sich nicht bewegen, solange "racing" nicht gleich 1 ist. Klicke auf den Papagei-Sprite. __Ergänze das Skript um einen Steuerungs-Block__ , der dem Papagei nur erlaubt, sich zu bewegen, falls __racing = 1__.

```scratch

	wenn Taste a gedrückt
	fallsf racing = 1
		gehe 4-er Schritte
	(ende falls)
```
9. Mache jetzt dasselbe für den Löwen-Sprite.

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Bewegen sich der Löwe oder der Papagei nur nachdem der Countdown vorbei ist?

Wir wollen wissen, wann das Rennen vorbei ist und dann alles zurücksetzen, so dass Ihr dann wieder spielen könnt.

##￼Schritt 4: Das Rennen beenden

1. Ergänze im Skript für den Papagei einen Block, der die Variable "racing"  =0 setzt, sobald der Sprite den Rand des Bildschirms erreicht.

```scratch

	wenn Taste a gedrückt
	falls racing = 1
		gehe 4-er Schritte
		falls wird Rand berührt?
			setze racing auf 0
		(ende falls)
	(ende falls)
```
2. Jetzt soll der Papagei uns sagen, falls er das Rennen gewonnen hat. Nimm ein Geräusch für den Parrot-Sprite auf, das abgespielt wird wenn der Papagei gewinnt. Klicke auf __Klänge__ und nimm ein Geräusch auf wie der Papagei das Rennen gewinnt!
3. Baue jetzt Blöcke in Dein Skript ein, die das Geräusch abspielen, das Du eben aufgenommen hast, und lasse den Papagei so sagen, dass er gewonnen hat:

```scratch

	wenn Taste a gedrückt
	falls racing = 1
		gehe 4-er Schritte
		falls wird Rand berührt?
			spiele Klang aufnahme1
			sage Der Papagei gewinnt! für 3 Sek.
		(ende falls)
	(ende falls)
	
		
```
4. Wiederhole jetzt alle diese Schritte für den Löwen.

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Kannst Du den Start-Knopf drücken und rennen, indem Du die "A"- und die "L"-Taste drückst?
Machen die Tiere die richtigen Geräusche, wenn sie gewonnen haben und sagen, dass sie gewonnen haben, wenn sie das Ende erreicht haben?

Speichere das Projekt

##￼Schritt 5: Das Spiel zurücksetzen

Nachdem das Rennen beendet ist müssen wir den anderen Sprites mitteilen, dass wir gewonnen haben und das Spiel zurücksetzen, so dass wir wieder spielen können.

__Der Sieger-Sprite muss mitteilen, dass er gewonnen hat.__

1. Klicke auf den Papagei-Sprite.
Baue einen Block ein, der "finished" sendet, nachdem der Sprite gesagt hat, dass er gewonnen hat.

```scratch

	wenn Taste a gedrückt
	falls racing = 1
		gehe 4-er Schritte
		falls wird Rand berührt?
			spiele Klang aufnahme1
			sage Der Papagei gewinnt! für 3 Sek.
			sende finished an alle
		(ende falls)
	(ende falls)

```
2. Jetzt müssen wir ein neues Skript einführen, das auf die "finished"-Meldung hört und den Papagei zurück zum Start bewegt. Was passiert, wenn Du den Wert von x veränderst?

```scratch

	wenn ich finished empfange
	setze x auf -175
```
3. Erzeuge dieses Skript jetzt auch beim Löwen. Probiere verschiedene Werte für x aus um sicherzustellen, dass der Löwe und der Papagei sich nebeneinander am Start aufstellen.
4. Wir wollen außerdem, dass der Löwe und der Papagei sich auf die gleiche Position begeben, wenn das Projekt gestartet wird. Erzeuge bei beiden ein neues Skript, das sie zum Start bewegt, sobald die Fahne angeklickt wird.

```scratch

	wenn FAHNE angeklickt
	setze x auf -175
```
5. Klicke jetzt den Knopf-Sprite an und erzeuge ein Skript, das ihn zeigt sobald er "finished" empfangen hat.
￼￼￼￼￼￼￼￼￼￼
###Teste Dein Projekt
__Klicke die grüne Fahne an.__


Kannst Du ein Rennen gegen eine Freundin oder einen Freund laufen, indem eine von Euch den Papagei bewegt, indem sie "A" drückt und die andere den Löwen, indem sie "L" drückt?

Speichere Dein Projekt

##￼Herausforderung: Baue einen Booster ein

* __Versuche einen Turbo einzubauen__ den Du einmal in jedem Rennen benutzen kannst, um den Papagei oder den Löwen __30 Schritte auf einmal__ zu bewegen.
* __Ergänze ein neues Kostüm,__ bei dem Feuer hinter jedem Sprite hervorkommt und es aussehen lässt, als ob der Turbo gezündet wurde.
* __Erzeuge noch ein Geräusch,__ das der Sprite macht wenn der Turbo gedrückt wurde.
￼

###Teste Dein Projekt

Speichere Dein Projekt


__Toll gemacht! Du bist fertig. Jetzt kannst Du das Spiel genießen!__
Denke daran: Du kannst das Spiel mit Deinen Freunden und Deiner Familie teilen, indem Du in der Menüleiste __Teilen__ anklickst!