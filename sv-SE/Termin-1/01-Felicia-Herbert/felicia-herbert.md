---
title: Felicia & Herbert
level: Nivå 1
language: sv-SE
stylesheet: scratch
embeds: "*.png"
note: "till_instruktorerna.md"
...

# Introduktion {.intro}

Vi ska skapa ett spel där __katten Felicia__ ska försöka ta __musen Herbert__. Du kontrollerar Herbert med muspekaren och försöker undvika att bli fångad av Felicia. Ju längre du håller dig ifrån honom desto fler poäng får du, men se till att inte åka fast för då går poängen ner igen!

# STEG 1: Felicia följer muspekaren {.activity}

##Checklista {.check}

+ Skapa ett nytt projekt.
+ Klicka på **Scen** bredvid sprajten och byt till fliken `Bakgrunder` <img alt="" class="inline" src="bakgrunder-flik.png">.
+ Klicka på `Välj bakgrund från biblioteket` <img alt="" class="inline" src="valj_bakgrund.png"> och välj sedan bakgrunden **Inomhus/hall** (eller annan).
+ Radera den ursprungliga tomma bakgrunden.
+ Klicka på sprajten. Klicka sedan på <img alt="" class="inline" src="info.png"> i övre vänstra hörnet. Byt namn på sprajten till **Felicia**.
+ Se till att Felicia bara pekar åt vänster-höger genom att klicka på den här knappen: <img alt="" class="inline" src="flip_arrows.png">
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

+ Följer Felicia muspekaren?
+ Ser det ut som att hon går när hon rör sig?
+ Rör hon sig i rätt hastighet?

## Spara ditt projekt {.save}

# STEG 2: Felicia jagar Herbert {.activity}

__Nu vill vi att Felicia ska jaga musen Herbert istället för muspekaren.__

##Checklista {.check}

+ Skapa en ny sprajt genom att klicka på `Välj ny sprajt från biblioteket` <img alt="" class="inline" src="valj_sprajt_biblioteket.png"> och välj **Djur/mouse1**.
+ Byt namn på sprajten till **Herbert**.
+ Byt klädsel och gör den mindre än Felicia genom att klicka på knappen `Förminska`: <img alt="" class="inline" src="forminska.png"> och sedan direkt på Herbert i händelsefönstret några gånger.
+ Se till så att Herbert bara pekar åt vänster-höger genom att klicka på den här knappen: <img alt="" class="inline" src="flip_arrows.png">
+ Se till att sprajten Herbert är vald och ge honom det här skriptet:

```blocks
när @ klickas på
för alltid
  gå till [muspekare v]
  peka mot [Felicia v]
```

## Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

+ Rör sig Herbert med muspekaren? 
+ Jagar Felicia Herbert?

## Spara ditt projekt. {.save}

# STEG 3: Felicia säger till när hon har fångat Herbert {.activity}

__Vi vill att Felicia ska veta när hon har fångat Herbert, och säga det till oss.__


+ Ändra Felicias skript så det ser ut såhär:

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

+ Säger Felicia till när hon har fångat Herbert?

## Spara ditt projekt {.save}

#STEG 4: Herbert blir ett spöke när han fångas {.activity}

__Istället för att Felicia säger någonting så vill vi att Herbert ska förvandlas till ett spöke när han fångas.__

##Checklista {.check}

+ Ändra i Felicias skript så att det skickar ut följande meddelande när hon fångar Herbert. I blocket ´skicka´ behöver du skriva in ett meddelande, i det här fallet **fångad**.

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

+ Importera en ny klädsel till Herbert genom att markera honom, klicka på fliken `Klädslar` <img alt="" class="inline" src="kladslar-flik.png">, sedan på `Välj klädsel från biblioteket` <img alt="" class="inline" src="valj_sprajt_biblioteket.png"> och välj **Fantasy/ghost2-a**.
+ Gör den nya spökklädseln mindre med knappen `Förminska` som tidigare: <img alt="" class="inline" src="forminska.png">
+ Byt namn på Herberts klädslar så att musklädseln heter **levande** och spökklädseln heter **död** (det gör man i övre delen av ritfönstret).
+ Skapa ett nytt skript till Herbert så att han kan förvandlas till spöke:

```blocks
när jag tar emot [fångad v]
byt klädsel till [död v]
vänta (1) sekunder
byt klädsel till [levande v]
```
  
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

+ Blir Herbert ett spöke när han fångas?
+ Står Felicia still tillräckligt länge för att Herbert ska kunna ge sig iväg?

##Spara ditt projekt {.save}

#STEG 5: Räkna poäng {.activity}

__Nu lägger vi till ett poängsystem så vi vet hur bra vi är på att hålla Herbert vid liv.

Vi börjar med att låta poängen vara noll och höjer den med ett varje sekund. Om Felicia fångar Herbert minskar vi poängen med fem.__

##Checklista {.check}

+ Gå till fliken `Skript` och välj `Data`. Skapa en variabel som heter **poäng** för alla sprajter.
+ Markera Scenen och skapa de här två skripten:

```blocks
när @ klickas på
sätt [poäng v] till [0]
för alltid
  ändra [poäng v] med (1)
  vänta (1) sekunder
end


när jag tar emot [fångad v]
ändra [poäng v] med (-5)
```
  
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

+ Ökas pängen med ett varje sekund?
+ Minskas poängen med fem när Herbert fångas?
+ Vad händer när Herbert fångas innan poängen har blivit fem? 
+ Nollställs poängen när du startar om spelet?

##Spara ditt projekt {.save}

__Bra jobbat, nu är du klar och kan spela spelet!__
Glöm inte att du kan dela spelet med dina kompisar genom att klicka på **Dela** i menyn.