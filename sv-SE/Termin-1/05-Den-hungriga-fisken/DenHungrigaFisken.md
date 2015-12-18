---
title: Den hungriga fisken
level: Nivå 2
language: sv-SE
stylesheet: scratch
embeds: "*.png"
note: "till_instruktorerna.md"
...

# Introduktion {.intro}
Vi ska göra ett spel om en hunrgig fisk! Styr den stora Hungriga Fisken och försök att äta upp alla kräftor som simmar omkring.

##STEG 1: Skapa en sprite som följer muspekaren {.activity}
__Nu ska få vi den Hungriga Fisken att simma omkring i havet!__

##Checklista {.check}

1. Skapa ett nytt Scratchprojekt.
2. Välj Scenen, och sen scenens flik Bakgrunder. Importera bakgrunden nature/underwater och ta bort background1.
3. Byt namn på Sprite 1 så den heter Hungriga Fisken.
4. Importera Hungriga Fiskens klädsel från resources/hungry-fish och ta sedan bort dess befintliga costume1 och costume2.
5. Klicka på knappen ovanför Klädslar-fliken så att fisken bara kan simma höger-vänster.
6. Nu ska du skapa ett script för Hungriga Fisken så att den följer muspekaren runt i havet. Det gör du såhär:


```scratch

	när FLAGGA klickas på
	för alltid		
		peka mot musmarkör
		gå 3 steg
	(slut på för alltid)
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 
Flytta runt muspekaren i havet. Följer fisken pekaren?
Vad händer om du inte flyttar muspekaren och fisken hinner ikapp den? Hur ser det ut? Varför händer det?

7. Du kan stoppa Hungriga Fisken från att flippa som en galning om du gör så att den bara rör sig när den inte är för nära muspekaren.
(_avstånd till_-blocket finns i Känna av-paletten.)


```scratch

	när FLAGGA klickas på
	för alltid om avstånd till musmarkör > 10
		peka mot musmarkör
		gå 3 steg
	(slut på för alltid)
```


##Testa ditt projekt {.flag}

##Spara ditt projekt {.save}

##Saker att pröva {.try}

Om du vill så kan du byta ut siffrorna i scriptet till andra. Hur påverkar det hur Hungriga Fisken rör sig? Byt ut avståndströskeln till ett högre nummer (t.ex. 100) eller ett lågt nummer (t.ex. 1). Byt ut hur mycket fisken fisken rör sig till ett högt nummer (t.ex. 20) eller ett lågt nummer (t.ex. 1 eller till och med 0).

##STEG 2: Lägg till lite kräftor {.activity}

1. Skapa en ny sprite från filen animals/lobster1.
2. Använd Förminska sprite-verktyget (ovanför Scenen) för att göra spriten mindre.
3. Skapa ett script som får kräftorna att simma omkring. Vi vill att de ska röra sig slumpvist, så vi får dem att gå framåt en liten bit och gör sen så att de slumpvist vänder sig åt vänster eller höger, och sen fortsätter så.


```scratch

	när FLAGGA klickas på
	för alltid		
		gå 2 steg
		vänd slumptal -20 till 20 grader
		studsa om vid kanten
	(slut på för alltid)
```


##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan__ och se hur kräftorna simmar omkring. Simmar de som du hade tänkt dig? Simmar de realistiskt?

__Just nu interagerar inte Hungriga Fisken med kräftorna. Det löser vi i nästa steg.__

##Spara ditt projekt {.save}

##Saker att pröva {.try}

* Pröva att byta ut siffrorna i slumptalet och gå-blocken. Rör sig kräftorna annorlunda?
* Vad gör __studsa om vid kanten__-blocket? Ta bort det och se vad som händer.


##STEG 3: Hungriga Fisken äter kräftorna {.activity}

__Nu vill vi att Hungriga Fisken ska äta kräftorna!__ När Hungriga Fisken har fångat en kräfta i munnen ska två saker hända:
* Hungriga Fisken ska stänga sin mun och göra ett ätljud.
* Kräftan ska försvinna för att sen komma tillbaka lite senare.

##Checklista {.check}

1. Först får vi kräftan att försvinna om den nuddar Hungriga Fisken, för att sen komma tillbaka 3 sekunder senare. Använd rör-blocket för att se om kräftan vidrör fisken.


```scratch

	när FLAGGA klickas på
	för alltid	
		gå 2 steg
		vänd slumptal -20 till 20 grader
		studsa om vid kanten
		om rör Hungriga Fisken?
			göm
			vänta 3 sekunder
			visa
		(slut på om)
	(slut på för alltid)
