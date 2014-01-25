Level 1

#Feuerwerk

__Einführung:__
In diesem Projekt wollen wir ein Feuerwerk über einer Stadt darstellen.

##￼SCHRITT 1: Erzeuge eine Rakete, die auf die Maus zufliegt

__Lass' uns die verschiedenen Bilder für das Spiel importieren__

1. Beginne ein neues Scratch-Projekt. Lösche die Katze, indem Du sie mit der rechten Maustasta anklickst und "Löschen" auswählst. 
2. Ersetze den Hintergrund mit "outdoor/city-with-water".
3. Nutze den __Neues Objekt aus Datei laden__ Knopf um ein Raketen-Objekt hinzuzufügen("Rocket")(benutze das "Resources/Rocket.png" Kostüm).
4. Bearbeite die Rakete so, dass sie versteckt wird, wenn die grüne Fahne angeklickt wurde.

Jetzt möchten wir, dass die Rakete sich auf den Mauszeiger zubewegt, wenn man mit der Maus klickt.

5. Ergänze einen "Wenn Taste Leertaste gedrückt"-Steuerungsblock. Lasse darunter die Rakete erscheinen und auf den Mauszeiger zugleiten.

```scratch

	wenn FAHNE angeklickt

	verstecke Dich
	
	wenn Taste Leertaste gedrückt
	zeige Dich
	gleite 1 Sek zu x: Maus x y: Maus y
```
		
###Teste Dein Projekt
__Klicke die grüne Fahne an, platziere die Maus über der Bühne und drücke die Leertaste.__

Erscheint die Rakete und bewegt sich auf den Mauszeiger zu?
Was passiert, wenn Du die Maus bewegst und die Leertaste wieder drückst?

Feuerwerkskörper fliegen normalerweise nicht von rechts nach links oder von links nach rechts. Lass uns daher sicherstellen, dass die Rakete immer vom unteren Rand des Bildschirms aus auf die Maus zufliegt. Benutze den "gehe zu"-Block. Lege fest, dass er sich zum unteren Rand des Bildschirms bewegen soll. Horizontal soll er jedoch an derselben Position bleiben.

```scratch

	wenn FAHNE angeklickt

	verstecke dich

	
	wenn Taste Leertaste gedrückt
	gehe zu x: Maus x-Position y: -200
	zeige dich
	gleite 1 Sek zu x: Maus x-Position y: Maus y-Position
```

###Teste Dein Projekt
__Klicke auf die grüne Fahne, platziere den Mauszeiger über der Bühne und drücke die Leertaste.__ 
Fliegt die Rakete vom unteren Bildschirmrand auf Deine Maus zu? Was passiert, wenn Du die Maus bewegst und die Leertaste noch einmal drückst?

7. Zum Schluss möchten wir es so einrichten, dass eine Rakete fliegt, wenn wir statt der Leertaste die linke Maustaste drücken. Um das zu erreichen können wir unser Skript mit einem __wiederhole fortlaufend, falls Maustaste gedrückt__-Schleife umhüllen.
Tausche dann den __wenn Taste Leertaste gedrückt__ Steuerungsblock gegen einen __wenn FAHNE angeklickt__ -Block. Vergewissere Dich außerdem, dass die Rakete versteckt ist, wenn das Spiel startet.

```scratch

	wenn FAHNE angeklickt
	verstecke dich
	wiederhole fortlaufend, falls Maustaste gedrückt?
		gehe zu x: Maus x-Position y: -200
		zeige dich
		gleite 1 Sek zu x: Maus x-Position y: Maus y-Position
	(stoppe alles)
```
###Teste Dein Projekt
__Klicke die grüne Fahne an. Drücke die linke Maustaste über der Bühne. Dann klicke noch einmal an einer anderen Stelle.__ 

###Zum Ausprobieren
1. Versuche zu verändern, wohin sich die Rakete bewegt ehe sie auf den Mauszeiger zu gleitet, so dass sie einen kleinen Bogen fliegt.
2. Versuche, einige Raketen ein wenig schneller oder langsamer fliegen zu lassen als andere.

Speichere Dein Projekt.

##SCHRITT 2: Lass die Rakete explodieren

Der erste Schritt zum Explodieren ist, die Rakete ein Knall-Geräusch machen zu lassen ("Resources\bang") bevor sie sich bewegt. Sobald sie die Maus erreicht hat soll sie sich verstecken. 
Du kannst ein Geräusch importieren, indem Du in der Übersicht in der Mitte den Tab "Klänge" auswählst. Hier klickst Du "Importieren" an.

```scratch

	wenn FAHNE angeklickt
	verstecke dich
	wiederhole fortlaufend, falls Maustaste gedrückt?
		gehe zu x: Maus x-Position y: -200
		spiele Klang bang
		zeige dich
		gleite 1 Sek zu x: Maus x-Position y: Maus y-Position
		verstecke dich
	(stoppe alles)
```
Lasse die Rakete als nächstes ein anderes Signal geben wenn sie explodiert. Wir werden uns dieses Signal später anhören.

