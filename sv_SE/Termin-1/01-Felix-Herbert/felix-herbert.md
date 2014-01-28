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

#STEG 1: Felix följer muspekaren

## {.check}

1. Skapa ett nytt projekt.
2. Klicka på Scen bredvid spriten och byt till fliken Bakgrunder, importa sen bakgrunden indoors/hall. Radera den ursprungliga tomma bakgrunden.
3. Byt namn på spriten till Felix.
4. Se till att Felix bara pekar åt vänster-höger genom att klicka på den här knappen:
5. Skapa följande script:

    ```scratch

        När FLAGGA klickas på

        för alltid

            peka mot musmarkör

            gå 10 steg

            nästa klädsel

            spela trumman 62 i 0.3 taktslag

        (slut på för alltid)
    ```
		
## Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__
Följer Felix muspekaren? Ser det ut som att han går när han rör sig? Rör han sig i rätt hastighet?

## Spara ditt projekt

# STEG 2: Felix jagar Herbert {.activity}

__Nu vill vi att Felix ska jaga musen Herbert istället för muspekaren.__

## {.check}

1. Skapa en ny sprite genom att klicka på Välj ny sprite från fil-knappen och välj animals/mouse1.
2. Byt namn på spriten till Herbert.
3. Byt klädsel och gör den mindre än Herbert.
Pröva med sex klick på Förminska-knappen:
4. Se till så att Herbert bara pekar åt vänster-höger.
5. Ge Herbert det här scriptet:

    ```scratch
        
        När FLAGGA klickas på
        för alltid
            gå till musmarkör
            peka mot Felix
        (slut på för alltid)
    ```

## Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Rör sig Herbert med musmarkören? Jagar Felix Herbert?

## Spara ditt projekt. {.flag}

#STEG 3: Felix säger till när han har fångat Herbert

__Vi vill att Felix ska veta när han har fångat Herbert, och säga det till oss.__

## {.activity}

1. Ändra Felix script så det ser ut såhär:

    ```scratch
        
        när FLAGGA klickas på
        för alltid
            peka mot musmarkör
            gå 10 steg
            nästa klädsel
            spela trumman 62 i 0.3 taktslag
            om rör Herbert
                säg Fångad! i 1 sekund
            (slut på om)
        (slut på för alltid)
    ```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Säger Felix till när han har fångat Herbert?

## Spara ditt projekt {.save}

#STEG 4: Herbert blir ett spöke när han fångas

__Istället för att Felix säger någonting så vill vi att Herbert ska förvandlas till ett spöke när han fångas.__

## {.activity}

1. Ändra i Felix script så att det skickar ut följande meddelande när han fångar Herbert.

    ```scratch
        
        när FLAGGA klickas på
        för alltid
            peka mot musmarkör
            gå 10 steg
            nästa klädsel
            spela trumman 62 i 0.3 taktslag
            om rör Herbert
                sänd fångad
                spela trumman 58 i 0.2 taktslag
                vänta 1 sekunder
            (slut på om)
        (slut på för alltid)
    ```

2. Importera en ny klädsel till Herbert från fantasy/ghost2-a.
3. Redigera klädseln och gör den mindre.
Sex klick på Förminska-knappen borde räcka.
4. Byt namn på Herberts klädslar på musklädseln heter "levande" och spökkostymen heter "död".
5. Skapa ett nytt script till Herbert för att förvandla honom till spöke:

    ```scratch
        
        när jag tar emot fångad
        växla till klädsel död
        vänta 0.5 sekunder
        växla till klädsel levande
    ```
	
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Blir Herbert ett spöke när han fångas?
Spelar Felix de rätta ljuden när han ska?
Står Felix still tillräckligt länge för att Herbert ska kunna ge sig iväg?

##Spara ditt projekt {.save}

#STEG 5: Räkna poäng

__Nu lägger vi till ett poängsystem så vi vet hur bra vi är på att hålla Herbert vid liv.
Vi börjar med att låta poängen vara noll och höjer den med ett varje sekund. Om Felix fångar Herbert minskar vi poängen med hundra.__

1. Skapa en variabel som heter poäng för alla sprites. Klicka på Variabler i toppmenyn, skapa en variabel och kalla den poäng.
2. På scenen, skapa de här två scripten

    ```scratch
        
        när FLAGGA klickas på
        sätt poäng till 0
        för alltid
            ändra score med 1
            vänta 1 sekunder
        (slut på för alltid)
        
        när jag tar emot fångad
        ändra score med -100
    ```
	
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Ökas pängen med ett varje sekund?
Minskas poängen med 100 när Herbert fångas?
Vad händer när Herbert fångas innan poängen har blivit hundra? Nollställs poängen när du startar om spelet?

##Spara ditt projekt {.save}

__Bra jobbat, nu är du klar och kan spela spelet!__
Glöm inte att du kan dela spelet med dina kompisar genom att klicka på __Dela ut__ i menyn.
