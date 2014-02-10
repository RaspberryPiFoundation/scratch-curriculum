---
title: Ökenracet
level: Nivå 2
language: sv-SE
stylesheet: scratch
embeds: "*.png"
note: "till_instruktorerna.md"
...

# Introduktion {.intro}
Det här är ett spel för två personer där en papegoja och ett lejon har kapplöpning genom öknen. Varje spelare ska slå på en tangent så fort den kan för att flytta på sitt djur, och den första som når kanten på skärmen vinner.


##STEG 1: Skapa scenen och lägg till sprites {.activity}

##Checklista {.check}

1. Välj Scenen och lägg till ökenbakgrunden (öken heter desert på engelska)
2. Lägg till en ny sprite, välj lejonspriten som du hittar i mappen animals.
3. Lägg till en sprite till, nu papegojspiten som du också hittar i mappen animals.


##STEG 2: Få lejonet och papegojan att röra på sig {.activity}

Vi vill att spritearna ska röra på sig när du trycker ner en tangent.

##Checklista {.check}

1. Börja med att välja lejonspriten och säg åt den att flytta sig 4 steg när du trycken ner tangenten "L".

```scratch

	när l trycks
	gå 4 steg
```

2. Välj sen papegojspriten och gör så att den rör sig 4 steg när du trycker på tangenten "A".

```scratch

	när a trycks
	gå 4 steg
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan
Rör sig ditt lejon och din papegoja över skärmen när du trycker ner A och L?__ 

##Spara ditt projekt {.save}

##STEG 3: Starta racet {.activity}

Vi behöver ha ett sätt att påbörja racet och att veta vem som har vunnit. __Först skapar vi en startknapp.__

##Checklista {.check}

1. Lägg till en ny sprite från en fil. Välj knappspriten inuti mappen "things".
2. Redigera klädseln på knappspriten, lägg till texten "Starta" och klicka på OK. Flytta spriten till mitten av scenen.
3. Lägg nu till ett script som visar spriten när projektet körs igång:

```scratch

	when FLAGGA klickas på
	visa
```

4. Nu vill vi att knappen ska räkna ner från 3 och sen säga "GÅ!", och sen gömmas när den klickas på. Lägg till ett script som ser ut såhär:

```scratch

	när Start klickas på
	säg klara i 1 sekunder
	säg färdiga i 1 sekunder
	säg GÅ! i en sekunder
	göm
```
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

När du trycken på startknappen, räknar den ner till starten och försvinner sen?

##Spara ditt projekt {.save}

Vi vill bara att de tävlande ska röra på sig efter att racet har startat och vi vill veta när racet är slut så vi behöver en variabel som kan hålla koll på den informationen.

##Checklista {.check}

5. Lägg till en variabel till alla sprites som du kallar springer. Kryssa ur rutan intill den så att den inte visas på scenen.
6. Sätt nu springer till 0 när projektet börjar köras. Ändra i ditt "när FLAGGA klickas på"-script så att det ser ut såhär:

```scratch

	when FLAGGA klickas på
	visa
	sätt springer till 0
```

7. Nu ska du sätta springer-variabeln till att bli 1 när nedräkningen är klar.
8. Sen behöver vi stoppa lejonet och papegojan från att röra sig om inte springer-variabeln är satt till 1. Klicka på papegojspriten. __Lägg till ett kontrollblock i scriptet__ som bara tillåter
papegojan att röra sig om __springer = 1__.

```scratch

	när a trycks
	om springer = 1
		gå 4 steg
	(slut på om)
```

9. Gör nu samma sak för lejonspriten.

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Flyttar sig lejonet och papegojan bara efter att nedräkningen är färdig?

Vi vill veta vem som vinner racet och återställa det när det är slut så att du kan tävla igen.

##STEP 4: Målgången {.activity}

1. Lägg till ett block i papegojans script som sätter springer-variabeln till 0 när spriten nuddar kanten av skärmen (mål).

```scratch

	när a trycks
	om springer = 1
		gå 4 steg
		om rör kant?
			sätt springer till 0
		(slute på om)
	(slut på om)
```
2. Nu vill vi att papegojan ska säga till om den har vunnit racet. Spela in ett nytt ljud till papegojspriten som spelas upp när papegojan vinner. Klicka på __ljud__ och spela sen in ljudet av papegojan som vinner racet!
3. Lägg nu till block som spelar upp ditt inspelade ljud och får papegojan att säga det när den har vunnit:

```scratch

	när a trycks
	om springer = 1
		gå 4 steg
		om rör kant?
			sätt springer till 0
			spela ljud recording1
			säg Papegojan vann! i 3 sekunder
		(slut på om)
	(slut på om)
```
4. Repetera nu samma steg för lejonet.

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Kan du trycka på startknappen och racea genom att trycka på A och L-tangenterna?
Gör spritearna sina vinnarljud och säger att de har vunnit när de når mål (kanten på skärmen)?

##Spara ditt projekt {.save}

##STEG 5: Nollställa spelet {.activity}

När kapplöpningen är slut behöver vi berätta för de andra spritearna att vi har vunnit och nollställa spelet så att vi kan spela igen.

__Vi behöver få vinnarspriten att sända ut att den har vunnit.__

##Checklista {.check}

1. Klicka på papegojspriten.
Lägg till ett block som sänder ut "klar" efter att spriten säger att den har vunnit.

```scratch

	när a trycks
	om springer = 1
		gå 4 steg
		om rör kant?
			sätt springer till 0
			spela ljud recording1
			säg Papegojan vann! i 3 sekunder
			sända klar
		(slut på om)
	(slut på om)
```
2. Nu behöver vi lägga till ett script som lyssnar till klar-meddelandet och flyttar tillbaka papegojan till startlinjen. Vad händer om du ändrar värdet för x?

```scratch

	when jag tar emot klar
	sätt x till -175
```
3. Lägg nu till samma script för lejonet. Pröva olika x-värden för att se till att lejonet och papegojan båda är på startlinjen.
4. Vi vill också att lejonet och papegojan ska vara på samma ställe när projektet körs, så lägg till ännu ett script till båda som flyttar dem till startlinjen
när vi klickar på flaggan.

```scratch

	när FLAGGA klickas på
	sätt x till -175
```
5. Klicka nu på knappspriten och lägg till ett script som visar den när den tar emot klar-meddelandet.

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__

Kan du tävla mot en kompis genom att en av er slår på A för att flytta papegojan och den andra flyttar lejonet genom att slå på L?

##Spara ditt projekt {.save}

##Utmaning: Lägg till en booster {.challenge}

* __Pröva att lägga till en booster__ som du kan använda en gång för varje race och som flyttar papegojan eller lejonet __30 steg på en gång__.
* __Lägg till en ny klädsel__ med eld som sprutar från spriten och få den att visas när boosten används.
* __Skapa ett nytt ljud__ som spriten kan göra när boosten används.

##Testa ditt projekt {.flag}

##Spara ditt projekt {.save}

__Bra jobbat, nu är du klar och kan spela ditt spel!__
Glöm inte att du kan dela spelet med dina kompisar och din familj genom att klicka på __Dela ut__ i menyn!
