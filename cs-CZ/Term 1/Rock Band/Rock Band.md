---
title: Rocková skupina
level: Scratch 1
language: cs-CZ
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*"]
...

# Úvod { .intro }

V tomto projektu se naučíš jak naprogramovat vlastní hudební nástroje!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26741186/?autostart=false" frameborder="0"></iframe>
  <img src="band-final.png">
</div>

# Step 1: Objekty - sprajty { .activity }

Před tím, než začneš oživovat objekty, musíš nějaké přidat. Ve Scratchi se tyto objekty nazývaji __sprites__ (sprajty). 

## Seznam úkolů { .check }

+ Jako první otevři Scratch editor. Online Scratch editor najdeš tady: <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>. Vypadá nějak takto:

	![screenshot](band-scratch.png)

+ Sprajt kočky, který vidíš je maskot Scratche. Té se pro tentokrát zbavíš tak, že na ni klikneš pravým tlačítkem a klikneš na 'delete'.

	![screenshot](band-delete.png)

+ Dále klikni na 'Choose sprite from library' aby se ti zobrazil seznam sprajtů.

	![screenshot](band-sprite-library.png)

+ Skroluj dolů dokud nenajdeš sprajt s bubnem. Klikni na něj a dále klikni na 'OK', tím ho přidáš do projektu.

	![screenshot](band-sprite-drum.png)

+ Klikni na ikonku 'shrink', a pak několikrát na sprajt s bubnem, abys ho zmenšil(a).

	![screenshot](band-shrink.png)

## Ulož projekt { .save }

Dej programu název vepsáním do textového pole vlevo nahoře.

Pak stiskni 'File' a potom 'Save now' pro uložení projektu.

![screenshot](band-save.png)

# Step 2: Scéna { .activity }

Scéna - __stage__ je oblast nalevo, kde obživne tvůj projekt. Je to něco jako jeviště v divadle.

## Seznam úkolů { .check }

+ V tento okamžik je scéna bílá a vypadá docela nudně. Přidáme proto 'kulisy' kliknutím na 'Choose backdrop from library'.

	![screenshot](band-stage-choose.png)

+ Klikni na 'Indoors' nalevo, a potom klikněte na "Stage 1 backdrop" a 'OK'.

	![screenshot](band-backdrop.png)

+ Tvoje scéna by nyní měla vypadat takto:

	![screenshot](band-stage.png)

# Step 3: Tvorba bubnu { .activity }

Naprogramujeme buben aby vydával zvuk, když na něj klikneš.

## Seznam úkolů { .check }

+ Na záložce 'Scripts' najdi bloky kódu, které jsou rozlišené podle barviček. 

	Klikni na sprajt bubnu a potom přetáhni tyto dva bloky do oblasti pro kód vpravo, tak aby byly spojené dorhromady (jako Lego kostky):

	![screenshot](band-code.png)

+ Klikni na buben, abys vyzkoušel(a) tvůj nový nástroj!

+ Můžeš také změnit jak vypadá bubdem, když na něj klikneš, pomocí kostýmu. Klikni na záložku 'Costumes' a tam uvidíš obrázek bubnu.

	![screenshot](band-drum-costume.png)

+ Klikni pravým tlačítkem na kostým a vyber 'duplicate', abys vytvořil(a) kopii.

	![screenshot](band-drum-duplicate.png)

+ Klikni na nový kostým (nazvaný 'drum2') a vyber nástroj pro kreslení čara nakresli čáry, tak aby to vypadalo, že buben vydává zvuky.

	![screenshot](band-drum-hit.png)

+ Jména kostýmů pro sprajt bubnu nejsou nyní moc popisující, tak je přejmenuj na 'not hit' a 'hit' vepsáním jména do textového pole.

	![screenshot](band-drum-name.png)

+ nyní máš pro buben dva různé kostýmy a můžeš s vybrat, který se zobrazí. Přidej tyto dva bloky kódu k bubnu:

	![screenshot](band-looks.png)

	Bloky pro změnu kostýmu najdeš v sekci `Looks` {.blocklooks} section.

+ Vyzkoušej buben Test your drum. Po kliknutí by měl měnit vzhled a hrát.

## Ulož projekt { .save }

##Výzva: Vylepšení bubnu { .challenge }

+ Zkusíš zmenit zvuk který buben vydává??

![screenshot](band-drum-sound.png)

+ Zkusíš upravit buben tak, aby hrál při stisknutí mezerníku? Budeš potřebovat tento blok `event` {.blockevents}:

```blocks
	when [space v] key pressed
```

Existující kód můžeš zkopírovat tak, že klikneš pravým tlačítkem myši a vybereš 'duplicate'.

![screenshot](band-duplicate-code.png)

## Ulož projekt { .save }

# Step 4: Vytvoření zpěváka { .activity .new-page }

Přidej zpěváka do tvé skupiny!

## Seznam úkolů { .check }

+ Přidej na scénu další dva sprajty: zpěvačku a mikrofon.

	![screenshot](band-singer-mic.png)

+ Před tím než naučíš zpěvačku zpívat, potřebuješ přidat zvuk do sprajtu. Ujisti se že máš vybranou zpěvačku, pak klikni na záložku 'Sounds' tab, a klikni na 'Choose sound from library':

	![screenshot](band-import-sound.png)

+ Když klikneš vlevo na 'Vocals', můžeš potom vybrat zvuk a přidat ho ke sprajtu.

	![screenshot](band-choose-sound.png)

+ Nyní po přidání zvuku přidej následující kód ke zpevačce:

	```blocks
		when this sprite clicked
		play sound [singer1 v] until done
	```

+ Klikni na zpěvačku aby ses ujistil(a), že zpívá.

## Ulož projekt { .save }

##Vývza: Změň zpěvačce kostým { .challenge }
Můžeš upravit zpěvačku tak, aby vypadala, že zpívá po kliknutí? Pokud nevíš jak, udělej to stejně jako u bubnu.

![screenshot](band-singer-final.png)

Nezapomeň vyzkoušet jestli tvůj nový kód funguje!

## Ulož projekt { .save }

##Výzva: Vytvoř si svoji hudební skupinu { .challenge }
Pomocí toho co jsi se již naučil(a) si vytovř svoji skupinu! Můžeš vytvořit jakýkoliv nástroj - podívej se do galérie na dostupné sprajty a zvuky.

![screenshot](band-ideas.png)

Tvoje nástroje nemusí mít smysl. Například můžeš udělat piáno z mufinů!

![screenshot](band-piano.png)

Tak jak používáš existující sprajty, můžes si nakreslit vlastní.

![screenshot](band-draw.png)

Pokud máš mirkofon, tak si nahraj vlastní zvuk, nebo můžeš použít kameru na spoštění nástrojů!

![screenshot](band-io.png)

## Ulož projekt { .save }
