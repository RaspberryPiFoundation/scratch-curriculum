---
title: Whack-a-Witch
level: Nivå 1
notes: "till_instruktorerna.md"
layout: project
---

# Introduktion {.intro}

Det här projektet är som spelet __Whack-a-Mole__. Du får poäng för att träffa häxorna som kommer upp på skärmen. Målet är att få så många poäng som möjligt på 30 sekunder!

# STEG 1: Skapa en flygande häxa {.activity}

##Checklista {.check}

1. __Skapa ett nytt Scratchprojekt.__
2. __Radera kattspriten__ och ersätt bakgrunden med bakgrunden __nature/woods__.
3. Använd "ny sprite från fil"-knappen för att lägga till en ny häxsprite till projektet (använd __fantasy/witch1__ ). 

__Nu vill vi göra så att häxan rör sig.__

##Checklista {.check}

4. Lägg till en "variabel" för denna sprite som heter "hastighet". 
På __Scenen__, ska denna variabel visas som "__Sprite1 hastighet__". 
Om det bara står "hastighet", radera variabeln och skapa den igen, för enbart denna sprite. Klicka bort bocken från rutan bredvid hastighetsblocket i __variabelpaletten__ så att den inte syns i Scenfönstret.
Hastighetsvariabeln kommer att kontrollera hur snabbt häxan rör sig. Vi använder en variabel så att vi kan ändra hur snabbt häxan rör sig under spelets gång.  
5. Vi vill att häxan ska börja röra sig när spelet startar, __så gör ett script som ser ut så här__:

```scratch

	när FLAGGAN klickas på
	sätt hastighet till 5
	För alltid
		gå hastighet steg
	(slut på för alltid)
```
		
###Testa ditt projekt {.flag}
__Klicka på den gröna flaggan__ och se vad häxan gör. Varför fastnar hon vid kanten av skärmen?

##Checklista {.check}

6. För att förhindra att häxan fastnar måste vi göra så att hon går tillbaka åt andra hållet när hon rör vid kanten av skärmen. 
Ändra ditt befintliga script genom att lägga till ett "studsa om vid kanten"-block under "gå hastighet steg"-blocket. 

```scratch

	när FLAGGAN klickas på

	sätt hastighet till 5

	för alltid

		gå hastighet steg

		studsa om vid kanten

	(slut på för alltid)
```
7. För att förhindra att häxan vänder sig upp och ner, klicka på "enbart vänd vänster-höger"-knappen i Spriteöversiktsområdet. 

###Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 
Rör sig häxan från sida till sida över skärmen? 

Spara ditt projekt  {.save}

###Saker att pröva {.try}
__Försök att ändra värdet för hastighetsvariabeln så att hon kan flyga snabbare eller långsammare. __

__Hur skulle du göra så att häxan flyger snabbare ju längre tid hon flyger?__
(Det här är en klurig en, så oroa dig inte om du inte förtår hur man gör. Du kommer att få mer ledtrådar under tiden du arbetar med projektet.)

##STEG 2: Gör så att häxan syns och försvinner slumpvis. {.activity}

För att göra spelet roligare vill vi att häxan ska synas och försvinna slumpvis. Vi gör det med ett annat script som körs samtidigt som det som flyttar häxan. Det nya scriptet behöver gömma häxan en godtycklig tid, sedan visa henne en godtycklig tid, och fortsätta så för alltid (eller tills  spelet avslutas). 

__Skapa ett script för häxan:__

```scratch

	när FLAGGAN klickas på
	för alltid
		göm
		vänta slumptal 2 till 5 sekunder 
		visa
		vänta slumptal 2 till 5 sekunder
	(slut på för alltid)
```
###Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 
Rör sig häxan från sida till sida över skärmen och försvinner och dyker hon upp slumpvis? 

Spara ditt projekt {.save}

