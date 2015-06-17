---
title: Flaxande Fågel
level: Level 2
language: sv-SE
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
---

# Introduktion { .intro}
__I det här projektet ska vi göra vår egen version av det väldigt populära spelet Flappy Bird. Projektet kräver Scratch 2.0.__
Tryck på mellanslag för att flaxa och försök att styra genom hålen i rören!

![screenshot](flappy_screenshot.png)

#**Steg 1:** Få fågeln Flappy att falla {.activity}

## Checklista { .check}

+ Om Scratch inte är på svenska, så välj svenska i menyalternativet som ser ut som en jordglob.
+ Skapa ett nytt Scratch-projekt. Ta bort katten genom att högerklicka på den och välja Radera.
+ Ersätt bakgrunden med ett utomhus-landskap. **desert** är ett bra val.
+ Lägg till fågeln Flappy. Du behöver en sprite med kostymer för vingar upp och vingar ner. **parrot** är ett bra val.
+ Byt namn på spriten till __Flappy__
+ Ge Flappy följande script:

    ```blocks
    när FLAGGA klickas på
        gå till x: (-50) y: (0)
        för alltid
            ändra y med (-3)
    ```

## Testa ditt projekt { .flag}

__Klicka på den gröna flaggan__, börjar Flappy i mitten på skärmen och faller ner?

## Spara ditt projekt { .save}

#**Steg 2:** Få Flappy att flyga {.activity}

*Sen ska vi få Flappy att flyga uppåt när du trycker på mellanslag.*

## Checklista { .check}

+ Klicka på fliken __Klädslar__ och döp kostymerna **vingar upp** och **vingar ner**.
+ Byt nu tillbaks till fliken __Script__ och lägg till detta script:

    ```blocks
    när [mellanslag v] trycks ned
        byt klädsel till [vingar ner v]
        repetera (10)
            ändra y med (6)
        slut
        byt klädsel till [vingar upp v]
        repetera (10)
            ändra y med (6)
        slut
    ```

## Testa ditt projekt { .flag}

__Klicka på den gröna flaggan__, kan du kontrollera Flappy med mellanslagstangenten? Märker du att Flappy inte alltid flyger uppåt när du trycker mellanslag? Vi ska fixa det nu...

## Spara ditt projekt { .save}

#**Steg 3:** Fixa kontrollerna {.activity}

*Vi vill att Flappy ska reagera varje gång vi trycker mellanslag. Men när vi trycker på mellanslag så börjar Flappy två loopar med förflyttning. Om vi trycker på mellanslag igen innan dessa loopar är färdiga så ignoreras det andra trycket. För att lösa detta så ska vi använda en variabel för att räkna hur många vingslag vi behöver göra.*

## Checklista { .check}

+ Flytta undan blocken under `när mellanslag trycks ned` {.blockbrown} (vi kommer att använda dom snart igen.)
+ Skapa en ny variable  `Enbart för denna sprite` {.blockgrey} och kalla den `Flax` {.blockorange}.
+ Lägg till följande script genom att dra in blocken som du tidigare drog åt sidan:

    ```blocks
    when FLAG clicked
        sätt [Flax v] till [0]
        byt klädsel till [vingar upp v]
        för alltid
            repetera tills <(Flax) = [0]>
                ändra [Flax v] med (-1)
                byt klädsel till [vingar ner v]
                repetera (10)
                    ändra y med (6)
                slut
                ändra klädsel till [vingar upp v]
                repetera (10)
                    ändra y med (6)
                slut

    ```

+ Och slutligen, lägg följande till din händelse `när mellanslag trycks ned` {.blockbrown}:

    ```blocks
    när [mellanslag v] trycks ned
        ändra [Flax v] med (1)
    ```

## Testa ditt projekt { .flag}

__Klicka på den gröna flaggan__, flaxar Flappy en gång för varje gång som du trycker på mellanslag?

## Spara ditt projekt { .save}

#**Steg 4:** Lägg till rören {.activity}

*Nu ska vi lägga till några hinder som Flappy kan flyga igenom.*

## Checklista { .check}

