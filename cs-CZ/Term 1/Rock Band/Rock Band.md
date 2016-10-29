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

# Krok 1: Postavy { .activity }

Před tím, než začneš oživovat objekty, musíš nějaké přidat. Ve Scratchi se tyto objekty nazývají __postavy__. 

## Seznam úkolů { .check }

+ Jako první otevři Scratch editor. Online Scratch editor najdeš tady: <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>. Vypadá nějak takto:

	![screenshot](band-scratch.png)

+ Postava kočky, kterou vidíš je maskot Scratche. Té se pro tentokrát zbavíš tak, že na ni klikneš pravým tlačítkem a klikneš na 'smazat'.

	![screenshot](band-delete.png)

+ Dále klikni na 'Vybrat postavu z knihovny', aby se ti zobrazil seznam postav.

	![screenshot](band-sprite-library.png)

+ Skroluj dolů dokud nenajdeš buben. Klikni na něj a dále klikni na 'OK', tím ho přidáš do projektu.

	![screenshot](band-sprite-drum.png)

+ Klikni na ikonku 'Zmenši', a pak několikrát na postavu s bubnem, pro zmenšení.

	![screenshot](band-shrink.png)

## Ulož projekt { .save }

Dej programu název vepsáním do textového pole vlevo nahoře.

Pak stiskni 'Soubor' a potom 'Uložit aktuální stav' pro uložení projektu.

![screenshot](band-save.png)

# Krok 2: Scéna { .activity }

__Scéna__ je oblast nalevo, kde obživne tvůj projekt. Je to něco jako jeviště v divadle.

## Seznam úkolů { .check }

+ V tento okamžik je scéna bílá a vypadá docela nudně. Přidáme proto 'pozadí' kliknutím na 'Vybrat pozadí z knihovny'.

	![screenshot](band-stage-choose.png)

+ Klikni na kategorii 'Uvnitř' nalevo, a potom klikněte na "stage1" a 'OK'.

	![screenshot](band-backdrop.png)

+ Tvoje scéna by nyní měla vypadat takto:

	![screenshot](band-stage.png)

# Step 3: Tvorba bubnu { .activity }

Naprogramujeme buben aby vydával zvuk, když na něj klikneš.

## Seznam úkolů { .check }

+ Na záložce 'Scénáře' najdi bloky kódu, které jsou rozlišené podle barviček. 

	Klikni na postavu bubnu a potom přetáhni tyto dva bloky do oblasti pro kód vpravo, tak aby byly spojené dohromady (jako Lego kostky):

	![screenshot](band-code.png)

+ Klikni na buben, abys vyzkoušel(a) tvůj nový nástroj!

+ Můžeš také změnit jak vypadá bubdem, když na něj klikneš a to pomocí kostýmu. Klikni na záložku 'Kostýmy' a tam uvidíš obrázek bubnu.

	![screenshot](band-drum-costume.png)

+ Klikni pravým tlačítkem na kostým a vyber 'kopírovat', pro vytvoření kopie.

	![screenshot](band-drum-duplicate.png)

+ Klikni na nový kostým (nazvaný 'drum2') a vyber nástroj pro kreslení čar a nakresli čáry, tak aby to vypadalo, že buben vydává zvuky.

	![screenshot](band-drum-hit.png)

+ Jména kostýmů pro postavu bubnu nejsou nyní moc popisující, tak je přejmenuj na 'hraje' a 'nehraje' vepsáním jména do textového pole.

	![screenshot](band-drum-name.png)

+ Nyní máš pro buben dva různé kostýmy a můžeš s vybrat, který se zobrazí. Přidej tyto dva bloky kódu k bubnu:

	![screenshot](band-looks.png)

	Bloky pro změnu kostýmu najdeš v sekci `Vzhled` {.blocklooks}.

+ Vyzkoušej buben. Po kliknutí by měl měnit vzhled a hrát.

## Ulož projekt { .save }

##Výzva: Vylepšení bubnu { .challenge }

+ Zkusíš změnit zvuk který buben vydává?

![screenshot](band-drum-sound.png)

+ Zkus upravit buben tak, aby hrál při stisknutí mezerníku. Budeš potřebovat tento blok `událost` {.blockevents}:

```blocks
	po stisku klávesy [space v]
```

Existující kód můžeš zkopírovat tak, že klikneš pravým tlačítkem myši a vybereš 'duplicate'.

![screenshot](band-duplicate-code.png)

## Ulož projekt { .save }

# Step 4: Vytvoření zpěvačky { .activity .new-page }

Přidej zpěvačku do tvé skupiny!

## Seznam úkolů { .check }

+ Přidej na scénu další dvě postavy: zpěvačku a mikrofon.

	![screenshot](band-singer-mic.png)

+ Před tím, než naučíš zpěvačku zpívat, potřebuješ přidat zvuk k postavě. Ujisti se že máš vybranou zpěvačku, pak klikni na záložku 'Zvuky' a klikni na 'Vybrat zvuk z knihovny':

	![screenshot](band-import-sound.png)

+ Když klikneš vlevo na 'Hlasy', můžeš potom vybrat zvuk a přidat ho k postavě.

	![screenshot](band-choose-sound.png)

+ Nyní po přidání zvuku přidej následující kód ke zpevačce:

	```blocks
		po kliknutí na mě
		hraj zvuk [singer1 v] až do konce
	```

+ Klikni na zpěvačku aby ses ujistil(a), že zpívá.

## Ulož projekt { .save }

##Vývza: Změň zpěvačce kostým { .challenge }
Můžeš upravit zpěvačku tak, aby vypadala, že zpívá po kliknutí? Pokud nevíš jak, udělej to stejně jako u bubnu.

![screenshot](band-singer-final.png)

Nezapomeň vyzkoušet jestli tvůj nový kód funguje!

## Ulož projekt { .save }

##Výzva: Vytvoř si svoji hudební skupinu { .challenge }
Pomocí toho co jsi se již naučil(a) si vytovř svoji skupinu! Můžeš vytvořit jakýkoliv nástroj - podívej se do galérie na dostupné postavy a zvuky.

![screenshot](band-ideas.png)

Tvoje nástroje nemusí mít smysl. Například můžeš udělat piáno z mufinů!

![screenshot](band-piano.png)

Tak jak používáš existující postavy, můžes si nakreslit vlastní.

![screenshot](band-draw.png)

Pokud máš mirkofon, tak si nahraj vlastní zvuk, nebo můžeš použít kameru na spouštění nástrojů!

![screenshot](band-io.png)

## Ulož projekt { .save }
