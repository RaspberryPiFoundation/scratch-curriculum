Level 3

#Malkasten

__Introduction:__
In diesem Projekt bauen wir uns ein Zeichenwerkzeug, mit dessen Hilfe Du selbst ein Künstler sein kannst. Du kannst die Stiftfarbe ändern, den Bildschirm leeren, stempeln und vieles mehr!
￼
##Schritt 1: Ziehe und zeichne

Wir fangen an mit einem Stift, der zeichnet wenn Du ihn über die Bühne ziehst.

1. Öffne ein neues Scratch-Projekt. Lösche die Katze, indem Du sie mit der rechten Maustaste anklickst und "Löschen" wählst.
2. Klicke auf die __Bühne__ und dann den __Hintergrund__ Tab. Importiere den __indoors/chalkboard__ Hintergrund.
3. Erzeuge einen neuen Sprite, den Du __Malstift__ nennst. Benutze dafür __resources\gruener-stift.__
4. Wechsle zum __Kostüme__ Tab und klicke "Bearbeiten" an. Im __Malprogramm__ soll die Mitte des Bildes immer an der Spitze des Bleistifts sein. Das erreichst Du, indem Du __Drehpunkt für das Kostüm setzen__ anklickst und die Linien herumschiebst, bis sie an der Spitze des Bleistifts sind.
5. Lasse den Bleistift dem Mauszeiger über die Bühne folgen, indem Du den __wiederhole fortlaufend-__ Block und den __gehe zu__ Mauszeiger-Block benutzt.

```scratch
wenn FAHNE angeklickt
wiederhole fortlaufend
	gehe zu Mauszeiger
(ende wiederhole)
```

__Jetzt möchten wir diesen Stifte-Sprite tatsächlich als Malstift benutzen.__ Wenn Du in die Malstift-Palette schaust, findest Du dort alle möglichen Blöcke, die etwas mit Zeichnen zu tun haben. Im Moment interessieren wir uns hauptsächlich für __senke Stift ab__ und __hebe Stift an__

6. Wir möchten die Maustaste benutzen, um den Malstift zu steuern. Sobald die Maustaste gedrückt ist, sollte der Malstift unten sein, wenn nicht sollte der Malstift angehoben sein. Wir können das mit Hilfe eines "falls... sonst"-Blocks und eines "Maustaste gedrückt?"-Blocks umsetzen.

```scratch
wenn FAHNE angeklickt
wiederhole fortlaufend
	gehe zu Mauszeiger
	falls Maustaste gedrückt?
	senke Stift ab
	sonst
	hebe Stift an
	(ende falls)
(ende wiederhole)
```
##Teste Dein Projekt
__Klicke die grüne Fahne an.__
Folgt der Stift dem Mauszeiger? Was passiert, wenn Du die Maustaste gedrückt hältst und die Maus bewegst? Mache Dir im Moment noch keine Gedanken über die Stiftfarbe.


7. Irgendwann ist der Bildschirm ziemlich voll von dem ganzen Gekritzel. Wir können den "wische Malspuren weg"-Block benutzen, um den Bildschirm wieder sauber zu machen.

```scratch
wenn FAHNE angeklickt
wische Malspuren weg
wiederhole fortlaufend
	gehe zu Mauszeiger
	falls Maustaste gedrückt?
	senke Stift ab
	sonst
	hebe Stift an
	(ende falls)
(ende wiederhole)
```

##Teste Dein Projekt
__Klicke die grüne Fahne an.__

Verschwindet Deine Zeichnung, wenn Du auf die grüne Fahne klickst?

Speichere Dein Projekt

##￼￼￼Schritt 2: Aufräumen

Statt das Spiel jedes Mal stoppen und neu starten zu müssen, bauen wir lieber einen Knopf ein, mit dem wir die Zeichnung verschwinden lassen können. Er wird das mit Hilfe des "wische Malspuren weg"-Knopfes tun.

1. Erzeuge einen neuen Sprite mit dem __resources/loeschen-knopf__ Kostüm. 
2. Ändere den Namen um in __loeschen__.
3. Platziere den Sprite in der unteren linken Ecke der Bühne.
4. Gib dem "loeschen"-Sprite dieses einfache Skript:

