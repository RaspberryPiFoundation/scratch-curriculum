---
title: Whack-a-Witch
level: Nivå 1
language: sv-SE
stylesheet: scratch
embeds: "*.png"
note: "till_instruktorerna.md"
...

# Introduktion {.intro}

Det här projektet är som spelet __Whack-a-Mole__. Du får poäng för att träffa häxorna som kommer upp på skärmen. Målet är att få så många poäng som möjligt på 30 sekunder!

# STEG 1: Skapa en flygande häxa {.activity}

##Checklista {.check}

+ __Skapa ett nytt Scratchprojekt.__
+ __Radera kattspriten__ och ersätt bakgrunden med bakgrunden __nature/woods__.
+ Använd "ny sprajt från fil"-knappen för att lägga till en ny häxsprite till projektet (använd __fantasy/witch1__ ). 

__Nu vill vi göra så att häxan rör sig.__

##Checklista {.check}

+ Gå till fliken `Skript` och välj `Data` {.blockdata}. Skapa en variabel OCH välj "Enbart för denna sprajt" och döp variabeln till "hastighet". OBS! Om du väljer "För alla sprajter" istället för "Enbart för denna sprajt" kommer spelet inte fungera. Då får du radera variablen och göra om.
+ Klicka bort bocken från rutan bredvid blocket `hastighet` {.blockdata} under `Skapa en variabel` så att den inte syns i Scenfönstret. Variablen "hastighet" kommer att styra hur snabbt häxan rör sig.
+ Vi vill att häxan ska börja röra sig när spelet startar, __så gör ett script som ser ut så här__:

```blocks
när @ klickas på
sätt [hastighet v] till [5]
för alltid
    gå (hastighet) steg
end
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan__ och se vad häxan gör. Varför fastnar hon vid kanten av skärmen?

##Checklista {.check}

Vi måste gör så att häxan går tillbaka åt andra hållet när hon rör vid kanten av skärmen. 

+ Ändra ditt befintliga script genom att lägga till blocket `studsa, vid kanten` {.blockmotion}:

```blocks
när @ klickas på
sätt [hastighet v] till [5]
för alltid
    gå (hastighet) steg
    studsa, vid kanten
end
```
+ För att förhindra att häxan vänder sig upp och ner, gå till sprajtinfo <img alt="" class="inline" src="info.gif"> klicka på <img alt="" class="inline" src="vanster-hoger.png">.

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 
Rör sig häxan från sida till sida över skärmen? 

Spara ditt projekt  {.save}

##Saker att pröva {.try}
__Försök att ändra värdet för hastighetsvariabeln så att hon kan flyga snabbare eller långsammare. __

__Hur skulle du göra så att häxan flyger snabbare ju längre tid hon flyger?__
(Det här är en klurig en, så oroa dig inte om du inte förtår hur man gör. Du kommer att få mer ledtrådar under tiden du arbetar med projektet.)

#STEG 2: Gör så att häxan syns och försvinner slumpvis. {.activity}

För att göra spelet roligare vill vi att häxan ska synas och försvinna slumpvis. Vi gör det med ett annat skript som körs samtidigt som det första. Det nya skriptet behöver gömma häxan ett tag, sedan visa henne ett tag, och fortsätta så för alltid (eller tills  spelet avslutas). 

+ __Skapa ett script för häxan:__

```blocks
när @ klickas på
för alltid
    göm
    vänta (slumptal (2) till (3)) sekunder
    visa
    vänta (slumptal (2) till (5)) sekunder
