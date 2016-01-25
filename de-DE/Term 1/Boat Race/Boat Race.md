---
title: Boat Race
level: Scratch 1
language: de-DE
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*","Project Resources/*"]
...

# Einleitung { .intro }

Du wirst lernen ein Spiel zu programmieren, in dem du mit der Maus ein Boot zur einer Insel steuerst.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/63957956/?autostart=false" frameborder="0"></iframe>
  <img src="boat-final.png">
</div>

# Schritt 1: Plane dein Spiel { .activity }

## Arbeitsschritte { .check }

+ Öffne ein neues Scratch-Projekt und lösche die Katzen-Figur, so dass dein Projekt leer ist. Du kannst den online Scratch-Editor hier finden: <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Klicke auf Bühnenbilder und zeichne dein Level. Du solltest hinzufügen:
	+ Die Holzbalken, um die dein Boot fahren wird;
	+ Die Insel, zu dem das Boot fahren soll.
	
	Hier ein Beispiel, wie dein Spiel aussehen könnte:

	![screenshot](boat-bg.png) 

# Schritt 2: Boot steuern { .activity }

## Arbeitsschritte { .check }

+ Wenn du vom Lehrer den Zugang zum 'Resources' Verzeichnis bekommen hast, klicke auf "Figur aus einer Datei laden" und füge die Bilddatei 'boat.png' hinzu. Verkleinere die Figur und stelle sie auf die Startposition.

	![screenshot](boat-boat.png)

	Wenn du das boat.png image nicht hast, mal dein eigenes Boot!

+ Du wirst das Boot mit deiner Maus Steuern. Füge diesen code zu deinem boot hinzu:

	```blocks
		when flag clicked
		point in direction (0 v)
		go to x: (-190) y: (-150)
		wiederhole fortlaufend
			point towards [mouse-pointer v]
			move (1) steps
		end
	```

+ Teste dein Boot, indem du die Flagge anklickst und die Maus bewegst. Segelt das Boot in Richtung der Maus?

	![screenshot](boat-mouse.png)

+ Was passiert wenn das Boot den Mauszeiger berührt?

	Um es zu verhindern, füge ein `falls` {.blockcontrol} Skript zu deinem Code hinzu, sodass sich das Boot nur bewegt, wenn es mehr als 5 Pixel von der Maus entfernt ist.

	![screenshot](boat-pointer.png)	

+ Teste dein Boot wieder und überprüfe, ob das Problem gelöst ist.

## Speichere dein projekt { .save }

# Schritt 3: Unfall! { .activity .new-page }

Dein Boot kann durch die braunen Holzbalken hindurch segeln! Das ändern wir jetzt.

## Arbeitsschritte { .check }

+ Du brauchst 2 Kostüme für dein Boot: Ein normales Kostüm, und eins für ein kaputtes Boot. Dupliziere das Boot Kostüm, und nenne sie 'Normal' und 'Kaputt'.

+ Klicke dein 'Kaputt' Kostüm und dann das 'Auswählen' Werkzeug an. Damit zerlegst du das Boot in Teile, bewegst und drehst sie. Lasse das Boot so aussehen als hätte es einen Unfall gebaut.

	![screenshot](boat-hit-costume.png)

+ Füge diesen Code zu deinem Boot hinzu, innerhalb der `wiederhole fortlaufend` {.blockcontrol} Schleife. Damit baut dein Boot jedes mal einen Unfall, wenn es einen der braunen Holzbalken berührt:

	```blocks
		if <touching color [#603C15]?> then
			switch costume to [Kaputt v]
			say [Oh Nein!] for (1) secs
			switch costume to [Normal v]
			point in direction (0 v)
			go to x: (-215) y: (-160)
		end
	```

	Dieser Code gehöhrt in die `wiederhole fortlaufend` {.blockcontrol} Schleife, sodass dein Code immer prüft, ob das Boot einen Unfall gebaut hat oder nicht.

+ Stelle sicher, dass dein Boot immer in dem 'Normal' Zustand startet.

+ Wenn du nun versuchst durch einen Holzbalken zu segeln, wirst du sehen, dass dein Boot kaputt geht und zum Start zurückkehrt.

	![screenshot](boat-crash.png)

## Speichere dein Projekt { .save }

## Herausforderung: Gewinnen! {.challenge}
Kannst du noch ein `falls` {.blockcontrol} Skript zu dem Code deines Bootes, sodass der Spieler gewinnt wenn er zur Wüsteninsel kommt?

Wenn das Boot zur gelben Wüsteninsel kommt, soll es 'JA-A-A!' sagen und das Spiel soll anhalten. Du wirst diesen Code benötigen:

```blocks
	say [JA-A-A!] for (1) secs
	stop [all v]
```

![screenshot](boat-win.png)

## Speichere dein Projekt { .save }

## Herausforderung: Musik effekte {.challenge}
Kannst du Musikeffekte zu deinem Spiel hinzufügen, falls dein Boot einen Unfall baut oder die Insel erreicht? Du könntest sogar Hintergrundmusik einfügen (schau dir das letzte projekt 'Rock-Band' an, wenn du Hilfe brauchst).

## Speichere dein Projekt { .save }

# Step 4: Zeitfahren { .activity }

Lass uns einen Timer zum Spiel hinzufügen. Damit soll der Spieler versuchen, so schnell wie möglich zur Wüsteninsel zu kommen.

## Arbeitsschritte { .check }

+ Füge eine neue Variable  namens `Zeit` {.blockdata} zu deiner Bühne hinzu. Du kannst auch das Aussehen  der Variable ändern. Wenn du Hilfe brauchst schaue dir das 'Luftballons' Projekt an.

	![screenshot](boat-variable.png)

+ Füge diesen Code zu deiner __Bühne__ hinzu, sodass der Timer läuft bis das Boot an der Wüsteninsel ankommt:

	```blocks
		when flag clicked
		set [time v] to [0]
		forever
			wait (0.1) secs
			change [time v] by (0.1)
		end
	```

+ Das war's! Teste dein Spiel und versuch, so schnell wie möglich zur Wüsteninsel zu kommen.

	![screenshot](boat-variable-test.png)

## Speichere dein Projekt { .save }

# Step 5: Hindernisse und Schübe { .activity }

Dieses Spiel ist _viel_ zu leicht - Lass uns ein paar Dinge hinzufügen, um es spannender zu machen.

## Arbeitsschritte { .check }

+ Als erstes füge ein paar 'Schübe' zu deinem Spiel, die das Boot beschleunigen. Ändere deinen Bühnen backdrop und füge ein paar weiße Schubpfeile hinzu.

	![screenshot](boat-boost.png)

+ Füge jetzt einen anderen Code zu deiner `wiederhole fortlaufend` {.blockcontrol} Schleife hinzu, sodass es 2 _extra_ Schritte macht, wenn es über einen Schubpfeil fährt.

	```blocks
		if <touching color [#FFFFFF]?> then
			move (3) steps
		end
	```

+ Du kannst ein drehendes Tor erstellen, das dein Boot meiden soll. Füge ein neues Kostüm dazu und nenne es 'Tor'. So soll es aussehen:

	![screenshot](boat-gate.png)

	Die Farbe des Tors soll mit der Farbe der Holzbalken übereinstimmen.

+ Markiere den Drehpunkt des Kostüms.

	![screenshot](boat-center.png)

+ Füge den Code `wiederhole fortlaufend` {.blockcontrol} hinzu, damit sich das Tor sich langsam dreht.

+ Teste das Spiel. Jetzt sollst du ein drehendes Tor sehen, dass du lieber umschiffen sollst.

	![screenshot](boat-gate-test.png)

## Speichere dein Projekt { .save }

## Herausforderung: Noch mehr Hindernisse! {.challenge .new-page}
Kannst Du noch mehr Hindernisse in dein Spiel einbauen? Hier sind ein paar Ideen:

+ Du kannst einen Schlammgebiet ins Bühnenbild einfügen, das das Boot verlangsamt, wenn es in den Schlamm reinsegelt. Nutze dafür das `warte` {.blockcontrol} Skript:

```blocks
	wait (0.01) secs
````

![screenshot](boat-algae.png)

+ Du kannst ein Objekt einfügen, das sich ständig bewegegt, z.B. einen Holzklotz oder einen Hai sein!

![screenshot](boat-obstacles.png)

Diese Skripte können dir helfen:

```blocks
	move (1) steps
	if on edge, bounce
````

Wenn das neue Objekt ist nicht braun, denke dran, seine Farbe im Code aufzunehmen:

```blocks
	if <  <touching color [#603C15]?> or <touching [shark v]?> > then
	end
```

## Speichere dein Projekt { .save }

## Herausforderung: Mehr Boote! {.challenge .new-page}
Kannst du das Spiel so ausbauen, dass zwei Spieler das gleichzeitig spielen können.

+ Dupliziere das Boot, nenne es 'Spieler 2' und ändere seine Farbe.

![screenshot](boat-p2.png)

+ Ändere die Startposition des Spieler 2, indem du diesen Code änderst:

```blocks
	go to x: (-190) y: (-150)
```

+ Lösche den Code für die Maussteuerung:

```blocks
	if < (distance to [mouse-pointer v]) > [5] > then
		point towards [mouse-pointer v]
		move (1) steps
	end
```

...und ersetze ihn mit dem Code für die Tastatursteuerung mit den Pfeiltasten.

Mit diesem Code wird das Boot vorwärts bewegt:

```blocks
	if < key [up arrow v] pressed? > then
		move (1) steps
	end
```

Du brauchst auch den Code zum `drehen` {.blockmotion} des Boots, wenn der Spieler auf die Pfeiltasten 'Links' oder 'Rechts' drückt.

## Speichere dein Projekt { .save }

## Herausforderung: Weitere Levels! {.challenge .new-page}
Kannst du weitere Bühnen erstellen und dem Spieler erlauben, einen Level auszuwählen?

```blocks
	when [space v] key pressed
	next backdrop
```

## Speichere dein Projekt { .save }

## Community Contributed Translation { .challenge .pdf-hidden }

This project was translated by Ilja Gendler and Oleg Bascurov. Our amazing translation volunteers help us give children around the world the chance to learn to code.  You can help us reach more children by translating a Code Club project via [Github](https://github.com/CodeClub/curriculum_documentation/blob/master/contributing.md) or by getting in touch with us at hello@codeclubworld.