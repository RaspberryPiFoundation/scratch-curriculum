---
title: Dodgeball
level: Scratch 2
language: cs-CZ
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*","Project Resources/*"]
...

# Úvod { .intro }

V tomto projektu se naučíš jak vytvořit plošinovku, kde se musíš vyhnout pohybujicích se míčů a dostat se až na konec levelu.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/39740618/?autostart=false" frameborder="0"></iframe>
  <img src="dodge-final.png">
</div>

# Krok 1: Pohyb postavy { .activity }

Nejdřiv vytvoříme postavu která se může pohybovat doleva a doprava, a taky šplhat po tyčích.

## Postup { .check }

+ Vytvoř si nový projekt a smaž kočičku, takže tvůj projekt bude prázndý. Webový editor najdeš na <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.
+ Pro tento projekt bys měl mít složku 'Project Resources', kde bude obrázek s pozadím, který použiješ. Přesvědč si že víš kde tato složka je, a pokud ne zeptej se tvého vedoucího týmu.

	![screenshot](dodge-resources.png)

+ Přidej obrázek 'background.png' jako nový pozadí scény, nebo si nakresli vlastní! Pokud budeš kreslit vlastní úroveň, ujisti se ze tyče a podlahy mají jiné barvy, a že tam jsou dveře (nebo něco jiného) kam musíš se svou postavičkou dojít. Takhle nějak by měl tvůj obrázek vypadat:

	![screenshot](dodge-background.png)

+ Přidej nový sprite, který bude tvou postavou. Vyber si raději sprite s více kostýmy, aby jsi mohl udělat jako že postava chodí.

	![screenshot](dodge-characters.png)

+  Budeme používat šípky aby jsi pohyboval postavou. Když hráč zmáčkne pravou šipku, chceš aby tvoje postava se otočila doprava, udělala několik kroků a vyměnila do dalšího kostýmu:

```blocks
  po kliknutí na ⚑
  opakuj dokola
    když <klávesa [šipka vpravo v] stisknuta?> tak
      natoč se směrem (90 v)
      posuň se o (3) kroků
      další kostým
    end
  end
```
+ Vyzkoušej pohyb své postavy kliknutím na tyčku a pak podržením šipky doprava. Hýbe se tvoje postava doprava? Vypadá tvoje postava jako že chodí?

	![screenshot](dodge-walking.png)

+ Na pohyb postavy doleva, budeme potřebovat další `když` {.blockcontrol} blok uvnitř tvého cyklu `opakuj dokola` {.blockcontrol}, který bude hýbat postavou doleva. Nezapomeň vyzkoušet svůj nový kód, aby jsi ujistil že funguje! Pokud se tvoje postava otočí vzhůru nohama ve chvíli, když chodí doleva, přidej blok `nastav způsob otáčení` {.blockcontrol} nad blokem `opakuj dokola` {.blockcontrol}:

```blocks
  po kliknutí na ⚑
  nastav způsob otáčení na [jen vlevo-vpravo v]
  opakuj dokola
    když <klávesa [šipka vpravo v] stisknuta?> tak
      natoč se směrem (90 v)
      posuň se o (3) kroků
      další kostým
    end
  end
```

+ Na šplhání po tyčí, tvoje postava se musí pohnout maličko nahoru když je zmáčknuta šipka nahoru a postava se dokýká správné barvy. Přidej tento kód dovnitř bloku `opakuj dokola` {.blockcontrol}:

```blocks
  když <<klávesa [šipka nahoru v] stisknuta?> a <dotýká se barvy [#FFFF00] ?>> tak
    změň y o (4)
  end
```
+ Vyzkoušej svojí postavu - můžeš vyšplhat po žlutých tyčích a dostat se na konec úrovně?

	![screenshot](dodge-test-character.png)

## Ulož svůj projekt { .save }

## Výzva: Dokončení úrovně {.challenge}
Dokážeš přidat kód ke tvé postavy, aby nečo řekla `když` {.blockcontrol} se dostane ke hnědým dveřím?

![screenshot](dodge-win.png)

## Ulož svůj projekt { .save }

# Krok 2: Přitažlivost a skákání { .activity }

Uděláme pohyb postavy vice reální, když přidáme přitažlivost a umožníme postavě skákat.

## Postup { .check }

+ Možná sis všiml že tvoje postava může chodit i mimo podlahy a zůstat ve vzduchu. Zkus vyjít stranou z podlahy a pozoruj co se stane.

	![screenshot](dodge-no-gravity.png)

+ Aby jsme toto napravili, přidáme do hry přitažlivost. Vytvoř novou proměnnou nazvanou `gravitace` {.blockdata}. Můžeš tuto proměnnou skrýt ze scény, pokud budeš chtít.

	![screenshot](dodge-gravity.png)

+ Přidej tento nový blok kódu, který nastaví gravitace na zápornou hodnotu, a pak použije tuto na změnu y-pozice tvé postavy.

```blocks
  po kliknutí na ⚑
  nastav [gravitace v] na [-4]
  opakuj dokola
    změň y o (gravitace)
  end
```

+ Klikni na vlajku, a pak přetáhni svou postavu na vršek tvé scény. Co se stane? Funguje přitažlivost jak jsi očekával?

	![screenshot](dodge-gravity-drag.png)

+ Přitažlivost by neměla hýbat postavou skrz podlahu nebo tyč! Přidej blok `když` {.blockcontrol} do tvého kódu, aby přitažlivost fungovala jen pokud bude postava ve vzduchu. Kód pro přitažlivost by měl vypadat asi takto:

```blocks
  po kliknutí na ⚑
  nastav [gravitace v] na [-4]
  opakuj dokola
    když <není <<dotýká se barvy [#0000FF] ?> nebo <dotýká se barvy [#FFFF00] ?>>> tak
      změň y o (gravitace)
    end
  end
```

+ Vyzkoušej přitažlivost znovu. Zastaví se pád postavy když stoji na podlaze nebo se drží tyče? Můžeš spadnout z kraje podlahy a dopadnout na podlahu níže?

	![screenshot](dodge-gravity-test.png)

+ Pojďme taky zařídit aby postava skočila když hráč zmáčkne mezerník. Velmi jednoduchý způsob jak toto zařídit je pohnout postavou nahoru nekolikrát, pomocí tohoto kódu:

```blocks
  po stisku klávesy [mezerník v]
  opakuj (10) krát
    změň y o (4)
  end
```

  Protože přitažlivost stále tlačí postavu dolů o 4 pixelů, musíš zvolit číslo větší než 4 ve tvém bloku `změň y o (4)` {.blockmotion}. Změň toto čislo tak aby jsi byl spokojený s tím, jak tvoje postava skáče.

+ Až budeš tento kód zkoušet, všimni si že pohyb postavy není moc plynulý. Aby bylo skákání plynulejší, budeš muset hýbat postavou o čím dále mensí počet pixelů, dokud se její pohyb nahoru zastaví.

+ Na to vytvoříme další proměnnou `výška skoku` {.blockdata}. Můžeš tuto proměnnou opět skrýt, pokud budeš chtít.

+ Smaž kód skákání který jsme přidali k postavě, a nahraď tímto kódem:

```blocks
  po stisku klávesy [mezerník v]
  nastav [výška skoku v] na [8]
  opakuj dokud nenastane <(výška skoku) = [0]>
    změň y o (výška skoku)
    změň [výška skoku v] o (-0.5)
  end
```

  Tento kód hýbe postavou o 8 pixelů, poté o 7,5 pixelů, poté 7 pixelů a tak dále, dokud postava neskončí skok. Toto pomůže aby byly skoky o hodně plynulejší.

+ Změň počáteční hodnotu tvé proměnné `výška skoku` {.blockdata} a vyzkoušej program tak, aby jsi byl spokojen s výškou skoku tvé postavy.

## Ulož svůj projekt { .save }

## Výzva: vylepšené skákání {.challenge}
Tvoje postava může skočit kdykoliv je zmáčknutý mezerník, i když je postavička ve vzduchu. Můžeš toto vyzkoušet podržením mezerníku. Můžes toto opravit tak aby postava mohla skočit pouze `jestli` {.blockcontrol} se dotýká modré podlahy?

## Ulož svůj projekt { .save }

# Krok 3: Uhýbání míčů { .activity .new-page}

Teď když už tvoje postava chodí, přidáme nějaké míče, kterým se bude muset tvoje postava vyhnout.

## Postup { .check }

+ Vytvoř nový sprite míče. Můžeš použít jakýkoliv typ míče který se ti bude líbit

	![screenshot](dodge-balls.png)

+ Změň velikost tvého míče, tak aby tvoje postava mohla skočit přes něj. Zkus míč přeskočit aby jsi vyzkoušel že to jde.

	![screenshot](dodge-ball-resize.png)

+ Přidej tento kód ke tvému míči:

	![screenshot](dodge-ball-motion.png)

  tento kód vytvoří nový klon míče každé 3 vteřiny. Každý nový klon se pohybuje po vrchní podlaží.

+ Klikni na vlajku aby jsi toto vyzkoušel.

	![screenshot](dodge-ball-test.png)

+Přidej další kód do spritu tvého míče, aby se mohl pohybovat přes všechny 3 podlaží.

	![screenshot](dodge-ball-more-motion.png)

+ Nakonec budeš potřebovat taky kód pro případ že byla tvoje postava zasažena míčem! Přidej tento kód ke spritu tvého míče:

```blocks
  když startuji jako klon
  opakuj dokola
    když <dotýká se [Pico walking v] ?> tak
      rozešli všem [zásah v]
    end
  end
```

+ Taky budeš potřebovat přidat kód ke tvé postavě, aby se vrátila na začátek, když je zasažena:

```blocks
  po obdržení zprávy [zásah v]
  natoč se směrem (90 v)
  skoč na pozici x: (-210) y: (-120)
```

+ Vyzkoušej svojí postavu a ujisti se ze se vrátí na začátek když je zasažena míčem.

## Ulož svůj projekt { .save }

## Výzva: náhodné míče {.challenge}
Všechny míče kterým se musí tvoje postava vyhnout vypadají stejně a objevují se pravidelně kazdých 3 sekund. Mohl bys toto vylepsit, tak aby:

+ Nevypadaly všechny stejně?
+ Objevovaly se po uplynutí různé doby?
+ Měli náhodné velikosti?

![screenshot](dodge-ball-random.png)

## Ulož svůj projekt { .save }

# Krok 4: Lasery! { .activity .new-page}

Uděláme hru trochu tězší, když přidáme lasery!

## Postup { .check }

+ Pridej nový sprite do hry, který se bude jmenovat 'Laser'. Měl by mít 2 kosttýmy, který nazveme 'zapnuto' a 'vypnuto'.

	![screenshot](dodge-lasers-costume.png)

+ Dej tvůj nový laser kdekoliv se ti bude líbit, mezi 2 podlahy.

	![screenshot](dodge-lasers-position.png)

+ Přidej kód ke tvému laseru, aby měnil mezi oba kostýmy.

```blocks
  po kliknutí na ⚑
  opakuj dokola
    změň kostým na [zapnuto v]
    čekej (2) sekund
    změň kostým na [vypnuto v]
    čekej (2) sekund
  end
```

  Pokud budeš chtít, můžeš `čekej` {.blockcontrol} a `náhodné číslo` {.blockoperators} čas mezi výměnou kostýmu.

+ A na konec přidej kód ke tvému laseru, aby se odeslala zpráva 'zasaženo' byla poslána když se laser dotkne postavy. Tento kód bude tentýž kód jaký jsi přidal ke spritu míče.

  Nemusíš přidat další kód ke tvé postavě - ona již ví co má dělat pokud je zasažena!

+ Vyzkoušej svou hru aby jsi byl jist že se můžeš dostat přes laser. Změň počet u `čekej` ve tvém kódu pokud je dosatt se přes lasery moc jednoduchý nebo moc obtižný.

## Výzva: více překážek {.challenge}
Pokud si stále myslíš že je hra příliš jednoduchá, můžeš přidat další překážky do tvé úrovně. Můžeš přidat cokoliv budeš chtít, ale tady je několik nápadů:

+ Létající smrtící motýl;
+ Podlahy které se objevují a mizí;
+ Padající tenisové míčky kterým musíš uhnout.

![screenshot](dodge-obstacles.png)

Můžes dokonce vytvořit více než jedno pozadí, a přesunout se do další úrovně když postava dojde ke hnědým dveřím:

```blocks
  když <dotýká se barvy [#714300] ?> tak
    změň pozadí na [next backdrop v]
    skoč na pozici x: (-210) y: (-120)
    čekej (1) sekund
  end
```

## Ulož svůj projekt { .save }

## Výzva: vylepšená přitažlivost {.challenge}

Tvoje hra má ještě jednu malou chybičku: přitažlivost nemá vliv na postavu pokud _jakákoliv_ její část se dotýká modré podlahy - dokonce i hlava! Můžeš toto vyzkoušet když vyšplháš skoro až nahoru po tyčí a pak pohybem doleva.

![screenshot](dodge-gravity-bug.png)

Uměl by jsi tuto chybu opravit? Aby to bylo možné, musíš dát tvé postavě jinak barevné kalhoty (ve _všech_ kostýmech)...

![screenshot](dodge-trousers.png)

...a poté nahradit kód:

```blocks
  <dotýká se barvy [#0000FF] ?>
```

kódem:

```blocks
  <barva [#00FF00] se dotýká barvy [#0000FF] ?>
```

Nezapomeň otestovat svojí opravu aby jsi byl jist že jsi opravila chybu!

## Ulož svůj projekt { .save }

## Výzva: více životů {.challenge}
Uměl by jsi dát hráči 3 `životy` {.blockdata}, namísto pouhého odesíání na začátek pokaždý? Takhle by mohla hra fungovat:

+ Na začátku má hráč 3 životy;
+ Po každém zásahu se odečte jeden život, a poté se vrátí postava na začátek;
+ Pokud již nejsou k dispozici žádné další životy, hra končí.

## Ulož svůj projekt { .save }