```scratch
wenn loeschen angeklickt
wische Malspuren weg
```

##Teste Dein Projekt
__Click on the green flag.__

Wischt der "löschen"-Knopf Deine Zeichnung weg?

Speichere Dein Projekt

##SCHRITT 3: Die Farbe ändern

Bisher können wir nur blaue Linien malen. Lass' uns auch ein paar andere Farben benutzen! Wir werden am unteren Rand des Rahmens noch ein paar Sprites hinzufügen. Die Sprites sollen aussehen wie farbige Knöpfe. Wenn wir auf einen der Knöpfe klicken, ändert das die Farbe der Linie, die wir zeichnen. Damit wir wissen, mit welcher Farbe wir grade malen, verändert der Knopf auch die Farbe des Malstift-Sprites.

1. Füge einen neuen Sprite hinzu, den Du __rot__ nennst. Benutze dafür __resources/rot-auswahl Kostüm__. 
2. Platziere ihn irgendwo in der unteren Reihe, in der Nähe des __Loeschen-Knopfes__.
3. Wenn der rote Sprite angeklickt wird, sollte er die Botschaft __rot__ senden.

```scratch
wenn Rot angeklickt
sende rot an alle
```
__Ja, das ist alles, was er tun muss. Die schwere Arbeit wird vom Malstift geleistet.__

Importiere beim Malstift ein neues Kostüm , __resources/roter-stift__. Setze auch hier, wie beim Original, das Zentrum des Kostüms an die Spitze des Stiftes, indem Du "Drehpunkt für das Kostüm setzen" benutzt.

4. Gib dem Malstift ein neues Skript. Wenn der Malstift die Botschaft __rot__ bekommt, soll er das Kostüm "roter Stift" anziehen und die Stiftfarbe rot wählen (benutze den "setze Stiftfarbe auf"-Block).

__Hinweis:__ wenn Du auf das farbige Quadrat im __setze Stiftfarbe auf__ Block, kannst Du mit der Pipette den roten Sprite anklicken um die richtige Farbe auszuwählen.

```scratch
wenn ich rot empfange
ziehe Kostüm roter-stift an
setze Stiftfarbe auf (rot)
```

##Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Zeichne eine Linie. Klicke dann auf den roten Sprite und zeichne  noch ein bisschen. Ändert der Bleistift das Kostüm? Zeichnet er jetzt rot? Zeichnet er mit der Spitze des roten Malstifts?

SPEICHERE DEIN PROJEKT

5. Wiederhole das alles für den blauen, gelben und grünen Auswahl-Sprite.

##￼￼Teste Dein Projekt
__Klicke die grüne Fahne an.__

￼￼￼Funktionieren alle Farb-Auswahl-Knöpfe? Ändern sie alle die Kostüme des Malstifts in die richtige Farbe? Zeichnet der Stift immer in der richtigen Farbe? Zeichnen alle Kostüme mit der Spitze des Malstifts?

SPEICHERE DEIN PROJEKT

##SCHRITT 4: Zeichne nur innerhalb der Begrenzung

Wahrscheinlich hast Du bemerkt, dass Du auf der ganzen Bühne zeichnen kannst, selbst in den Rand hinein. Das soll nicht passieren. Die Zeichnung soll in der Mitte der Bühne bleiben. Das können wir erreichen, indem wir sicherstellen, dass der Malstift die Zeichenfläche nicht verlassen darf. Das ist die hellgraue Fläche auf der Bühne.


Erinnerst Du Dich daran, dass Scratch Punkte festlegen kann, indem es die x- und die y-Achse benutzt?￼￼￼￼￼￼￼ Unsere Zeichenfläche liegt zwischen 230 and -230 auf der x-Achse und 170 und -120 auf der y-Achse. Diese Werte können wir in einem __falls__ Block benutzen, um zu prüfen, ob sich der Mauszeiger innerhalb dieses Gebietes befindet, ehe wir den Malstift dorthin bewegen.

Hierfür musst Du einen neuen "falls"-Block um Deinen __gehe zu... falls__ Block herum bauen. Innerhalb des neuen "if"-Blocks kannst Du das prüfen:

