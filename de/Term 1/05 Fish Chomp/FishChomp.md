Level 2

#Fisch Füttern

__Einführung:__
Wir wollen ein Fisch-Fütter-Spiel bauen! Steuere den großen Hungrigen Fisch und versuche, mit ihm alle Beutetiere zu fressen, die herumschwimmen.

##￼Schritt 1: Erzeuge einen Sprite, der das Kostüm wechselt.
__Lass' den Hungrigen Fisch im Meer herumschwimmen!__

1. Beginne ein neues Scratch-Projekt.
2. Klicke die Bühne an und wähle dann den "Hintergründe"-Tab. Importiere den Hintergrund "nature/underwater" und lösche background1.
3. Ändere den Namen von Sprite 1 um in Hungrigen Fisch.
4. Importiere das Kostüm für Hungrigen Fisch, "resources/hungry-fish" und lösche seine bisherigen Kostüme "costume1" und "costume2".
5 Stelle ein, dass Hungriger Fisch sich nur nach rechts/links richten kann.
6. Erstelle jetzt das Skript für Hungrigen Fisch, so dass er der Maus durch das Meer folgt:

```scratch

	wenn FAHNE angeklickt
	wiederhole fortlaufend		
		zeige auf Mauszeiger
		gehe 3er Schritte
	(Ende wiederholen)
```

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 
Bewege den Mauszeiger durch das Meer. Folgt der Fisch der Maus?
Was passiert, wenn Du die Maus nicht weiterbewegst und der Fisch sie einholt? Wie sieht es aus? Warum passiert das?


7. Du kannst verhindern, dass der Fisch sich wie verrückt hin und her dreht, indem Du ihn sich nur bewegen lässt, wenn er dem Mauszeiger nicht zu nahe kommt.
(Der _Entfernung von_ Block ist in der Fühlen-Palette).


```scratch

	wenn FAHNE angeklickt
	wiederhole fortlaufend, falls Entfernung von Mauszeiger > 10
		zeige auf Mauszeiger
		gehe 3er Schritte
	(Ende wiederholen)
```


###Teste Dein Projekt

Speichere Dein Projekt

##Zum Ausprobieren

Wenn Du möchtest, kannst Du unterschiedlich große Zahlen in das Skript eingeben. Wie verändert das die Bewegung von Hungrigem Fisch? Benutze für den Entfernungsgrenzwert eine große Zahl (z.B. 100) oder eine kleine Zahl (z.B. 1). Ändere die Distanz, die der Fisch zurücklegt, in eine große Zahl (z.B. 20) oder eine kleine Zahl (z.B. 1 oder sogar 0).


##Schritt 2: Gib' dem Fisch ein Beutetier

1. Erzeuge einen neuen Sprite aus der Datei "animals/lobster1". 
2. Benutze das Werkzeug, um den Sprite schrumpfen zu lassen (über der Bühne).
3. Erzeuge ein Skript, das das Beutetier herumschwimmen lässt. Wir wollen, dass sie sich zufällig bewegt. Dafür soll es sich ein Stückchen vorwärts bewegen, sich dann ein bisschen nach rechts oder links bewegen und das alles anschließend wiederholen.

```scratch

	wenn FAHNE angeklickt
	wiederhole fortlaufend		
		gehe 2er Schritt
		drehe Zufallszahl von -20 bis 20 Grad
		pralle vom Rand ab
	(Ende wiederholen)
```

###Teste Dein Projekt
__Klicke auf die grüne Fahne__ und beobachte, wie das Beutetier herumschwimmt. Schwimmt es so herum, wie Du das erwartet hast? Sehen seine Bewegungen echt aus?

__Im Moment beeinflussen sich Hungriger Fisch und das Beutetier nicht gegenseitig. Wir werden uns im nächsten Schritt darum kümmern.__

Speichere Dein Projekt

###Zum Ausprobieren