###Saker att pröva {.try}
__Försök att ändra intervallet av slumptal. Vad händer om du väljer väldigt höga siffror eller väldigt låga?__
(Ger det här dig några ledtrådar för hur man får häxan att öka hastigheten ju längre spelet håller på? )

##STEG 3: Gör så att häxan försvinner när hon klickas på {.activity}

För att göra detta till ett spel, måste vi ge spelaren något att göra. Den måste klicka på häxan för att få henne att försvinna. När häxan klickas på, vill vi att hon försvinner och spelar ett ljud. 

##Checklista {.check}

1. I fliken __Sounds__ importerar vi ljudet __electronic/fairydust__. 

2. __Lägg till detta script till häxan__:

```scratch

	när sprite1 klickas på 

	göm

	spela ljudet Fairydust
```
###Testa ditt Projekt {.flag}
__Klicka på den gröna flaggan.__ 

Försvinner häxan och spelar ljudet när du klickar på den? 

##Spara ditt projekt {.save}

###Saker att pröva {.try}
__Fråga en instruktör om du kan spela in ditt eget ljud för att spela upp.__

##Steg 4: Lägg till poängsättning och tidtagning {.activity}

Vi har en häxa, men nu vill vi göra ett spel! Vi vill ge poäng varje gång vi klickar på häxan men vi vill även ha en tidsgräns på spelet. Vi kan använda en variabel för poängsättning och tidtagning. 

##Checklista {.check}

1. Skapa en ny "variabel" för sprites som heter __poäng__, och ändra häxans script för att öka varibeln med 1 varje gång hon klickas på. 

```scratch
	när sprite1 klickas på
	göm
	spela ljudet Fairydust
	ändra score med 1
```

2. Byt till __Scenen__ och skapa en  __ny variabel__ (denna gång bara för Scenen) som kallas __timer__. Lägg till ett nytt script som inträffar när den gröna flaggan klickas på som sätter "timer" till __30__ och återställer score till __0__. Använd sedan "repetera tills"-blocket för att vänta en sekund och sedan minska "timer" med
ett. Detta ska fortgå tills timer är 0, då används "stoppa alla" för att stoppa spelet. 

```scratch

	när FLAGGAN klickas på
	sätt timer till 30
	sätt score till 0
	repetera tills timer = 0
		vänta 1 sekunder
		ändra timer med -1
	(slut på repetera)
	stoppa alla
```


###Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

##Spara ditt projekt {.save}

###Saker att pröva {.try}
__Hur kan du göra så att häxan ökar hastigheten under spelets gång?__


__Bra gjort, du har gjort klart det grundläggande spelet. Det finns dock fler saker som du kan göra med ditt spel. Prova på den här utmaningen!__

##Utmaning: lägg till fler häxor {.challenge}

Om det är bra med en häxa, så måste det vara ännu bättre mer fler! __Låt oss ha tre häxor som flyger omkring.__
1. Duplicera häxan genom att __högerklicka__ på den i spritelistan. 
2. __Anpassa storleken på spriten__ för varje häxa så att häxorna får olika storlek.
3. Byt __hastighetsvariabeln__ för varje häxa så att de alla flyger i olika hastigheter. 
4. Flytta runt häxorna på skärmen så att de inte är alla på samma plats. 

###Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

Har du tre häxor som rör sig från sida till sida över skärmen, som slumpvis syns och försvinner, och försvinner de då du klickar på dem?

##Spara ditt projekt {.save}

###Saker att pröva {.try}
1. __Hur många häxor är ett bra antal för spelet?__
2. __Kan du få häxorna att se olika ut? Du kan antingen ändra deras klädslar eller också använda några block från "Utseende" för att ändra dem.__
3. __Kan du göra så att häxorna är värda olika mycket poäng? Vad sägs om att göra den snabbaste (och minsta) värd 10 poäng?__


__Bra gjort, du är klar, nu kan du njuta av spelet!__
Glöm inte att du kan dela ditt spel med dina vänner och din familj på __Dela ut__ på menyn!