Maus y-Position ist größer als -120 und Maus y-Position ist kleiner als 170
und
Maus x-Position ist größer als -230 und Maus x-Position ist kleiner als 230

__Achtung!__ Um das zu bauen brauchst Du mehrere __und__ Operatoren-Blöcke,einen für die beiden Maus x-Position-Bedingungen, einen für die beiden Maus y-Position-Bedingungen und einen letzten um sie alle miteinander zu verbinden:

```scratch
wische Malspuren weg
wiederhole fortlaufend
falls Maus y-Position > -120 und Maus y-Position < 170 und Maus x-Position > -230 und Maus x-Position < 230
gehe zu Mauszeiger
```

Da wir außerhalb der Zeichenfläche nicht zeichnen dürfen, könnten wir den Malstift verstecken, sobald er die Zeichenfläche verlässt.  Um das zu erreichen, kannst Du den  __falls__ gegen einen __falls sonst__ Block austauschen. Behalte die gleichen Bedingungen für das __falls__, __zeige__ den Malstift wenn es wahr ist und verstecke ihn wenn nicht.

```scratch
Wenn FAHNE angeklickt
hebe Stift an
wische Malspuren weg
wiederhole fortlaufend
falls Maus y-Position > -120 und Maus y-Position < 170 und Maus x-Position > -230 und Maus x-Position < 230
		gehe zu Mauszeiger
		zeige dich
		falls Maustaste gedrückt?
			senke Stift ab
		sonst
			hebe Stift an
		(ende falls)
	sonst
		verstecke dich
	(ende falls)
(ende wiederhole)
```

##Teste Dein Projekt
__Klicke die grüne Fahne an.__

Kannst Du immer noch innerhalb der Zeichenfläche malen? Kannst Du außerhalb der Zeichenfläche malen? Was passiert mit dem Malstift, wenn Du die Zeichenfläche verlässt und wieder  zurückgehst?
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼
SPEICHERE DEIN PROJEKT

##SCHRITT 5: Radiergummi

__￼￼￼￼Linien zeichnen macht Spaß, aber manchmal macht man einen Fehler und würde ihn gern wegradieren.__ Wir können das mit einem neuen Malstift-Werkzeug machen, das in grau zeichnet (derselben Farbe wie der Hintergrund).

Ergänze auf der Bühne einen neuen Knopf-Sprite um den Radiergummi auswählen zu können. Benutze das __resources/radiergummi__ dafür. Du musst es ein wenig verkleinern, damit es an den unteren Rand der Bühne passt. Es sollte genauso funktionieren wie die anderen Farb-Auswahl-Knöpfe und eine radiergummi-Nachricht schicken.

Der Malstift-Sprite sollte auf die Radiergummi-Nachricht antworten, indem er die Stiftfarbe auf grau umstellt (Denke daran, dass Du die __Pipette__ benutzen kannst, um die Farbe des Hintergrunds auszuwählen). Der Malstift braucht außerdem ein neues Kostüm um den Radiergummi darzustellen: benutze dasselbe __resources/radiergummi__ Kostüm. __Denke daran, den Mittelpunkt des Kostüms zu setzen.__

##Teste Dein Projekt
__Klicke die grüne Fahne an.__

Radiert der Radiergummi die Linien weg? Funktioniert es gut bis an die Ränder? Kannst Du zwischen Radiergummi und Malstift wechseln?

SPEICHERE DEIN PROJEKT

##￼￼￼SCHRITT 6: Stempel

Als nächstes möchten wir ein Stempel-Werkzeug bauen, mit dem Du kleine Bilder auf die Zeichnung stempeln kannst.

Aufgaben-Checkliste