```

##Testa ditt projekt {.flag}
__Testa ditt spel igen - kan du hitta några fel?__ Lägg märke till att kräftorna försvinner oavsett var på Hungriga Fisken den nuddar. Och så skulle fisken bara kunna vänta i 3 sekunder och äta kräftan igen precis när den kommer tillbaka - vilket inte är så rättvist!

##Checklista {.check}
2. Hur kan vi se till att kräftan bara försvinner om den nuddar Hungriga Fiskens mun? Vi skulle kunna använda rör färgen-blocket och kolla om den nuddar fisken blå tänder. För att göra det här behöver du byta ut rör-blocket mot
ett rör färgen-block i ditt script, sen klicka på färgen i blocket och till sist klicka på fiskens tänder.
3. Sen kan vi få kräftan att röra sig mot en slumpvis punkt på skärmen innan den kommer tillbaka igen, och ge den ett slumpvärde för x och y.

```scratch

	när FLAGGA klickas på
	för alltid		
		gå 2 steg
		vänd slumptal -20 till 20 grader
		studsa om vid kanten
		om rör färgen []?
			göm
			vänta 3 sekunder
			gå till x:slumptal -220 till 220 y: slumptal -170 till 170
			visa
		(slut på om)
	(slut på för alltid)
```
##Testa ditt projekt {.flag}

Testa spelet igen - försvinner kräftan bara om den har nuddat fiskens mun? Och kommer den tillbaka på en slumpvis punkt på skärmen istället för där den var när den åts upp?

##Checklista {.check}

4. Fisken behöver veta när den har ätit något så att den kan spela ett ljud och byta utseende. För att lösa det kan vi låta kräftan sända ut att den har blivit uppäten innan den försvinner.

```scratch

	när FLAGGA klickas på
	för alltid		
		gå 2 steg
		vänd slumptal -20 till 20 grader
		studsa om vid kanten
		om rör färgen []?
			sända du fick mig
			göm
			vänta 3 sekunder
			å till x:slumptal -220 till 220 y: slumptal -170 till 170
			visa
		(slut på om)
	(slut på för alltid)
```
__Nu vill vi att fisken ska svara på det här meddelandet genom att göra ett ätljud och slå ihop käkarna.__


##Checklista {.check}

5. Lägg till klädseln resources/mouth-closed och ljudet resources/chomp till Hungriga Fisken-spriten.
6. Lägg sen till ett nytt script till Hungriga Fisken så att den svarar på meddelandet som kräftan skickat ut. Det här scriptet ska få fisken att spela upp ätljudet och byta till klädseln med stängd mun, vänta lite grann och sen byta tillbaka igen.


```scratch

	när jag tar emot du fick mig
	spela ljudet chomp
	repetera 2
		växla till klädsel mouth-closed
		vänta 0.5 sekunder
		växla till klädsel hungry-fish
	(slut på repetera)