* Versuche, die Zahlen des "Zufallszahl"- und des "Gehe"-Blocks zu verändern. Auf welche Weise verändern sich die Bewegungen des Beutetiers?
* Was bewirkt der __pralle vom Rand ab__ Block? Nimm' ihn heraus und beobachte, was passiert.

##￼Schritt 3: Hungriger Fisch frisst das Beutetier

__Jetzt wollen wir dafür sorgen, dass Hungriger Fisch das Beutetier frisst!__ Sobald Hungriger Fisch das Beutetier mit dem Maul gefangen hat, müssen zwei Dinge passieren:
* Der Hungrige Fisch muss sein Maul zumachen und ein Fressgeräusch machen.
* Das Beutetier muss verschwinden und kurze Zeit später wieder auftauchen.

1. Zuerst lassen wir das Beutetier verschwinden, sobald es den hungrigen Fisch berührt. Es soll 3 Sekunden später wieder auftauchen. Benutze den "berühren"-Block um zu erkennen, ob es den Fisch berührt.

```scratch

	wenn FAHNE angeklickt
	wiederhole fortlaufend		
		gehe 2er Schritt
		drehe Zufallszahl von -20 bis 20 Grad
		pralle vom Rand ab
		falls wird Hungriger Fisch berührt?
			verstecke dich
			warte 3 Sek.
			zeige dich
		(Ende falls)
	(Ende wiederholen)
```

###Teste Dein Projekt
__Probiere Dein Spiel noch einmal aus – kannst Du irgendwelche Probleme erkennen?__ Achte darauf, dass das Beutetier verschwindet, egal an welcher Stelle es den hungrigen Fisch berührt. Außerdem könnte der Fisch einfach drei Sekunden warten und das Beutetier fressen, sobald es wieder auftaucht. Das ist nicht besonders fair!

2. Wie können wir dafür sorgen, dass das Beutetier nur verschwindet, wenn es das Maul des hungrigen Fisches berührt? Wir könnten den "wird Farbe berührt?"-Block benutzen und schauen was passiert, wenn das Beutetier die blauben Zähne des Fisches berührt. 
Tausche dafür in Deinem Skript den "Berühren"-Block gegen den "wird Farbe berührt?"-Block aus. Klicke auf die Farbe im Block und klicke dann auf die Zähne des Fisches.
3. Als nächstes können wir das Beutetier sich mit einem "gehe"-Block zu einem zufälligen Punkt auf dem Bildschirm bewegen lassen bevor es wieder auftaucht. Wir geben ihm dafür einen zufällig erzeugten Wert für x und y.

```scratch

	wenn FAHNE angeklickt
	wiederhole fortlaufend		
		gehe 2er Schritt
		drehe Zufallszahl von -20 bis 20 Grad
		pralle vom Rand ab
		falls wird Farbe [] berührt?
			verstecke dich
			warte 3 Sek.
			gehe zu x: Zufallszahl von -220 bis 220 y: Zufallszahl von -170 bis 170
			zeige dich
		(Ende falls)
	(Ende wiederholen)
```
###Teste Dein Projekt

Probiere das Spiel noch einmal aus – verschwindet das Beutetier nur, wenn es das Maul des Fisches berührt? Taucht es an einem beliebigen Punkt auf dem Bildschirm wieder auf, statt an der Stelle, an der es gefressen wurde?

4. Der Fisch muss wissen, wenn er etwas gegessen hat, damit er ein Geräusch machen und sein Aussehen ändern kann. Um das zu erreichen, soll das Beutetier senden, dass es gefressen wurde, bevor es verschwindet.

```scratch

	wenn FAHNE angeklickt
	wiederhole fortlaufend		
		gehe 2-er Schritte
		drehe Zufallszahl von -20 bis 20 Grad
		pralle vom Rand ab
		falls wird Farbe [] berührt?
			sende erwischt
			verstecke dich
			warte 3 Sek.
			gehe zu x:Zufallszahl von -220 bis 220 y: Zufallszahl von -170 bis 170
			zeige dich
		(Ende falls)
	(Ende wiederhole)
```
__Jetzt wollen wir, dass der Fisch auf diese Nachricht antwortet, indem er ein "chomp"-Geräusch macht und mit den Zähnen schnappt.__

