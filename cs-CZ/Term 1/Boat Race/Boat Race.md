---
title: Závod lodí
level: Scratch 1
language: cs-CZ
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*","Project Resources/*"]
...

# Úvod { .intro }

Naučíte se jak vytvořit hru, ve které budete používat myš k navigaci loďky na opuštěný ostrov.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/63957956/?autostart=false" frameborder="0"></iframe>
  <img src="boat-final.png">
</div>

# Step 1: Naplánování hry { .activity }

## Seznam úkolů { .check }

+ Vytovřte nový projekt a smažte kočičku, takže váš projekt bude prázdný. Online editor můžete nalézt zde: <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Naplánujte si váš level hry. Klikněte na "Stage backdrop". Měli byste přidat:
	+ Dřevo, kterému se bude loďka vyhýbat;
	+ Opuštěný ostrov, na kterém má loďka přistát.

	Tady je obrázek jak by měla vaše hra vypadat:

	![screenshot](boat-bg.png) 

# Step 2: Ovládání loďky { .activity }

## Seznam úkolů { .check }

+ Pokud vám dal vedoucí klubu adresář se soubory, klikněte na  'Upload sprite from file' a vyberte obrázek 'boat.png'. Měli byste zmenšit obrázek a vložit ho na startovní pozici.

	![screenshot](boat-boat.png)

	Pokud obrázek nemáte, můžete si loďku nakreslit!

+ Abyste mohli ovládat loďku myší, přidejte tento kód:

	```blocks
		when flag clicked
		point in direction (0 v)
		go to x: (-190) y: (-150)
		forever
			point towards [mouse-pointer v]
			move (1) steps
		end
	```

+ Otestujte loďku tak, že kliknete na zelenou vlaječku a hýbejte myší. Plave loďka za myší?

	![screenshot](boat-mouse.png)

+ Co se stane, když loďka doplave ke kurzoru myši?

	Abyste tomuto chování zabránili musíte přidat blok `if` {.blockcontrol} , tak, aby se loďka pohybovala jen když je dále než 5 pixelů od myši.

	![screenshot](boat-pointer.png)	

+ Vyzkoušejte znovu vaši loďku, zda byl problém vyřešen.

## Uložte projekt { .save }

# Step 3: Havárie! { .activity .new-page }

Nyní může vaše loďka proplouvat dřevěnýma bariérama! Pojďme to opravit.

## Seznam úkolů { .check }

+ Budete potřebovat dva "kystýmy" pro vaši loďku, jeden normální, a jeden pro loďku po nárazu. Zduplikujte kostým vaší loďky a nazvěte je 'normal' (normální) a 'hit' (náraz).

+ Klikněte na kostým 'hit' a vyberte nástroj 'Select' abyste loďku rozdělili na kousky a ty zrotovali. Upravte loďku tak, aby vypadala jako po nárazu.

	![screenshot](boat-hit-costume.png)

+ Přidjte tento kód k vaší loďce do bloku `forever` {.blockcontrol}, tak aby loďka narazila, jakmile se dotkne hnědého dřeva:

	```blocks
		if <touching color [#603C15]?> then
			switch costume to [hit v]
			say [Noooooo!] for (1) secs
			switch costume to [normal v]
			point in direction (0 v)
			go to x: (-215) y: (-160)
		end
	```

	Tento kód je ve smyčcce `forever` {.blockcontrol}, takže váš kód trvale kontroluje, zda nedochází k nárazu loďky.

+ Také musíte zajistit, aby loďka začínala nenabouraná - kostým 'normal'.

+ Nyní když loďka dopluje ke dřevu, měla by narazit a objevit se znovu na začátku.

	![screenshot](boat-crash.png)

## Uložte projekt { .save }

## Výhra! {.challenge}
Přidejte další blok s podmínkou `if` {.blockcontrol} do kódu loďky tak, aby hráč vyhrál, když se dostane na ostrov.

Když se loďka dostane na žlutý ostrov měla by říci 'YEAH!' a hra se zastaví. K tomu potřebujete následující kód:

```blocks
	say [YEAH!] for (1) secs
	stop [all v]
```

![screenshot](boat-win.png)

## Uložte projekt { .save }

## Zvukové efekty {.challenge}
Nyní můžete přidat zvukové efekty pro náraz nebo pro konec hry. Stejně tak můžete přidat hudbu na pozadi. (v projektu 'Rock Band' se naučíte jak).

## Uložte projekt { .save }

# Step 4: Závod na čas { .activity }

Přidejte do hry časovač proto, aby se hráč snažil dostat do cíle co nejrychleji.

## Seznam úkolů { .check }

+ Přidejte proměnnou nazvanou `time` {.blockdata} na stage. Můžete také změnit její vzhled, pokud chcete vědět jak, podívejte se na projekt 'Balónky'.

	![screenshot](boat-variable.png)

+ Přidejte tento kód na vaši  __stage__, tak aby se počítal čas, dokud loďka nedopluje na ostrov:

	```blocks
		when flag clicked
		set [time v] to [0]
		forever
			wait (0.1) secs
			change [time v] by (0.1)
		end
	```

+ To je ono! Vyzkoušejte hru a uvidíte jak rychlí dokážete být!

	![screenshot](boat-variable-test.png)

## Uložte projekt { .save }

# Step 5: Překážky a bonusy { .activity }

Nyní je hra moc jednoduchá - přidáme pár věcí aby byla zajímavější.

## Seznam úkolů { .check }

+ Jako první přidáme 'zrycchlovače'. Nakreslete do vaší hry několik bílých šipek.

	![screenshot](boat-boost.png)

+ Nyní je potřeba přidat do cyklu `forever` {.blockcontrol} pár říkazů tak, aby se loďka posunula rychleji o 2 _extra_ kroky, když najede na zryychlovač.

	```blocks
		if <touching color [#FFFFFF]?> then
			move (3) steps
		end
	```

+ Můžete také přidat otáčivou bránu, které se musí loďka vyhnout:

	![screenshot](boat-gate.png)

	Ujistěte se, že má stejnou barvu jako dřevěné bariéry.

+ Nastavte střed brány.

	![screenshot](boat-center.png)

+ Přidejte kód k bráně tak, aby so otáčela pomalu stále dokola v bloku `forever` {.blockcontrol}.

+ Vyzkoušejte si hru. Nyní by se měla objevit brána, která se otáčí a které se musíte vyhnout.

	![screenshot](boat-gate-test.png)

## Uložte projekt { .save }

## Výzva: více překážek! {.challenge .new-page}
Přidejte více překážek, tady je pár nápadů:

+ Můžete přidat zelený sliz, který hráče zpomalí. Použijte blok `wait` {.blockcontrol}:

```blocks
	wait (0.01) secs
````

![screenshot](boat-algae.png)

+ Přidejte pohyblivé objekty jako jsou plovoucí polena nebo žraloci!

![screenshot](boat-obstacles.png)

Tyto bloky vám pomůžou:

```blocks
	move (1) steps
	if on edge, bounce
````

Pokud není objekt hnědý musíte přidat následující kód k loďce:

```blocks
	if <  <touching color [#603C15]?> or <touching [shark v]?> > then
	end
```

## Uložte projekt { .save }

## Výzva: Více lodí! {.challenge .new-page}
Zkusíte změnit hru na závod mezi dvouma hráči?

+ Zduplikujte loďku,přejmenujte ji na 'Player 2' a změnte barvu.

![screenshot](boat-p2.png)

+ Změňte startovací pozici pro druhou loďku změnou kódu:

```blocks
	go to x: (-190) y: (-150)
```

+ Smažte kód pro kontrolu loďky myší:

```blocks
	if < (distance to [mouse-pointer v]) > [5] > then
		point towards [mouse-pointer v]
		move (1) steps
	end
```

...a nahraĎte ho kódem pro kontrolu pomocí šipek na klávesnici.

Toto je kód pro posun loďky dopředu:

```blocks
	if < key [up arrow v] pressed? > then
		move (1) steps
	end
```

Také budete potřebovat kód pro  otočení loďky - `turn` {.blockmotion} když stisknete levou a pravou šipku.

## Uložte projekt { .save }

## Více levelů! {.challenge .new-page}
Zkuste přidat více kulis - backdrops, a umožněte hráči přepínat.

```blocks
	when [space v] key pressed
	next backdrop
```

## Uložte projekt { .save }
