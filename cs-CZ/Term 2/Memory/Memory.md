---
title: Paměť
level: Scratch 2
language: cs-CZ
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*"]
...

## Komunitní projekt { .challenge .pdf-hidden }
Tento projekt vytvořil Erik se svou dcerou Ruth. Budeme rádi, když přispějete i vy svým nápadem, všechen [kód najdete na  Githubu](https://github.com/CodeClub).

# Úvod { .intro }

V tomto projektu vytvoříš hru, kdy si musíš zapamatovat a zopakovat řadu náhodných barev!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/34874510/?autostart=false" frameborder="0"></iframe>
  <img src="colour-final.png">
</div>

# Krok 1: Náhodné barvy { .activity }

Vytvořme postavičku, která bude měnit barvy. Tyto si hráč snaží zapamatovat.

## Postup { .check }

+ Vytvoř nový projekt ve Scratchi a smaž kočičí sprite tak, aby byl projekt prázndý. Webový scratch editor najdeš na <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Vyber si postavičku a pozadí scény. Postavička nemusí být člověk, ale musí být jednoduché ji přemalovat na jinou barvu (mít kostýmy).

	![screenshot](colour-sprite.png)

+ V této hře budeš používat čísla zastupující jednotlivé barvy:

	+ 1 = červená;
	+ 2 = modrá;
	+ 3 = zelená;
	+ 4 = žlutá.

	Dej svojí postavičce 4 různě barevné kostýmy, pro kažou zmíněnou barvu jeden (zkopíruj kostým a/nebo v editoru změň barvu). Zkontroluj, že jsou barvy oblečků ve správném pořadí.

	![screenshot](colour-costume.png)

+ Pro náhodnou sekvenci budeš potřebovat  __seznam__. Seznam je jednoduše proměnná, která si pamatuje více hodnot __v určitém pořadí__. Vytvoř novou proměnnou - seznam, který se bude jmenovat `sekvence` {.blockdata}. Seznam bude potřeba pouze pro postavičku, zaklikni také 'Pouze pro tento sprite'.

	![screenshot](colour-list.png)

	Teď by měl být vidět prázdný seznam nahoře a k tomu spoustu nových bloků pro použití se seznamem.

	![screenshot](colour-list-blocks.png)

+ Přidej k postavičce následující blok kódu. Tím se k seznamu přidá náhodné číslo (také se přepne obleček), to se opakuje celkem 5 krát, jednou za vteřinu:

	```blocks
		when flag clicked
		delete (all v) of [sequence v]
		repeat (5)
			add (pick random (1) to (4)) to [sequence v]
			switch costume to (item (last v) of [sequence v]
			wait (1) secs
		end
	```

	Všimni si, že jsme seznam na začátku vyprázdnili.

## Výzva: Přidej zvuk {.challenge}
Spusť několikrát svůj projekt. Všimni se, že se občas stane, že to samé číslo je vybrané dvakrát (nebo víckrát) za sebou, takže je těžší si to správně zapamatovat. Dokážeš zahrát zvuk bubnu pokaždé, když se postavičce změní kostým?

Dokážeš nechat zahrát různý zvuk bubnu, podle toho, jaké náhodné číslo bylo vybráno? Bude to _velmi_ podobné kódu na změnu kostýmu.

## Ulož svůj projekt { .save }

# Krok 2: Zopakování sekvence { .activity }

Přidejme 4 tlačítka, která bude hráč mačkat, aby zopakoval sekvenci, kterou si zapamatoval.

## Postup { .check }

+ Přidej do projektu 4 sprity bubnů, které budou sloužit, jako tlačítka. Nastav jim naše 4 barvy.

	![screenshot](colour-drums.png)

+ Když se klikne na červený buben, je třeba vyslat zprávu postavičce, aby věděla, že bylo zmáčknuté čerené tlačítko. Přidej následující kus kódu k červenému bubnu:

	```blocks
		when this sprite clicked
		broadcast [red v]
	```

+ Když tvá postavička zprávu obdrží, musí zkontrolovat, že je na prvním místě v seznamu číslo 1 (to znamená, že je to červená). Pokud ano, odstraní ze seznamu první prvek, protože hráč uhádl správně. Pokud ne, tak game over!

	```blocks
		when I receive [red v]
		if <(item (1 v) of [sequence v])=[1]> then
			delete (1 v) of [sequence v]
		else
			say [Game over!] for (1) secs
			stop [all v]
		end
	```

+ Také můžeš přidat efekt zablikáním světel, když je seznam prázdný, to znamená, že všechno bylo uhodnuto správně. Přidej tento blok kódu na konec skriptu `when flag clicked` {.blockevents} u postavičky:

	```blocks
		wait until < (length of [sequence v]) = [0]>
		broadcast [won v] and wait
	```

+ Klikni do scény a přidej následující kód, pozadí pak bude měnit barvu, když hráč vyhrál.

	```blocks
		when I receive [won v]
		play sound [drum machine v]
		repeat (50)
			change [color v] effect by (25)
			wait (0.1) secs
		end
		clear graphic effects
	```

## Výzva: Vytvoř 4 tlačítka {.challenge}
Zopakuj zmíněný postup i pro modré, zelené a žluté tlačítko. Jaký kód zůstane stejný a jaký se musí pro každé tlačítko upravit?

Také můžeš přidat pro každé tlačítko zvuk.

Nezapomeň pokažé úpravě kód spustit a otestovat! Dokážeš si zapamatovat sekvenci 5 barev? Je sekvence po každé jiná?

## Ulož svůj projekt { .save }

# Krok 3: Více levelů { .activity .new-page }

Doteď si hráč musel zapamatovat 5 po sobě jdoucích barev. Pojďme hru vylepšit tak, že se bude zvětšovat počet barev k zapamatování v sekvenci.

## Postup { .check }

+ Vytvoř novou proměnnou `score` {.blockdata}.

	![screenshot](colour-score.png)

+ Toto `score` {.blockdata} bude použité k určení délky sekvence, kterou si hráč musí zapamatovat. Na začátek nastavíme skóre (a tím déklu sekvence) na hodnotu 3. Přidej tento kód na začátek bloku `when flag clicked` {.blockevents} u tvé postavičky:

	```blocks
		set [score v] to [3]
	```

+ Místo současné neměnné délky 5 teď chceme, aby `score` {.blockdata} určovalo déklu sekvence. Změň smyčku `repeat` {.blockcontrol} u své postavičky (vytváření sekvence) na:

	```blocks
		repeat (score)
		end
	```

+ Pokud budou všechny barvy uhodnuty správně, přidáme ke skóre 1, tím prodloužíme sekvenci.

	```blocks
		change [score v] by (1)
	```

+ Nakonec musíš přidat nekonečnou smyčku `forever` {.blockcontrol} kolem kódu pro generování sekvence, tak aby se vytvořila sekvence pro každý level. Takhle by měl vypadat tvůj kód u postavičky:

	```blocks
		when flag clicked
		set [score v] to [3]
		forever
			delete (all v) of [sequence v]
			repeat (score)
				add (pick random (1) to (4)) to [sequence v]
				switch costume to (item (last v) of [sequence v]
				wait (1) secs
			end
			wait until < (length of [sequence v]) = [0]>
			broadcast [won v] and wait
			change [score v] by (1)
		end
	```

+ Zavolej kamarády, ať přijdou vyzkoušet tvou hru. Nezapomeň schovat okno seznamu `sekvence` {.blockdata} než začnou hrát!

## Ulož svůj projekt { .save }

# Krok 4: High score { .activity }

Pojďme ukládat skóre, abys mohl soutěžit s kamarády.

## Postup { .check }

+ Do projektu přidej 2 proměnné, nazveme je `high score` {.blockdata} a `name` {.blockdata}.

+ Pokaždé, když hra skončí (hráč zmáčknul špatné tlačítko), zkontrolujeme, jestli právě nahrané skóre není vyšší, než to, které máme uložené. Pokud ano, uložíme si score jako high score a uložíme si jméno hráče. Tady je, jak by měl vypadat skript u tvého červeného tlačítka:

	```blocks
		when I receive [red v]
		if <(item (1 v) of [sequence v])=[1]> then
			delete (1 v) of [sequence v]
		else
			say [Game over!] for (1) secs
			if < (score) > (high score) > then
				set [high score v] to (score)
				ask [High score! What is your name?] and wait
				set [name v] to (answer)
			end
			stop [all v]
		end
	```

+ Tento kód musíš také vložit ke zbývajícím 3 tlačítkům! Všimnul(a) sis, že kód pro 'Game over' je stejný u všech 4 tlačítek?

	![screenshot](colour-same.png)

+ Když se rozhodneš upravit část kódu, jako třeba zvuk nebo nápis 'Game over', budeš to muset udělat 4-krát! To může být otrava a ztráta zpousty času.

	Místo toho si raději zadefinujeme vlastní blok a použijeme _(reuse)_ ho v našem projektu. Klikni na `nové bloky` {.blockmoreblocks} a potom 'Vytvořit blok'. Tento nový blok nazveme 'Game over'.

	![screenshot](colour-more.png)

+ Zkopíruj kód z větve `else` {.blockcontrol} z bloku u červeného tlačítka do nového bloku:

	![screenshot](colour-make-block.png)

+ Právě jsi vytvořil(a) novou _funkci_ nazvanou `Game over` {.blockmoreblocks}, Kterou můžeš použít, kdekoliv budeš potřebovat. Přetáhni nový blok `Game over` {.blockmoreblocks} do kódu všech 4 tlačítek.

	![screenshot](colour-use-block.png)

+ Teď přidej zvuk, který zazní, když se zmáčkne špatné tlačítko. Tentokrát stačí přidat kód _pouze jednou_ do bloku `Game over` {.blockmoreblocks} a už ne 4-krát samostatně, hurá!

	![screenshot](colour-cough.png)

## Výzva: Vytvoření více bloků {.challenge}
Všimnul(a) sis nějaké další části kódu, která je stejná u všech 4 tlačítek?

![screenshot](colour-more-blocks.png)

Dokážeš udělat další nový blok, který budou tlačítka používat?

## Ulož svůj projekt { .save }

## Výzva: Jiný kostým {.challenge}
Všimnul(a) sis, že hra začíná s postavičkou ukazující jednu barvu a také, že když hráč zadává sekvenci, zůstává zobrazená poslední barva?

Dokážeš přidat postavičce další, čistě bílý kostým, který se ukáže na začátku hry a během toho, co se hráč snaží zadat sekvenci?

![screenshot](colour-white.png)

## Ulož svůj projekt { .save }

## Výzva: Obtížnost {.challenge}
Dokážeš nechat hráče zvolit mezi 'easy mode' (pouze červený a modrý buben) a 'normal mode' (všechny 4 bubny)?

Klidně můžeš přidat 'hard mode', který bude s 5. bubnem!

## Ulož svůj projekt { .save }