5. Füge das "resources/mouth-closed" Kostüm und das "resources/chomp"-Geräusch zum Hungrigen Fisch-Sprite hinzu.
6. Ergänze beim Hungrigen Fisch jetzt ein neues Skript, so dass er auf die Nachricht antworten kann, die das Beutetier sendet. Das Skript soll den Fisch das 'chomp'-Geräusch abspielen lassen und das "mouth-closed"-Kostüm anziehen, kurz warten und wieder das andere Kostüm anziehen.

```scratch

	wenn ich erwischt empfange
	spiele Klang chomp
	wiederhole 2 mal
		ziehe Kostüm mouth-closed an
		warte 0.5 Sek
		ziehe Kostüm hungry-fish an
	(ende wiederhole)
```

__Jetzt wo unser Hungriger Fisch bereit zum Fressen ist, wollen wir das Meer mit Beutetieren füllen. Klicke den Beutetier-Sprite mit der rechten Maustaste an und dupliziere ihn mehrere Male.__

###Teste Dein Projekt.
Klicke auf die grüne Fahne.
Frisst Hungriger Fisch das Beutetier? Frisst er die unterschiedlichen Beutetiere?

Speichere Dein Projekt

###Zum Nachdenken
Warum müssen wir beim Skript für das Beutetier am Anfang den "zeige dich"-Block einbauen? Überlege was passieren würde, wenn das Beutetier gefressen wird und das Spiel zu Ende ist, bevor das Beutetier wieder auftaucht. Was würde passieren, wenn das Spiel dann neu gestartet werden würde?

__Gut gemacht! Das Basis-Spiel ist jetzt fertig. Es gibt aber noch viele Möglichkeiten, Dein Spiel auszubauen. Bist Du bereit für eine Herausforderung?__


##￼Herausforderung 1: Die Beutetiere sollen sich unterschiedlich bewegen

Im Moment bewegen sich alle Beutetiere auf die gleiche Weise. __Kannst Du erreichen, dass eines sich anders bewegt als die anderen?__
__Hinweis:__ Arbeite nicht zu lange an diesem Teil ohne die anderen Aktivitäten in diesem Projekt anzuschauen.

__Suche Dir eines der Beutetiere aus, um damit zu experimentieren.__ Falls sie alle das gleiche Kostüm tragen gib ihm eine andere Farbe mithilfe des __setze Farbe-Effekt__-Blocks. Auf diese Weise kannst Du es von den anderen Beutetieren unterscheiden.

Lasse dieses Beutetier sich langsamer bewegen als die anderen. __Hinweis:__ Schaue Dir den gehe (2)-er Schritt-Block an.


###Teste Dein Projekt
Bewegt sich das Beutetier langsamer? Wird das Spiel dadurch besser?
Wenn Du das erreicht hast, __versuche, eines der Beutetiere sich schneller bewegen zu lassen als die anderen.__


Bewegen sich die Beutetiere noch auf realistische Weise? Machen diese Veränderungen das Spiel besser?
__Hinweis:__ Falls Deine Beutetiere im Kreis herumschwimmen, überprüfe die Werte im "Zufallszahl von...bis"-Block innerhalb des "drehe"-Blocks.

Wie wäre es, wenn jedes der Beutetiere sich unterschiedlich verhalten würde, indem Du verschiedene Kombinationen dieser Änderungen benutzt?

Machen irgendwelche dieser Veränderungen das Spiel besser? Machen sie es interessanter, macht es mehr Spaß, wird es leichter oder schwerer? Ist etwas davon "besser"?

Speichere Dein Projekt

