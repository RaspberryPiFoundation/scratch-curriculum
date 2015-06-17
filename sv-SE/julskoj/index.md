---
title: Julskoj
level: Nivå 2
language: sv-SE
stylesheet: scratch
embeds: "*.png"
---

##Introduktion {.intro}
__I det här projektet kommer vi att skapa ett spel med rullande bakgrunder, poängsättning och en festlig Game Over-skärm.__
En olycka i en leksaksfabrik har gjort att julklappar faller ner från himlen. Hjälp Rudolf att rädda Julen genom att fånga julklapparna!

##STEG 1: Gör så att Rudolf flyger {.activity}

##Checklista {.check}

1. Starta ett nytt Scratchprojekt. Ta bort katten genom att högerklicka på den och välja Radera. 
2. Byt bakgrunden till SkyBackground.png.
3. Använd __Välj ny sprite från fil__ knappen för att lägga till Rudolf-spriten till projektet (använd __Rudolph.png__ filen)
4. Byt namn på spriten till __Rudolf__.
5. Gör så att Rudolf följer musen genom att använda följande script: 


```scratch
när FLAGGA klickas på
lägg överst
för alltid 
	gå till musmarkör
(slut på för alltid)
```

##Testa ditt projekt {.flag}

__Klicka på den gröna flaggan och flytta på muspekaren__, följer Rudolf efter muspekaren? 

##Checklista {.check}

6. För att göra spelet mer intressant ska vi lägga till några rörliga snöiga backar så att det ser ut som att Rudolf flyger. Använd knappen __Välj ny sprite från fil__ för att lägga till Snöspriten till projektet ( använd filen __SnowHills.png)
7. Byt namn på spriten till __Snow1__.
8. Skapa en ny variabel genom att klicka på Variabler och Ny variabel. Kalla den ScrollX och skapa den för alla sprites, bocka sedan av rutan bredvid för att 
ta bort variabeln från scenen. Den här variabeln kommer att användas för att kontrollera hur backarna rör sig. 
9. Lägg till följande script för att göra så att backarna rör sig:

```scratch
när FLAGGA klickas på 
sätt y till 0
för alltid
	sätt x till ScrollX
	ändra ScrollX med -1
	om ScrollX < -480
		sätt ScrollX till 0
	(slut på om)
(slut på för alltid)
```

##Testa ditt projekt {.flag}

__Klicka på den gröna flaggan__, rör sig backarna? Vad händer då backarna rör sig mot sidan av scenen? 

##Checklista {.check}

10. Låt oss fixa problemet med att de snöiga backarna flimrar då de når den högra sidan av skärmen. Lägg till mer backar till scenen genom att använda __Välj ny sprite från fil__ knappen för att lägga till Snö-spriten till projektet igen (använd SnowHills.png-filen).
11. Byt namn på spriten till __Snow2__.
12. Lägg till följande script till Snow2-spriten för att tillåta en ytterligare uppsättning av backar som följer tätt efter det första: 

```scratch
när FLAGGA klickas på 
sätt y till 0
för alltid
	sätt x till ScrollX + 479
(slut på för alltid)
```

##Testa ditt projekt {.flag}

__Klicka på den gröna flaggan__, rör sig backarna? Har problemet med de flimrande träden försvunnit? 

##Spara ditt projekt {.save}

##STEG 2: Fallande julklappar {.activity}

##Checklista {.check}

1. Vi måste nu lägga till julklappar som Rudolf ska samla in. Använd knappen __Välj ny sprite från fil__ för att lägga till Julklapp-spriten till projektet (använd Present.png filen).
2. Byt namn på spriten __Julklapp__.
3. __Skapa en ny variabel__ genom att klicka på __variabler__. Kalla den för `Stopp` och gör den för enbart för denna sprite, bocka sedan av rutan bredvid för att ta bort den från scenen. Denna kommer att användas för att kontrollera när julklappen ska tas bort från spelet. 
4. __Skapa en annan variabel__ och kalla den för "hastighet" - gör så att den finns för enbart denna sprite. Bocka sedan av rutan bredvid för att ta bort variabeln från scenen. Den här variabeln kommer att användas för att kontrollera julklapparnas hastighet då de faller nerför skärmen. 
5. Lägg till följande script till __Julklapp__ -spriten för att låta den falla ned från himlen. Notera att vi kommer att använda "slumptal" för att göra så att julklapparna framträder på olika ställen varje gång. 
6. Genom att använda kommandot "rör [ Rudolf ]" kan vi göra så att julklappen försvinner när den vidrörs. Detta kan vi använda senare för att sätta poäng. 


```scratch
när FLAGGA klickas på
för alltid
	sätt Stopp till 0
	gå till x: slumptal -230 till 230 y: slumptal 50 till 170
	sätt Hastighet till -1
	repetera tills stopp = 1
		ändra y med hastighet 
		om y-läge av Present < -160
			sätt stopp till 1
		(slut på om)
		om rör Rudolf?
			sätt stopp till 1
		(slut på om)
	(slut på repetera)
(slut på för alltid)
```