+ Klicka på `Rita ny sprite`
+ Döp klädseln till **rör**.
+ Om klädseln är i `Bitmapsläge` {.blockgrey} så klicka på knappen `Omvandla till vektor` {.blockgrey}.
+ Klicka på knappen `Zoom -` {.blockgrey} så att du kan se hela rit-ytan.
+ Klicka på `Rektangel` {.blockgrey}, välj en färg, och klicka på knappen `Ifylld rektangel` {.blockgrey}.
+ Klicka och drag två lådor, en från uppe i mitten och en från nere i mitten, som på bilden nedan:

![screenshot](pipe_design.png)

+ Du kan tona dina rör genom att klicka på knappen `Färglägg en form` {.blockgrey} och klicka på knappen `Horisontell gradient` {.blockgrey}. Välj två nyanser av samma färg, en för förgrundsfärgen och en för bakgrundsfärgen. När du klicka för att fylla i formerna, så kommer färgen att skifta mellan de valda färgerna.
+ Döp din sprite **Rör**

## Spara ditt projekt { .save}

#**Steg 5:** Få rören att flytta på sig {.activity}

*Nu ska vi få rören att röra sig och placera sig slumpmässigt så att de skapar en hinderbana för Flappy.*

## Checklista { .check}

+ Klicka på din **Rör** sprite och välj fliken `Script`.
+ Lägg till följande script:

    ```blocks
    när FLAGGA klickas på
        göm
        sät storlek till (200)%
        för alltid
            skapa klon av [mig själv v]
            vänta (2) sekunder

    när jag startar som klon 
        gå till x: (240) y: (slumptal (-80) till (80))
        visa
        repetera (120)
            ändra x med (-4)
        slut
        radera klonen
    ```

## Testa ditt projekt { .flag}

__Klicka på den gröna flaggan__, kommer det rör med hål i flygande på olika höjd? On du tycker att det är svårt att åka med Flappy genom hålen i rören så kan du göra hålen större genom att att redigera klädseln till spriten **rör**.

## Spara ditt projekt { .save}

#**Steg 6:** Upptäcka kollision med rören {.activity}

*För att göra spelet till en utmaning så behöver spelaren styra Flappy genom hålen i rören utan att röra rören eller kanterna på skärmen. Nu ska vi lägga till block som känner av om Flappy nuddar någonting.*

## Checklista { .check}

+ Nu ska vi lägga till ett ljud när Flappy krockar. Klicka på spriten **Flappy** och sen på fliken `Ljud` {.blockgrey}.
+ Klicka på knappen `Välj ljud från biblioteket` {.blockgrey}.
+ Välj ett krock-ljud för **Flappy**. Ljudet **screech** är bra.
+ Klicka på fliken `Script` {.blockgrey}.
+ Lägg till följande script:

    ```blocks
    när FLAGGA klickas på
        vänta tills ((rör [kant v]?) eller (rör [Rör v]?))
        spela ljudet [screech v]
        säg [Spelet är över!]
        skicka [SpeletÖver v]
        stoppa [andra scritp i sprite v]
    ```

+ Klicka på spriten **Rör** och lägg till följande script:

    ```blocks
    när jag tar emot [SpeletÖver v]
        stoppa [andra script i sprite v]
    ```

## Testa ditt projekt { .flag}

__Klicka på den gröna flaggan__, slutar spelet när Flappy nuddar ett rör eller kanten på skärmen?

## Spara ditt projekt { .save}

#**Steg 7:** Lägg till poängräkning {.activity}

*Nu ska vi lägga till så att spelaren får poäng varje gång som Flappy kommer igenom ett rör.* 

## Checklista { .check}

+ Vi lägger till ett ljud som ska spelas när Flappy får ett poäng. Klicka på spriten **Rör** och lägg till ett poäng-ljud. **bird** är ett bra val.
+ Klicka nu på fliken `Script` {.blockgrey}.
+ Skapa en ny variabel `För alla sprites` och döp den till `poäng` {.blockorange}.
+ Lägg till ett block som sätter poängen till 0 när flaggan klickas på.
+ Lägg till följande block:

    ```blocks
    när jag startar som klon
    	vänta tills <(x-läge) < ([x-läge v] av [Flappy v])>
    	ändra [poäng v] med (1)
    	spela ljud [bird v]
    ```

