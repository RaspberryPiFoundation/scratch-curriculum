Level 1

#Fireworks

__Einleitung:__
In diesem Projekt werden wir ein Feuerwerk über der Stadt erzeugen.

##￼SCHRITT 1: Wir erstellen eine Rakete, die zur Maus fliegt.
__Zuerst importieren wir alle Bilder, die zu dem Projekt gehören__
1. Starte ein neues Scratch Projekt. Entferne die Katze, indem du sie mit der rechten Maustaste anklickst und Löschen wählst
2. Ersetze den Hintergrund mit outdoor/city-with-water
3. Nutze den __neue Grafik aus Datei__ Knopf, um die Grafik der Rakete zum Projekt hinzuzufügen (wähle die Resources/Rocket.png Datei).
4. Lasse die Rakete verschwinden, wenn die grünne Flagge angeklickt wird.
Nun wollen wir die Rakete auf den Mauszeiger zufliegen lassen, wenn du klickst.
5. Füge einen "when space key pressed" Kontrollblock hinzu und lasse darunter die Rakete auftauchen und auf die Maus zugleiten.

```scratch
	when FLAG clicked
	hide
	
	when space key pressed
	show
	glide 1 secs to x: mouse x y: mouse y
```
		
###Teste dein Projekt
__Klicke auf die grüne Flagge, platziere die Maus über dem Feld und drücke die Space-Taste.__
Taucht die Rakete auf und bewegt sich auf die Maus zu?
Was passiert, wenn du die Maus bewegst und erneut die Space-Taste drückst?
6. Feuerwerkskörper neigen nicht dazu, hin und her zu fliegen. Lass uns also sicherstellen, dass die Rakete immer von unten nach oben auf die Maus zufliegt. Bevor wir die Rakete anzeigen lassen, nutze den go to Block, um sie vertikal unter den sichtbaren Bereich zu verschieben, horizontal aber auf der Stelle zu bleiben.
```scratch
	when FLAG clicked
	hide
	
	when space key pressed
	go to x: mouse x y: -200
	show
	glide 1 secs to x: mouse x y: mouse y
```

###Teste dein Projekt
__Klicke auf die grüne Flagge, platziere die Maus über dem Feld und drücke die Space-Taste.__ 
Bewegt sich die Rakete von unten auf die Maus zu? Was passiert, wenn du die Maus bewegst und erneut die Space-Taste drückst?

7. Lass uns nun abschließend dafür sorgen, dass all das passiert, wenn du anstatt der Space-Taste die Maustaste drückst. Um das zu erreichen, können wir unser Skript in einen __forever if mouse down__ Block einbetten.
Dann ändern wir den __when space key pressed__ Kontrollblock zu __when flag clicked__ und stellen zum Schluss noch sicher, dass die Rakete zu Beginn unsichtbar ist.
```scratch
	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		show
		glide 1 secs to x: mouse x y: mouse y
	(end forever)
```
###Teste dein Projekt
__Klicke auf die grüne Flagge und danach auf das Feld. Klicke anschließend noch auf eine andere Stelle.__ 
###Dinge, zum Ausprobieren
1. Versuche zu verändern, wohin die Rakete fliegt bevor sie sich auf die Maus zubewegt, um sie einen leichten Bogen fliegen zu lassen..
2. Versuche einige Raketen etwas schneller oder langsamer als andere zu machen.
Speichere dein Projekt ab.

##SCHRITT 2: Lasse die Rakete explodieren

￼1. Der erste Schritte, um die Rakete explodieren zu lassen, ist ein Knall Geräuch abzuspielen (Resources\bang) bevor sie sich zu bewegen beginnt, und sich dann verstecken zu lassen, wenn sie die Maus erreicht. Um einen Klang zu importieren, gehe zu dem Sounds Tab und klicke auf importieren.

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
2. Als nächstes lassen wir die Rakete eine neue Nachricht verbreiten, wenn sie explodiert. Die Nachricht hören wir uns später an.
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
###Teste dein Projekt
__Klicke auf die grüne Flagge.__ 
Gehe sicher, dass die Rakete den Klang abspielt und sich dann ausblendet, wenn sie die Maus erreicht.

3. Importiere eine neue Grafik (Resources/firework1.png)
4. Wenn sie die Nachricht erhält, soll sie sich ausblenden und mithilfe des go to Blocks zu der Position der Rakete bewegen. Anschließend soll sie sich wieder einblenden und eine Sekunde später wieder verschwinden.

```scratch
	when I receive explode

	hide
	go to x: x position of rocket y: y position of rocket
	show
	wait 1 sec
	hide
```
###Teste dein Projekt
__Lasse noch eine Rakete fliegen.__ 
Wird sie mit der Explosionsgrafik ersetzt, wenn sie explodiert?
Was passiert, wenn du die Maustaste gedrückt hälst, während du sie bewegst? (Keine Sorge, das beheben wir später noch.)
Speichere dein Projekt ab.

##￼SCHRITT 3: Mache jede Explosion einzigartig
1. Jetzt können wir jede Explosion einzigartig machen, indem wir den set color effect Block verwenden und ihn eine zufällige Farbe zwischen 0 und 200 wählen lassen, bevor wir sie anzeigen.
```scratch
	when I receive explode

	hide
	set colour effect to pick random 1 to 200
	go to x: x position of rocket y: y position of rocket
	show
	wait 1 sec
	hide
```

###Teste dein Projekt
__Klicke auf die grüne Flagge.__ 
Hat jede Explosion eine andere Farbe?
2. Lass uns nun einige weitere Explosionsgrafiken einfügen, um einige Explosionen besonders zu machen. Dafür nutzen wir Resources/firework2.png und Resources/firework3.png und wechseln zwischen ihnen, wieder bevor wir sie anzeigen.

###Teste dein Projekt
__Klicke auf die grüne Flagge.__ 
Hat jede Rakete eine andere Explosionsgrafik?
3. Lassen wir nun die Explosionen größer werden, anstatt nur zu erscheinen. Statt eine Sekunde zu warten, setze die Größe der Grafik auf 5% bevor wir sie zeigen und sobald sie sichtbar ist, vergrößere sie 50 mal um Faktor 2 mit einem repeat Block.

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
###Teste dein Projekt
__Klicke auf die grüne Flagge.__ 

Geht die Explosion von der Mitte der Rakete aus und vergrößert sich dann langsam?

###Dinge, zum Ausprobieren
Warum versuchst du nicht, jede Explosion einzigartig zu machen, indem du ihre Größe und die Geschwindigkeit, mit der sie sich vergrößert, variierst.
Speichere dein Projekt ab.

##SCHRITT 4: Fehlerbehebung
Erinnerst du dich an den Fehler, der auftrat, wenn du die Maustaste gedrückt hälst?
Das passiert, weil wenn die Rakete die Nachricht über die Explosion aussendet, die if-Schleife sofort wiederholt wird und so eine weitere Nachricht ausgesandt wird, bevor die erste Explosion fertig angezeigt wurde.

1. Um das zu beheben, können wir den broadcast Block zu einem broadcast and wait Block abändern. Auf diese weise wird die Schleife so lange angehalten, bis die Explosion fertig ist mit explodieren.

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
###Teste dein Projekt
__Klicke auf die grüne Flagge, halte die Maustaste gedrückt und bewege den Zeiger über das Feld.__ 

Erscheint die Explosionsgrafik am richtigen Ort und zur richtigen Zeit?
Speichere dein Projekt ab.