##Testa ditt projekt {.flag}

__Klicka på den gröna flaggan,__ faller julklapparna från himlen? Försvinner de när Rudolf rör dem eller då de slår i marken?

##Checklista {.check}

7. Låt oss göra spelet mer intressant genom att byta färg på julklapparna varje gång de faller ner. Gör detta genom att använda ändra färg-kommandot. 
8. Ändra hastigheten på varje julklapp genom att byta ut sätt hastighet  med slumptal-kommandot, prova olika värden som -10 till -1. Ditt script ska nu se ut så här. 


```scratch
när FLAGGA klickas på
för alltid
	sätt stopp till 0
	gå till x: slumptal -230 till 230 y: slumptal 50 till 170
	ändra färg effekten med slumptal 1 till 100
	sätt hastighet  till -1
	repetera tills stopp = 1
		ändra y med hastighet 
		om y-läge av Present < -160
			sätt stopp till 1
		(slut på om)
		om rör Rudolf?
			sätt stopp till 1
		(slut på om)
	(slut på repetera)
(slut på för alltid)
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan,__ faller julklapparna med olika hastighet och har de olika färg?

##STEG 3: Poängsättning och ljudeffekter {.activity}

##Checklista {.check}

1. __Låt oss ändra vårt script för att hålla koll på poängsättningen i spelet.__ Vi kan sedan använda detta för att bestämma när game over-meddelandet ska visas.
2. Skapa en ny __variabel__ genom att klicka på variabler. Kalla den "Poäng" och gör den för alla sprites. Låt denna variabel vara ibockad så att den syns på skärmen. 
3. Ändra scriptet bakom __Present__ spriten så att det ser ut så här. Notera att vi har lagt till både ljudeffekter med `spela trumman` kommandot och även  `ändra [ score ] med 1` när Rudolf rör julklappen.


```scratch
när FLAGGA klickas på
för alltid
	sätt stopp till 0
	gå till x: slumptal -230 till 230 y: slumptal 50 till 170
	ändra färg effekten med slumptal 1 till 100
	sätt hastighet  till -1
	repetera tills stopp = 1
		ändra y med hastighet 
		om y-läge av Present < -160
			spela trumman 57 i 0.2 taktslag
			sätt stopp till 1
		(slut på om)
		om rör Rudolf?
			spela trumman 39 i 0.2 taktslag
			sätt stopp till 1
			ändra poäng med 1
		(slut på om)
	(slut på repetera)
(slut på för alltid)
```

4. Låt oss lägga till lite musik till spelet, importera ljudfilen __Jingle_Bells.mp3__ till __Scenen__.

```scratch
när FLAGGA klickas på
sätt ScrollX till 0
sätt Score till 0
spela ljudet Jingle_Bells
```

5. Lägg till följande script till __Scenen__, detta kommer att __sätta poängen till 0__ när spelet startas. Det kommer också att spela Jingle Bells när spelet spelas. 

Notera, om musiken till en början låter "hackig" ska du spara projektet, stänga ner Scratch och öppna projektet igen.  

##Testa ditt projekt {.test}

__Klicka på den gröna flaggan,__ ändras poängen när Rudolf rör vid en julklapp? 

##Spara ditt projekt {.save}

##STEG 4: Game over {.activity}

##Checklista {.check}

1. __Låt oss ändra vårt script för att hålla koll på poängen i spelet.__ Vi kan använda detta senare för att bestämma när game over-meddelandet ska visas. 
2. Ändra scriptet på __Scenen__ så att när __poäng når 10__ ska vi "sända" ett __GameOver__ -meddelande. 

```scratch
när FLAGGA klickas på 
sätt ScrollX till 0
sätt Score till 0
spela ljudet Jingle_Bells
för alltid
	om score = 10
		sända GameOver och vänta
	(slut på om)
(slut på för alltid)
```

3. Vi måste nu lägga in vårt GameOver-meddelande. Använd knappen __Välj ny sprite från fil__ för att lägga till __GameOver__ -spriten till projektet (använd filen GameOver.png).
4. Byt namn på spriten till __GameOver__.
5. __Lägg till följande script till GameOver-spriten.__ Detta kommer att gömma bilden när spelet startar och visa den när GameOver-meddelandet har tagits emot. 


```scratch
när FLAGGA klickas på 
göm

när jag tar emot GameOver
lägg överst
visa
stoppa alla
```

##Testa ditt projekt {.flag}

__Klicka på den gröna flaggan,__ ändras poängen när Rudolf rör vid julklappen? 

##Spara ditt projekt {.save}

##Utmaning: Gör spelet svårare {.challenge}

* Kan du få julklapparna att vingla på deras väg nerför skärmen? 
* Kan du lägga till mer än en julklapp till spelet på samma gång? 
* Ändra GameOver-meddelandet så att det visas efter att 20 julklappar har samlats in. 
* Kan du minska poängen med 1 när en julklapp slår i marken? 

__Bra gjort du är klar, nu kan du njuta av spelet.__
Ha en riktigt God Jul!