## Testa ditt projekt { .flag}


__Klicka på den gröna flaggan__, får spelaren poäng när Flappy flyger genom hålen i rören?

## Spara ditt projekt { .save}

##Saker att försöka { .try}
1. __På hur många sätt kan du göra spelet lättare eller svårare?__
2.__Grattis, du har slutfört det grundläggande spelet. Det finns dock fler saker som du kan göra med spelet. Testa gärna dom följande utmaningarna!__

##Utmaning 1: lägg till en high score { .challenge}

+ Skapa en ny variabel och klicka i boxen `Moln variabel (lagrad på servern)` {.blockgrey}. Kalla variabeln `hi-score` {.blockorange}. Notera att du måste vara en Scratcher för att få använda molndata.
+ När spelet är över så kontrollera om du behöver sätta en ny highscore:

    ```blocks
    när jag tar emot [SpeletÖver v]
        om <(poäng) > (hi-score)> då
            sätt [hi-score v] till (score)
        slut
        stoppa [andra script i sprite v]
    ```

##Testa ditt projekt { .flag}
__Klicka på den gröna flaggan__, uppdateras highscore när du får högre poäng?

##Spara ditt projekt { .save}

##Utmaning 2: lägg till gravitation { .challenge}

När någonting faller under gravitation så faller det oftast inte med en konstant hastighet. I den här utmaningen ska vi göra så att Flappy faller som utav gravitation.

+ Lägg till en ny variabel till **Flappy** (`Enbart för denna sprite` {.blockgrey} ) och kalla den `stigning` {.blockorange}.
+ Ändra Flappys script för fallandet:

    ```blocks
    när FLAGGA klickas på
        sätt [stigning v] till [0]
        gå till x: (-50) y: (0)
        för alltid
            ändra y med (stigning)
            ändra [stigning v] med (-0.4)
    ```

+ Ändra Flappys script för flaxande:

    ```blocks
    när FLAGGA klickas på
        sätt [flax v] till [0]
        byt klädsel till [vingar upp v]
        för alltid
            repetera tills <(flax) = [0]>
                ändra [flax v] med (-1)
                byt klädsel till [vingar ner v]
                ändra [stigning v] med (8)
                wait (0.2) secs
                switch costume to [wings up v]
                wait (0.2) secs
    ```

##Testa ditt projekt { .flag}
__Klicka på den gröna flaggan__, accelererar Flappy när han faller och flaxar?

##Spara ditt projekt { .save}

##Utmaning 3: falla ut från skärmen { .challenge}

Få Flappy att trilla ner till botten på skärmen när spelaren förlorar, innan spelet avslutas.

+ Byt upp blocket `skicka SpeletÖver` {.blockbrown} till ett block med `skicka Fall` {.blockbrown}
+ Lägg sen till följande script:

    ```blocks
    när jag tar emot [Fall v]
        repetera (10)
            vänd motsols (5) grader

    när jag tar emot [Fall v]
        repetera tills <(y position) < [-180]>
            ändra y med [stigning]
            ändra [stigning v] med (-0.4)
        slut
        göm
        skicka [SpeletÖver v]
    ```

+ Glöm inte att lägga till blocket `visa`  {.blockpurple} och att återställa Flappys rotation när spelet startar om.
+ Se också till att du inte stoppar andra script förrän du har skickat SpeletÖver

##Testa ditt projekt { .flag}
__Klicka på den gröna flaggan__, faller Fally ner och ut från skärmen efter att han träffar ett rör? Kommer Flappy tillbaks med korrekt rotation efter att ha startat om spelet?.

##Spara ditt projekt { .save}

__Bra jobbat, du är färdig! Nu kan du njuta av spelet!__
Glöm inte att du kan dela med dig av ditt spel alla dina vänner och din familj genom att klicka på __Dela__ uppe till höger i meny-panelen!


