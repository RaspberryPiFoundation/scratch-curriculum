---
title: Felix og Herbert
level: 1.1
language: nb-NO
embeds: ["*.png"]
...

# Felix og Herbert

# Introduksjon { .intro}

Vi skal lage et spill hvor katten __Felix__ skal fange musa __Herbert__. Du styrer Herbert med musepekeren og skal prøve å unngå å bli tatt av Felix. Jo lenger du unngår ham jo flere poeng får du, men blir du tatt, går poengsummen din ned.

![skjermbilde](screengrab.png)

|Sjekkliste| Følg instruksjonene på lista. Huk av etter hvert|
|---|-----|
|**Test**| **Klikk på det grønne flagget for å teste koden**|
|**Lagre**| **Husk å lagre koden når du har lagt til noe nytt**|

# Steg 1: Felix følger musepekeren { .activity}

__Vi ønsker at katten Felix skal følge etter musepekeren.__

## Sjekkliste{ .check}

+ Start et nytt prosjekt.
+ Trykk på ´i´ i hjørnet av ![Sprite1](sprite1.png) og bytt navn på figuren til Felix.
+ Sørg for at Felix kun ser til høyre og venstre ved å sette rotasjonsmåte til ![Høyre/Venstre](rotasjonsmate-hv.png).
+ Klikk på scenen ved siden av Felix i vinduet for figurer. Velg fanen 'Bakgrunner' og trykk på ![Velg en ferdig bakgrunn](velg-bakgrunn.png) for å importere en ferdig bakgrunn. Velg bakgrunnen 'Utendørs/brick wall2'.
+ Velg ![skript](fane-skript.png)-fanen og lag dette skriptet:

```blocks
Når grønt flagg klikkes
for alltid
  pek mot [musepeker v]
  gå (10) steg
  neste drakt
  trommeslag (3 v) som varer (0.25) takter
```
      

## Test prosjektet { .flag}

__Klikk på det grønne flagget.__

+ Følger Felix musepekeren?
+ Ser det ut som han går når han beveger seg?
+ Beveger han seg med riktig hastighet?

## Lagre prosjektet { .save}

# Steg 2: Felix jager Herbert { .activity}

__Nå ønsker vi at Felix skal jage musa Herbert i stedet for musepekeren.__

## Sjekkliste { .check}

+ Lag en ny figur ved å trykke på ![Velg figur fra biblioteket](figur-fra-bibliotek.png) og velg figuren 'Dyr/Mouse1'.
+ Bytt navn på figuren til Herbert og sørg for at også Herbert kun kan se til høyre og venstre ![Høyre/Venstre](rotasjonsmate-hv.png).
+ Gjør Herbert mindre enn Felix ved å trykke på ![krymp](krymp.png) (øverst mot midten av vinduet). Prøv seks klikk.
+ Gi Herbert dette skriptet:

```blocks
      Når grønt flagg klikkes
      for alltid
        gå til [musepeker v]
        pek mot [Felix v]
```

## Test prosjektet { .flag}

__Klikk på det grønne flagget.__

+ Flytter Herbert seg med musepekeren?
+ Jager Felix Herbert?

## Lagre prosjektet { .save}

# Steg 3: Felix sier når han har fanget Herbert { .activity}

__Vi vil at Felix skal vite når han har fanget Herbert og fortelle det til oss.__

## Sjekkliste { .check}

+ Endre skriptet til Felix til dette:

```blocks
      Når grønt flagg klikkes
      for alltid
        pek mot [musepeker v]
        gå (10) steg
        neste drakt
        trommeslag (3 v) som varer (0.25) takter
        hvis (berører [Herbert v]?)
          si [Tok deg!] i (1) sekunder
```

## Test prosjektet { .flag}

__Klikk på det grønne flagget.__

+ Sier Felix fra når han har fanget Herbert?

## Lagre prosjektet { .save}

# Steg 4: Herbert blir et spøkelse når han fanges { .activity}

__I stedet for at Felix sier noe, vil vi at Herbert blir forvandlet til et spøkelse når han fanges.__

## Sjekkliste { .check}

+ Endre skriptet til Felix slik at det sender en melding og lager en lyd når han fanger Herbert:

```blocks
      Når grønt flagg klikkes
      for alltid
        pek mot [musepeker v]
        gå (10) steg
        neste drakt
        trommeslag (3 v) som varer (0.25) takter
        hvis (berører [Herbert v]?)
          send melding [Fanget!]
          trommeslag (1 v) som varer (0.25) takter
          si [Tok deg!] i (1) sekunder
          vent (1) sekunder
```
  
+ Velg Herbert og gå til ![drakter](fane-drakter.png)-fanen.
+ Hent en ny drakt ved å trykke på ![Velg drakt fra biblioteket](figur-fra-bibliotek.png) og velg 'Fantasi/ghost2-a'
+ Gjør drakten mindre ved å velge ![Krymp](krymp.png) og trykke seks ganger på spøkelsesdrakten.
+ Endre navnene på Herberts drakter slik at musedrakten heter 'levende' og spøkelsesdrakten heter 'død'.
+ Lag et nytt skript for Herbert for å gjøre ham om til et spøkelse. Ikke slett det gamle skriptet!:

```blocks
      når jeg mottar [Fanget! v]
      bytt drakt til [død v]
      vent (0.5) sekunder
      bytt drakt til [levende v]
```
  

## Test prosjektet { .flag}

__Klikk på det grønne flagget.__

+ Forvandles Herbert til et spøkelse når han fanges?
+ Spiller Felix de riktige lydene til riktig tid?
+ Står Felix stille lenge nok til at Herbert kommer seg unna?

## Lagre prosjektet { .save}

# Steg 5: Telle poeng { .activity}

__La oss legge til en poengsum slik at vi kan se hvor flink man er til å holde Herbert i live. Vi begynner med poengsummen null og øker den med en for hvert sekund. Hvis Felix fanger Herbert, minker vi poengsummen med hundre.__

## Sjekkliste { .check}

+ På ![skript](fane-skript.png)-fanen under kategorien ![Data](kategori-data.png), lag en ny variabel. La den gjelde for alle figurer og kall den 'Poeng'.
![poengsum](ny-variabel-poengsum.png)
+ Lag disse to skriptene på scenen:

```blocks
      Når grønt flagg klikkes
      sett [Poeng v] til (0)
      for alltid
        endre [Poeng v] med (1)
        vent (1) sekunder
      når jeg mottar [Fanget! v]
      endre [Poeng v] med (-100)
```

## Test prosjektet { .flag}

__Klikk på det grønne flagget.__

+ Øker poengsummen med en hvert sekund?
+ Går poengsummen ned med hundre når Herbert blir fanget?
+ Hva skjer når Herbert fanges før du har hundre poeng?
+ Går poengsummen tilbake til null når du starter spillet på nytt?

## Lagre prosjektet { .save}

__Du er ferdig. Godt gjort. Nå kan du spille spillet!__

Husk at du kan dele spillet med familie og venner ved å trykke 'Legg ut' på menylinjen.