1. Füge einen neuen Sprite hinzu. Benutze dafür ein Bild oder Kostüm, das Dir gefällt. Schrumpfe den Sprite und platziere ihn am unteren Rand des Bildschirms neben den anderen Werkzeugen. Wenn der Sprite angeklickt wird, sollte er __stempel senden__
2. Gib dem Malstift-Sprite ein weiteres Kostüm, dasselbe, das FDu für den __stempel__ Knopf ausgesucht hast.
3. Wähle den Malstift Sprite und erzeuge eine neue Variable __malstift-modus__ nur für diesen Sprite. Diese Variable werden wir benutzen um uns zu merken, ob wir grade stempeln oder zeichnen.
4. Erzeuge ein neues Skript um auf die Stempel-Nachricht zu reagieren. Das Kostüm muss zu "Stempel" wechseln und die  __malstift-modus__ Variable muss auf __false__ gesetzt werden.
5. Ändere die anderen Skripte, die auf Werkzeug-Auswahl-Nachrichten antworten (rot, grün, blau und radiergummi). Bei ihnen muss die  __malstift-modus__ Variable auf __true__ gesetzt werden.
6. Zum Schluss wollen wir diese Variable überprüfen, __wenn die Maustaste gedrückt ist__ um zu sehen, ob wir grade zeichnen oder stempeln sollten. Falls malstift modus = true sollten wir das bisherige __senke Stift ab__ benutzen, Falls nicht, sollten wir stattdessen stempeln. 

##￼￼￼￼￼￼￼￼￼￼￼Teste Dein Projekt
__Klicke die grüne Fahne an.__
￼￼
Funktioniert der Stempel richtig?

Was passiert, wenn Du zu einem der normalen Malstifte-Werkzeug wechselst?

SPEICHERE DEIN PROJEKT
￼
__Gut gemacht! Du hast die Grundlagen für den Malkasten gebaut.
Probiere diese Herausforderungen!__
￼￼￼
##Herausforderung 1: Regenbogen-Malstift

Lass' uns einen besonderen Malstift einbauen, der in Regenbogenfarben malt. Das ist etwas, das Du nicht mit normalen Buntstiften machen kannst. Dann kannst Du ein bisschen damit angeben, was man beim Zeichnen mit dem Computer so alles machen kann. Das Geheimnis dabei ist, die Malstift-Farbe mit Hilfe eines Block zu wechseln.

Baue als Erstes den Sprite für die Auswahl des Regenbogen-Werkzeugs ein und gib dem Malstift-Sprite das Regenbogen-Werkzeug-Kostüm:

1. Erzeuge einen neuen Werkzeug-Auswahl-Sprite und platziere es am Rand der Bühne, neben den anderen Farben-Sprites. Benutze das  resources/regenbogen-auswahl Kostüm und lass' es regenbogen senden, wenn es angeklickt wird.
2. Gib dem Malstift-Sprite das regenbogen-stift-Kostüm. (resources/regenbogen-stift)

Jetzt musst Du ein Skript bauen, das die Stiftfarbe viele Male pro Sekunde wechselt, um den Regenbogen-Effekt zu erzeugen. (Bei mir hat ändere Stiftfarbe um 5 alle 0.05 Sek. gut funktioniert, Du solltest aber unbedingt auch andere Werte ausprobieren). 
Die Timer-Scratch-Karte zeigt Dir, wie Du dafür sorgen kannst, dass etwas in einem bestimmten Rhythmus wechselt. Benutze einen  "ändere Stiftfarbe um 5"-Block statt eines "ändere timer um -1"-Blocks innerhalb der Schleife.

Du musst diese Schleife steuern, so dass sie die Stiftfarbe nur ändert, wenn der Regenbogenstift ausgewählt wurde, sonst haben alle Stifte den Regenbogen-Effekt. Das kannst auf ähnliche Weise lösen wie der Stift-Sprite zwischen Malstift und Stempel-Modus wechselt. Erzeuge eine neue Variable regenbogenWechsel, die den Wert "true" hat, wenn Du den Regenbogen-Effekt haben möchtest und sonst immer "false". Jedes Mal, wenn der Malstift auf eine Nachricht reagiert, sollte der Wert der regenbogenWechsel-Variable entsprechend gesetzt werden.

Benutze, was Du beim Einbau des Stempels gelernt hast, um den Regenbogen-Effekt zu steuern. Die Skripte, die auf die Werkzeug-Auswahl-Nachrichten reagieren, müssen jeweils zwei Variablen setzen: malstift modus und regenbogenWechsel.

##Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Funktioniert das Regenbogen-Werkzeug richtig?

Was passiert, wenn Du zu einem der normalen Malstifte wechseln möchtest?

SPEICHERE DEIN PROJEKT

