---
title: Felix & Herbert
level: Nivå 1
language: sv-SE
stylesheet: scratch
embeds: "*.png"
note: "till_instruktorerna.md"
...

# Introduktion {.intro}

Vi ska skapa ett spel där __katten Felix__ ska försöka ta __musen Herbert__. Du kontrollerar Herbert med muspekaren och försöker undvika att bli fångad av Felix. Ju längre du håller dig ifrån honom desto fler poäng får du, men se till att inte åka fast för då går poängen ner igen!

# STEG 1: Felix följer muspekaren {.activity}

##Checklista {.check}

+ Skapa ett nytt projekt.
+ Klicka på Scen bredvid sprajten och byt till fliken Bakgrunder, importera sedan bakgrunden Inomhus/hall. Radera den ursprungliga tomma bakgrunden.
+ Byt namn på sprajten till Felix.
+ Se till att Felix bara pekar åt vänster-höger genom att klicka på den här knappen:
+ Skapa följande skript:

```blocks
när @ klickas på
för alltid
  peka mot [muspekare v]
  gå (10) steg
  nästa klädsel
  spela trumman (13 v) i (0.25) taktslag
```
    
## Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__
Följer Felix muspekaren? Ser det ut som att han går när han rör sig? Rör han sig i rätt hastighet?

## Spara ditt projekt {.save}

# STEG 2: Felix jagar Herbert {.activity}

__Nu vill vi att Felix ska jaga musen Herbert istället för muspekaren.__

##Checklista {.check}

+ Skapa en ny sprajt genom att klicka på Välj ny sprajt från fil-knappen och välj Djur/mouse1.
+ Byt namn på sprajten till Herbert.
+ Byt klädsel och gör den mindre än Herbert.
Pröva med sex klick på Förminska-knappen:
+ Se till så att Herbert bara pekar åt vänster-höger.
+ Ge Herbert det här skriptet:

```blocks
när @ klickas på
för alltid
  gå till [muspekare v]
  peka mot [Felix v]
```

## Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Rör sig Herbert med musmarkören? Jagar Felix Herbert?

## Spara ditt projekt. {.save}

# STEG 3: Felix säger till när han har fångat Herbert {.activity}

__Vi vill att Felix ska veta när han har fångat Herbert, och säga det till oss.__


+ Ändra Felix skript så det ser ut såhär:

```blocks
när @ klickas på
för alltid
  peka mot [muspekare v]
  gå (10) steg
  nästa klädsel
  spela trumman (13 v) i (0.25) taktslag
  om <rör [Herbert v]?> då
    säg [Fångad!] i (1) sekunder
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Säger Felix till när han har fångat Herbert?

## Spara ditt projekt {.save}

#STEG 4: Herbert blir ett spöke när han fångas {.activity}

__Istället för att Felix säger någonting så vill vi att Herbert ska förvandlas till ett spöke när han fångas.__

##Checklista {.check}

+ Ändra i Felix skript så att det skickar ut följande meddelande när han fångar Herbert.

```blocks
när @ klickas på
för alltid
  peka mot [muspekare v]
  gå (10) steg
  nästa klädsel
  spela trumman (13 v) i (0.25) taktslag
  om <rör [Herbert v]?> då
    skicka [fångad v]
  säg [Fångad!] i (1) sekunder
```

+ Importera en ny klädsel till Herbert från Fantasy/ghost2-a.
+ Redigera klädseln och gör den mindre.
Sex klick på Förminska-knappen borde räcka.
+ Byt namn på Herberts klädslar på musklädseln heter "levande" och spökkostymen heter "död".
+ Skapa ett nytt skript till Herbert för att förvandla honom till spöke:

```blocks
när jag tar emot [fångad v]
byt klädsel till [död v]
vänta (0.5) sekunder
byt klädsel till [levande v]
```
  
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Blir Herbert ett spöke när han fångas?
Spelar Felix de rätta ljuden när han ska?
Står Felix still tillräckligt länge för att Herbert ska kunna ge sig iväg?

##Spara ditt projekt {.save}

#STEG 5: Räkna poäng {.activity}

__Nu lägger vi till ett poängsystem så vi vet hur bra vi är på att hålla Herbert vid liv.
Vi börjar med att låta poängen vara noll och höjer den med ett varje sekund. Om Felix fångar Herbert minskar vi poängen med tio.__

##Checklista {.check}

+ Skapa en variabel som heter poäng för alla sprajter. Klicka på Variabler i toppmenyn, skapa en variabel och kalla den poäng.
+ På scenen, skapa de här två skripten

```blocks
när @ klickas på
sätt [poäng v] till [0]
för alltid
  ändra [poäng v] med (1)
  vänta (1) sekunder
end


när jag tar emot [fångad v]
ändra [poäng v] med (-10)
```
  
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Ökas pängen med ett varje sekund?
Minskas poängen med 10 när Herbert fångas?
Vad händer när Herbert fångas innan poängen har blivit tio? Nollställs poängen när du startar om spelet?

##Spara ditt projekt {.save}

__Bra jobbat, nu är du klar och kan spela spelet!__
Glöm inte att du kan dela spelet med dina kompisar genom att klicka på __Dela ut__ i menyn.