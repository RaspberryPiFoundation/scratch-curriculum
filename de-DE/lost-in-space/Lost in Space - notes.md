---
title: Lost in Space â€” Volunteer Notes
---

#Einführung:
In diesem Projekt lernen die Kinder, wie man Codeblöcke miteinander kombiniert, um eine einfache Animation zu erzeugen.

#Ressourcen
Für dieses Projekt sollte Scratch 2 benutzt werden. Scratch 2 kann entweder online benutzt werden unter [jumpto.cc/scratch-on](http://jumpto.cc/scratch-on) oder es kann von [jumpto.cc/scratch-off](http://jumpto.cc/scratch-off) heruntergeladen und offline benutzt werden.

Sie finden eine fertig gestellte Version dieses Projekts unter <a href="http://scratch.mit.edu/projects/26818098/#editor">online</a> oder es kann heruntergeladen werden, indem Sie auf den 'Project Materials' (Projektmaterialien) Link für dieses Projekt klicken, der u.a. Folgendes enthält:

+ LostInSpace.sb2

#Lernziele
+ Schleifen:
	+ `Repeat` {.blockcontrol} (Wiederholung) Schleifen;
	+ `Forever` {.blockcontrol} (Für immer) Schleifen.

Dieses Projekt deckt Elemente aus den folgenden Bereichen des [Raspberry Pi Lehrplans zur digitalen Produktion](http://rpf.io/curriculum):

+ [Einfach Programmierkonstrukte benutzen, um einfache Programme zu erstellen.](https://www.raspberrypi.org/curriculum/programming/creator)

#Aufgaben
+ „Verbessere deine Animation“: Ändern von Zahlen in einem kurzen Programm;
+ „Erstelle deine eigene Animation“: Wende das Gelernte an, um eine neue Animation herzustellen.

#Häufig gestellte Fragen (FAQ)
+ Die Kinder müssen evtl. daran erinnert werden, die Position, die Größe sowie andere Effekte eines Sprites beim Start der Animation wieder 'reset' (auf Null zu stellen). Dies kann einfach erzielt werden, indem manche der folgenden Blöcke zum Start der Animationen hinzugefügt werden:

```Blöcke
	gehe zu x:(0) y:(0)
```

```Blöcke
	Größe auf (100) % einstellen
```

```Blöcke
	Grafik-Effekte löschen
```

+ Das 'spaceship' (Raumschiff) Sprite wird sich seitwärts bewegen, es sei denn, es wird um 90 Grad im Uhrzeigersinn gedreht. Das Drehen des Raumschiffs ist Teil der Projektanweisungen. Falls dies Probleme bereiten sollte, kann jedoch ein anderes Sprite als Ersatz für das Raumschiff benutzt werden.

	![screenshot](images/space-rotate.png)