```scratch

	wenn FAHNE angeklickt
	verstecke dich
	wiederhole fortlaufend, falls Maustaste gedrückt?
		gehe zu x: Maus x-Position y: -200
		spiele Klang bang
		zeige dich
		gleite 1 Sek zu x: Maus x-Position y: Maus y-Position
		verstecke dich
		sende explode
	(stoppe alles)
```
###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 
Vergewissere Dich, dass die Rakete ein Geräusch macht und versteckt wird, sobald sie die Maus erreicht hat.

3. Importiere ein neues Objekt: Resources/firework1.png
4. Sobald es das Signal "explode" bekommt, soll es sich verstecken und sich zu der Stelle bewegen, an der sich die Rakete befindet. Dazu soll es den "gehe zu"-Block benutzen, sich zeigen und eine Sekunde später verschwinden.

```scratch

	wenn ich explode empfange

	verstecke dich

	gehe zu x: x-Position von Rocket y: y-Position von Rocket

	zeige dich

	warte 1 Sek

	verstecke dich
```
###Teste Dein Projekt
__Lasse noch eine Rakete fliegen.__ 
Wird sie von dem Explosions-Bild ersetzt sobald sie explodiert?
Was passiert, wenn Du die Maustaste gedrückt hältst während Du die Maus bewegst? (Mache Dir keine Gedanken, wir werden das später in Ordnung bringen).

Speichere Dein Projekt

##￼SCHRITT 3: Mache jede Explosion einzigartig

Jetzt können wir jede Explosion einzigartig machen, indem wir den "setze Farbe-Effekt"-Block benutzen. Er wählt per Zufallsgenerator eine Farbe zwischen 1 und 200 bevor die Explosion gezeigt wird.

```scratch

	wenn ich explode empfange

	verstecke dich

	setze Farbe-Effekt auf Zufallszahl von 1 bis 200

	gehe zu x: x-Position von Rocket y: y-Position von Rocket

	zeige dich

	warte 1 Sek.

	verstecke dich
```

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 

Hat jede Explosion eine andere Farbe?

Lass' uns ein paar unterschiedliche Explosions-Bilder als Kostüme hinzufügen. Wir benutzen dafür "Resources/firework2.png" und "Resources/firework3.png". Wir wechseln bei jeder Rakete zwischen den verschiedenen Bildern bevor die Explosion gezeigt wird.

###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 

Hat jede Rakete ein anderes Explosions-Bild?

Zum Schluss wollen wir, dass die Explosionen mit der Zeit wachsen statt einfach nur zu erscheinen. Statt eine Sekunde zu warten setzen wir die Größe des Objekts auf 5% ehe wir es zeigen. Sobald es gezeigt wird vergrößern wir es in fünfzig Durchläufen mal 2, indem wir eine "wiederhole"-Schleife benutzen.

```scratch

	wenn ich explode empfange

	verstecke dich

	setze Farbe-Effekt auf Zufallszahl von 1 bis 200

	gehe zu x: x-Position von Rocket y: y-Position von Rocket

	setze Größe auf 5%

	zeige dich
	
	wiederhole 50
		ändere Größe um 2
	(Ende wiederhole)

	verstecke dich
```
###Teste Dein Projekt
__Klicke auf die grüne Fahne.__ 

Breitet sich das Explosions-Bild von der Mitte der Rakete aus aus und wächst langsam?

###Zum Ausprobieren
Wir könnten die Explosionen noch unterschiedlicher gestalten, indem wir die Größe und das Wachstum der Explosion verändern? 

Speichere Dein Projekt

##SCHRITT 4: Wir reparieren den Sende-Fehler
Erinnerst Du Dich, dass wir ein Problem haben, wenn wir die Maustaste gedrückt gehalten?
Bisher ist es so: Sobald die Rakete die Explosion meldet, wiederholt sie sofort die "wiederhole"-Schleife und es wird ein neues Explosionssignal gesendet. Das geschieht noch bevor die erste Explosion bis zum Ende dargestellt wurde.

Wir können das korrigieren, indem wir den "sende"-Block durch einen "sende und warte"-Block ersetzen. Auf diese Weise wird die Schleife nicht wiederholt bevor die Explosion nicht zu Ende ist. 

```scratch

	wenn FAHNE angeklickt
	verstecke dich
	wiederhole fortlaufend, falls Maustaste gedrückt?
		gehe zu x: Maus x-Position y: -200
		spiele Klang bang
		zeige dich
		gleite 1 Sek. zu x: Maus x-Position y: Maus y-Position
		verstecke dich
		sende explode an ale und warte
	(stoppe alles)
```
###Teste Dein Projekt
__Klicke die grüne Fahne an, halte die Maustaste gedrückt und bewege die Maus über die BÜhne.__ 

Erscheint das Explosions-Bild am richtigen Platz und zur richtigen Zeit?

Speichere Dein Projekt