end
```
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 
+ Rör sig häxan från sida till sida över skärmen och försvinner och dyker hon upp slumpvis? 

##Spara ditt projekt {.save}

##Saker att pröva {.try}
__Försök att ändra slumptalen. Vad händer om du väljer väldigt höga siffror eller väldigt låga?__

Kan du få häxan att öka hastigheten ju längre spelet håller på?

#STEG 3: Gör så att häxan försvinner när hon klickas på {.activity}

För att göra detta till ett spel, måste vi ge spelaren något att göra. När spelaren klickar på häxan, vill vi att hon försvinner och spelar ett ljud. 

##Checklista {.check}

+ I fliken <img alt="" class="inline" src="ljud-flik.png"> importerar vi med knappen <img alt="" class="inline" src="int-speaker.png"> ljudet __Elecktronisk/fairydust__.
+ __Lägg till detta skript till häxan__:

```blocks
när denna sprajt klickas på
göm
spela ljudet [fairydust v]
```
###Testa ditt Projekt {.flag}
__Klicka på den gröna flaggan.__ 

Försvinner häxan och spelar ljudet när du klickar på den? 

##Spara ditt projekt {.save}

##Saker att pröva {.try}
__Fråga en instruktör om du kan spela in ditt eget ljud för att spela upp.__

#Steg 4: Lägg till poängsättning och tidtagning {.activity}

Vi har en häxa, men nu vill vi göra ett spel! Vi vill ge poäng varje gång vi klickar på häxan men vi vill även ha en tidsgräns på spelet. Vi kan använda en variabel för poängen och en för tiden. 

##Checklista {.check}

+ Skapa en ny variabel för ALLA sprajtar som heter `Poäng` {.blockdata}.
+ Ändra häxans skript för att öka varibeln med 1 varje gång hon klickas på. 

```blocks
när denna sprajt klickas på
göm
spela ljudet [fairydust v]
ändra [Poäng v] med (-1)
```

+ Byt till __Scenen__ och skapa en __ny variabel__ som kallas `Tid` {.blockdata}. 
+ Lägg till ett nytt skript som minskar "Tid" med 1 varje sekund tills Tid = 0:

```blocks
repetera tills <(Tid) = [0]>
    vänta (1) sekunder
    ändra [Tid v] med (-1)
end
```

+ När spelet startar så ska Tid vara 30 sekunder och Poäng vara 0. Lägg till några block i början:

```blocks
när @ klickas på
sätt [Tid v] till [30]
sätt [Poäng v] till [0]
repetera tills <(Tid) = [0]>
    vänta (1) sekunder
    ändra [Tid v] med (-1)
end
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

#Spara ditt projekt {.save}

##Saker att pröva {.try}
__Hur kan du göra så att häxan ökar hastigheten under spelets gång?__

__Bra gjort, du har gjort klart det grundläggande spelet. Det finns dock fler saker som du kan göra med ditt spel. Prova på den här utmaningen!__

##Utmaning: lägg till fler häxor {.challenge}

Om det är bra med en häxa, så måste det vara ännu bättre mer fler! __Låt oss ha tre häxor som flyger omkring.__
+ Kopiera häxan genom att __högerklicka__ på den i sprajtområdet. 
+ __Anpassa storleken på sprajten__ för varje häxa så att häxorna får olika storlek (Använd förstora/förminska-knapparna i menyraden).
+ Skapa en __hastighetsvariabel__ för varje häxa så att alla flyger i olika hastigheter. 
+ Flytta runt häxorna på skärmen så att de inte är alla på samma plats. 

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

Har du tre häxor som rör sig från sida till sida över skärmen, som slumpvis syns och försvinner, och försvinner de då du klickar på dem?

##Spara ditt projekt {.save}

##Saker att pröva {.try}
+ __Hur många häxor är ett bra antal för spelet?__
+ __Kan du få häxorna att se olika ut? Du kan antingen ändra deras klädslar eller också använda några block från "Utseende" för att ändra dem.__
+ __Kan du göra så att häxorna är värda olika mycket poäng? Vad sägs om att göra den snabbaste (och minsta) värd 10 poäng?__


__Bra gjort, du är klar, nu kan du njuta av spelet!__
Glöm inte att du kan dela ditt spel med dina vänner och din familj på __Dela ut__ på menyn!