##￼Herausforderung 2: Die Beutetiere sollen den Hungrigen Fisch meiden

Die Beutetiere in diesem Spiel sind wirklich dumm! Sie schwimmen zufällig herum bis sie gefressen werden. Echte Beutetiere gehen Raubtieren aus dem Weg. __Wir wollen eines der Beutetiere vor dem Hungrigen Fisch davonschwimmen lassen.__

Es gibt in Scratch keinen Block, der einem sagen kann, in welcher Richtung sich ein anderer Sprite befindet. Aber Du kannst einen Sprite in die Richtung eines anderen zeigen lassen, sich umdrehen und in die andere Richtung schauen lassen. Die Blöcke, die Du dafür brauchst, sind in der __Bewegung__ Palette.

Benutze diese Idee __um eines der Beutetiere immer vom Hungrigen Fisch weg zeigen zu lassen.__ Vielleicht möchtest Du es zappeln lassen wenn es wegschwimmt.

###Teste Dein Projekt
Wird es dadurch schwieriger, die Beutetiere zu fangen? Wird das Spiel dadurch schwieriger?

Speichere Dein Projekt

##Herausforderung 3: Ergänze den Spielstand
Es genügt nicht, die Beutetiere zu fressen. Wie kannst Du wissen, dass Du dieses Spiel besser kannst als Deine Freunde? __Wir möchten den Spielstand registrieren, daher wollen wir eine Punkteanzeige einbauen.__ Schau Dir die __Spielstand registrieren Scratch Karte an__ um herauszufinden, wie Du das lösen kannst.. 

Wo sollte sich der Block befinden, der die Punkte addiert?

Vergewissere Dich, dass der Punktestand bei Beginn des Spiels zurück auf Null gesetzt wird. Wo sollte sich dieser Block befinden?

###Teste Dein Projekt
Wird der Punktestand bei Beginn des Spiels auf Null gesetzt? Wird er jedesmal höher, wenn Du ein Beutetier frisst?

Speichere Dein Projekt

##Herausforderung 4: Baue einen Countdown ein

__Gib' Dir ein Zeitlimit für das Spiel.__ Wie viele Beutetiere kannst Du in 30 Sekunden fressen?

Schau Dir die __Timer Scratch Karte__ an um zu erfahren, wie Du einen Timer in das Spiel einbauen kannst.Fange mit einem 30-sekündigen Spiel an.

###Teste Dein Projekt
Beginnt der Timer bei 30?

Zählt er in der richtigen Geschwindigkeit abwärts?

Kannst Du Beutetiere fangen, während die Zeit läuft?

Stoppt das Spiel wenn die Zeit abgelaufen ist?

Speichere Dein Projekt

##￼Herausforderung 5: Es soll Bonus-Punkte geben
Wenn man alle drei Beutetiere gleichzeitig fressen kann soll es viele Bonus-Punkte geben. Wie findest Du heraus, wie viele Fische gefressen worden sind?
__Hinweis:__ Eine Art, das zu lösen ist, __eine Variable zu benutzen um zu zählen, wie viele Beutetiere herumschwimmen.__

Speichere Dein Projekt

##Herausforderung 6: Ändere das Spiel: Lasse die Beutetiere leben! Manchmal kann man tolle neue Ideen entwickeln, indem man eine alte Idee nimmt und genau das Gegenteil tut.

__Verändere das Spiel: Statt einen großen Fisch zu steuern, der die Beutetiere frisst, steuerst Du jetzt ein Beutetier, das in einem Meer von Hungrigen Fischen schwimmt.__ Wie lange dauert es, bis Du gefressen wirst?

Speichere Dein Projekt

__Super gemacht, Du bist fertig! Jetzt kannst Du Dein Spiel genießen!__
Denke daran, dass Du Dein Spiel mit Deinen Freunden und Deiner Familie teilen kannst, indem Du in der Menüleiste auf den  __Teilen__ Knopf klickst!
