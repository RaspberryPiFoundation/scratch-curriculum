---
title: Fyrverkerier
level: Nivå 1
language: sv-SE
stylesheet: scratch
embeds: "*.png"
note: "till_instruktorerna.md"
...

# Introduktion {.intro}

I det här projektet ska vi skapa ett fyrverkeri över en stad. 

##STEG 1: Skapa en raket som flyger mot muspekaren {.activity}

__Låt oss importera olika bilder för spelet__

##Checklista {.check}

1. Starta ett nytt Scratchprojekt. Radera katten genom att högerklicka på den och välja Radera. 
2. Ersätt bakgrunden med outdoor/city-with-water
3. Använd __ny sprite från fil__ för att lägga till en raketsprite till projektet (använd klädseln Resources/Rocket.png)  
4. Göm raketen när den gröna flaggan har klickats på.

Nu vill vi att raketen ska röra sig mot muspekaren när musen har klickats.

5. Lägg till ett "när mellanslag trycks"-block, och låt under detta raketen synas och glida mot muspekaren

```scratch

	när FLAGGAN klickas på
	göm
	
	när mellanslag trycks
	visa
	glid 1 sek till x: mus x y: mus y
```
		
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan, placera muspekaren över scenen och tryck på mellanslag.__

Visas raketen och rör den sig mot musen?
Vad händer om du rör musen och slår mellanslag igen?

6. Fyrverkerier brukar inte flyga från sida till sida, så låt oss se till att den alltid glider mot musen från botten av skärmen. Innan vi visar raketen, använd "gå till"-blocket för att säga åt den 
att röra sig från botten av skärmen, men stanna på samma ställe horisontellt. 
 

```scratch

	när FLAGGAN klickas på
	göm
	
	när mellanslag trycks
	gå till x: mus x y: -200
	visa
	glid 1 sek till x: mus x y: mus y
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan, placera musen över scenen och tryck på mellanslag.__
Flyger raketen mot musen från botten av skärmen? Vad händer om du rör musen och trycker mellanslag igen?

7. Slutligen, låt oss få detta att fungera genom att använda musknappen istället för mellanslag. För att göra detta kan vi avsluta vårt script i en __för alltid om musknappen?__.
Byt sedan __när mellanslag trycks__-kontrollblocket med __när flaggan klickats på__, och sist men inte minst se till att raketen är gömd när allt börjar. 

```scratch

	när FLAGGAN klickas på
	göm
	för alltid om musknappen?
		gå till x: mus x y: -200
		visa
		glid 1 sek till x: mus x y: mus y
	(slut på för alltid)
```
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan, tryck sedan på musknappen någonstans på scenen. Klicka igen på en annan punkt.__ 

##Saker att pröva {.activity}
1. Försök att göra några raketer lite långsammare eller snabbare än andra. 
2. Försök att ändra raketens riktning innan den glider mot muspekaren så att den får en båge. 

##Spara ditt projekt. {.save}

##STEG 2: Gör så att raketen exploderar {.activity}

##Checklista {.check}

1. Första steget för att få raketen att explodera är att se till att det spelas ett bang-ljud (resources\bang) innan den börjar röra på sig, och sedan gömma sig då den når musen. För att importera ett ljud, gå till Ljud-fliken och klicka på import.

```scratch

	när FLAGGAN klickas på
	göm
	för alltid om musknappen?
		gå till x: mus x y: -200
		spela ljudet bang
		visa
		glid 1 sek till x: mus x y: mus y
		göm
	(slut på för alltid)
```
2. Nu ska vi göra så att raketen sänder ett nytt meddelande när den exploderar. Vi kommer att lyssna efter detta meddelande senare.

```scratch

	när FLAGGAN klickas på
	göm
	för alltid om musknappen? 
		gå till x: mus x y: -200
		spela ljudet bang
		visa
		glid 1 sek till x: mus x y: mus y
		göm
		sänd explosion
	(slut på för alltid)
```
##Testa ditt projekt {.flag}

__Klicka på den gröna flaggan.__ 
Se till att raketen spelar ett ljud och göms när den når musen. 

##Checklista {.check}

3. Skapa en ny sprite från fil, Resources/firework1.png
4. När den tar emot explosionsmeddelandet ska den gömma sig och sedan flyttas till raketens position genom att använda "gå till"-blocket, för att sedan försvinna igen en sekund senare.

```scratch

	när jag tar emot explosion
	göm
	gå till x: x läge av raket y: y läge av raket
	visa
	vänta 1 sek
	göm
```
##Testa ditt projekt {.flag}
__Skicka en annan flygande raket.__ 
Blir den ersatt med en explosionsbild när den exploderar? 
Vad händer om du håller musknappen nere medan du rör på musen? (Oroa dig inte, vi ska fixa det här senare).

##Spara ditt projekt {.save}

##STEG 3: Gör varje explosion unik {.activity}

1. Nu kan vi göra varje explosion mer unik genom att använda "sätt färg effekten"-blocket, och låta det välja slumpmässiga färger mellan 1 och 200 innan det visas.

```scratch

	när jag tar emot explosion
	göm
	sätt färg effekten till slumptal 1 till 200
	gå till x: x läge av raket y: y läge av raket
	visa
	vänta 1 sek
	göm
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

Har varje explosion olika färg?

2. Låt oss lägga till ett antal möjliga explosionsbilder som klädslar, genom att använda Resources/firework2.png och Resources/firework3.png, och växla mellan dem för varje raket, innan den visas.

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

Har varje raket olika explosionsbilder? 

3. Slutligen, låt oss göra så att explosionen blir större efter att raketen exploderar! Istället för att vänta en sekund, sätt storleken på spriten till 5% innan den visas, och sedan när den visas öka storleken med 2 femtio gånger genom att använda ett repetitionsblock. 

```scratch

	när jag tar emot explode
	göm
	sätt färg effekt till slumpvis 1 till 200
	gå till x: x läge av raket y: y läge av raket
	sätt storleken till 5%
	visa
	repetera 50
	ändra storlek med 2
	(slut på repetera)
	göm
```
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

Sprider sig explosionsbilden från mitten av raketen och växer sakta? 

##Saker att pröva {.activity}
Varför inte försöka göra varje explosion unik genom att ändra storlek och förstoringshastighet?

##Spara ditt projekt {.save}

##Steg 4: Fixa "Sänd"-buggen {.activity}

Kommer du ihåg att vi tidigare hade problem med att hålla ner musknappen? 
Detta inträffar på grund av att när raketen sänder explosionen så kommer den att omedelbart repetera om-loopen och skicka ut ett nytt explosionsmeddelande innan den senaste har slutat synas. I datorvärlden kallas sådana problem för "buggar".

1. För att ordna detta kan vi ersätta "sända"-blocket med ett "sända och vänta"-block. På det sättet kommer loopen inte att repeteras förrän explosionen har exploderat färdigt.

```scratch

	när FLAGGAN klickas på
	göm
	för alltid om musknappen? 
		gå till x: mus x y: -200
		spela ljud bang
		visa
		glid 1 sek till x: mus x y: mus y
		göm
		sända explosion och vänta
	(slut på för alltid)
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan, håll nere musknappen och flytta muspekaren runt scenen.__ 

Syns explosionsbilden på rätt plats och vid rätt tid?

##Spara ditt projekt {.save}

__Bra gjort du är klar, nu kan du njuta av spelet!__

Glöm inte att du kan dela ditt spel med alla dina vänner och din familj genom att klicka på "Dela ut" på menyn!