```

__Nu är Hungriga Fisken redo att äta, så vi fyller havet med kräftor. Högerklicka på kräftspriten och klicka på "kopiera" flera gånger.__

##Testa ditt projekt {.flag}
Klicka på den gröna flaggan.
Äter den Hungriga Fisken kräftorna?  Äter den alla kräftorna?

##Spara ditt projekt {.save}

##Saker att tänka på
Varför måste vi lägga till ett visa-block i början av kräftans script? Fundera på vad som skulle hända om kräftan blev uppäten och spelet avslutades innan den hann komma tillbaka. Vad skulle hända om spelet startades om då?


__Bra jobbat, nu är du klar med grundspelet. Men det finns fler saker du kan lägga till. Är du redo för en utmaning?__


##Utmaning 1: Få kräftorna att röra sig annorlunda {.challenge}

Just nu rör sig alla kräftorna på samma sätt. __Kan du få en av dem att röra sig annorlunda?__
__Ledtråd:__ Lägg inte för mycket tid på den här delen utan att kolla in de andra utmaningarna i det här projektet.

__Välj en av kräftorna att experimentera med.__ Om de alla har samma klädsel, ändra färgen på experimentkräftan med __ändra färgeffekten__-blocket. På så vis kan du alltid känna igen den.

Gör så att experimentkräftan rör sig långsammare än de andra. __Ledtråd:__ Kolla in gå 2 steg-blocket.


##Testa ditt projekt {.flag}
Rör sig kräftan långsammare? Gör det spelet roligare?
Nu kan du __pröva att få en av kräftorna att röra sig snabbare än de andra.__

Rör sig kräftorna fortfarande på ett bra sätt? Gör de här ändringarna att spelet blir roligare?
__Ledtråd:__ Om dina kräftor simmar runt i cirklar, kolla in värdena i slumptal-blocket och vänd-blocket.

Tänk om du skulle göra så att alla kräftor betedde sig olika, genom att ändra de här värdena på olika sätt?

Gör någon av dina ändringarna att spelet blir bättre? Gör de spelet mer intressant, kul, svårt, eller lätt? 

##Spara ditt projekt {.save}

##Utmaning 2: Få kräftorna att undvika Hungriga Fisken {.challenge}

Kräftorna i det här spelet är väldigt dumma! De bara simmar omkring hursomhelst tills de blir uppätna. Riktiga bytesdjur simmar bort från rovdjur. __Vi gör så att en av kräftorna simmar iväg från Hungriga Fisken.__

Det finns inget block i Scratch som säger vilket håll en annan sprite är på väg åt. Men du kan få en sprite att peka mot en annan spite, och sen få den att vända sig åt andra hållet. Blocken du behöver finns i __Rörelse__-paletten.

__Gör nu så att en av kräftorna alltid pekar åt motsatt håll som Hungriga Fisken.__ Du kanske även vill få den att vagga lite när den simmar iväg.

##Testa ditt projekt {flag}
Gör det här kräftan svårare att fånga? Gör det spelet bättre?

##Spara ditt projekt {.save}

##Utmaning 3: Lägg till ett poängsystem {.challenge}
Det räcker inte med att bara äta kräftor. Hur vet du att du är bättre än dina kompisar? __Du måste ha ett sätt att hålla koll på poängen, så vi lägger till en poängtavla.__ Titta på Scratch-kortet __Keep Score__ som beskriver hur man gör det.

Var ska du lägga blocket som uppdaterar poängen?

Se till så att poängen nollställs i början av spelet. Var ska det blocket vara?

##Testa ditt projekt {.flag}
Nollställs poängen när du startar spelet? Blir den högre varje gång du äter en kräfta?

##Spara projektet {.save}

##Utmaning 4: Lägg till en timer {.challenge}

__Ge dig själv en tidsgräns i spelet.__ Hur många kräftor kan du äta på 30 sekunder?

Titta på Scratch-kortet __Timer__ för att förstå hur man lägger till en timer i spelet. Börja med att spelet håller på i 30 sekunder.

##Testa ditt projekt {.flag}
Börjar timern på 30?

Tickar den ner i rätt hastighet?

Kan du fånga kräftor medan timern är igång?

Avslutas spelet när timern blir 0?

Spara ditt projekt

##Utmaning 5: Lägg till bonuspoäng {.challenge}
Dela ut en stor bonuspoäng om du kan äta alla tre kräftorna på samma gång. Hur kan du hålla koll på hur många kräftor som har blivit uppätna?
__Ledtråd:__ Ett sätt att göra det här på är att __använda en variabel för att räkna hur många kräftor som simmar omkring.__


##Spara ditt projekt {.save}

##Utmaning 6: Ändra spelreglerna: håll kräftorna vid liv! {.challenge}
Ibland får man de bästa idéerna genom att ta en existerande idé och göra motsatsen.

__Ändra i spelreglerna så att du, istället för att kontrollera fisken som försöker äta de andra, kontrollerar en kräfta i havet med massor av Hungriga Fiskar.__ Hur länge kan du klara dig utan att bli uppäten?

##Spara ditt projekt {.save}

__Bra jobbat, du är klar! Nu kan du spela!__
Kom ihåg att du kan dela med dig av spelet till dina kompisar och din familj genom att klicka på __Dela ut__ i menyn!