##￼￼￼￼￼￼￼￼￼Herausforderung 2: Tastaturkürzel

Statt der Auswahl-Sprites am unteren Rand der Bühne kann man auch Tastatur-Kürzel benutzen, um die verschiedenen Werkzeuge auszuwählen.
Um mit der Tastatur arbeiten zu können kannst Du den "Wenn Taste [] gedrückt"-Block benutzen. Dabei brauchst Du einen Block für jede Taste, die Du benutzen möchtest. Dann wird dieselbe Botschaft gesendet wie wenn der jeweilige Auswahl-Sprite angeklickt worden wäre. Erzeuge bei der Bühne dieses Skripte.

Ich habe diese Tastaturkürzel benutzt:
* wische Malspuren weg - a
* Radiergummi - e
* Roter Stift -r 
* Blauer Stift - b
* Gelber Stift - y
* Grüner Stift - g
* Regenbogen-Stift - w
￼￼￼* Stempel - s

##Teste Dein Projekt
__Klicke die grüne Fahne an.__

￼￼Werden alle Werkzeuge richtig ausgewählt? Funktionieren alle Werkzeuge, wenn Du sie mit der Tastatur auswählst? Kann man die Werkzeuge auch noch über die Auswahl-Sprites auf der Bühne auswählen?

SPEICHERE DEIN PROJEKT

##Herausforderung 3: Groß und klein
Die meisten Zeichen-Werkzeuge haben eine weitere Funktion, nämlich die Größe des Malstifts zu verändern. Lasst uns das noch einbauen.
Dabei gibt es ein Problem: Wenn man die Größe verändert muss man manchmal die Größe des Stifts verändern und manchmal die Größe des Kostüms des Stifte-Sprites. Das hängt davon ab, ob wir einen Stift oder einen Stempel benutzen.

Erzeuge zwei neue Werkzeug-Auswahl-Sprites, die wir "groesser" und "kleiner" nennen wollen. Sie sollten die Kostüme resources/groesser-auswahl und resources/kleiner-auswahl und sollten die "groesser" und "kleiner"-Botschaft schicken.

Der Stifte-Sprite kann auf diese Botschaft reagieren, indem er die Stiftgröße um 1 bzw. die Kostüm-Größe um 10 verändert, abhängig vom Wert der Variable malstift-modus (benutze einen "falls... sonst"-Block, ähnlich wie der Sprite zwischen Stift absenken und Stempeln unterscheidet).
Vergiss nicht, auch für "groesser" und "kleiner" Tastenkürzel einzuführen. Ich habe die hoch/runter-Pfeile benutzt.

SPEICHERE DEIN PROJEKT

Ist Dir aufgefallen, dass wenn Du die Größe des Stempels veränderst, auch die Größe des Malstifts auf dem Bildschirm verändert wurde, sobald Du ihn ausgewählt hast.
Um das zu verhindern, musst Du die Größe wieder auf 100% setzen, sobald Du zu einem Stift wechselst. Auf diese Weise sehen die Werkzeuge von der Größe her immer richtig aus.

Um es noch besser zu machen, kannst Du den Stempel sich daran erinnern lassen, welche Größe er hatte, bevor Du den Stift ausgewählt hast. Er soll dann wieder zu der alten Größe zurückkehren, sobald er wieder gewählt wird.
Der einfachste Weg, um das zu erreichen ist, eine neue Variable namens "stempelGroesse" zu erzeugen. Sobald die Größe des Stempels verändert wird, wird ihr die neue Größe zugewiesen.
Sobald der Stempel dann angeklickt wird kann er sich die alte Größe aus dieser Variablen auslesen. 
￼￼￼￼￼￼￼￼
￼
##￼Teste Dein Projekt
__Klicke auf die grüne Fahne.__

Funktioniert bei den Malstiften die Steuerung der Größe?

Was passiert, wenn Du zum Stempel wechselst, die Größe änderst und wieder zu einem Stift wechselst?

SPEICHERE DEIN PROJEKT


__Toll gemacht! Du bist fertig. Jetzt kannst Du das Spiel genießen!__

Denke daran: Du kannst das Spiel mit Deinen Freunden und Deiner Familie teilen, indem Du in der Menüleiste __Teilen__ anklickst!