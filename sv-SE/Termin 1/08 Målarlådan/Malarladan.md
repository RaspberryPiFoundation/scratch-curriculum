Nivå 3

#Målarlådan

__Introduktion:__
I det här projektet bygger vi ett ritverktyg som du kan använda för att skapa din egen konst. Du kan byta färg, tömma skärmen, göra stämplar och mycket mer!

##STEG 1: Dra och måla

Vi börjar med en penna som ritar när du drar runt den på Scenen.

1. Skapa ett nytt Scratchprojekt. Radera katten genom att högerklicka på den och välj radera.
2. Klicka på __Scenen__ och sen på fliken __Bakgrunder__. Ladda upp bakgrunden frame.bmp.
3. Skapa en ny sprite som du kallar __penna__, använd __resources\green-pencil.__
4. Byt till fliken __klädslar__ och __Redigera__, ändra sen mittpunkten av bilden så att den hamnar på pennans spets. För att göra det kan du klicka på __Sätt mittpunkt på klädseln__ och dra i linjerna tills de hamnar på spetsen.
5. Få pennan att följa muspekaren runt scenen genom att använda __för alltid__ och __gå till musmarkör.__

```scratch
när FLAGGA klickas på
för alltid
	gå till musmarkör
(slut på för alltid)
```

__Nu vill vi använda den här pennspriten som en riktig penna.__ Om du tittar under avdelningen Penna hittar du alla möjliga block som har att göra med att rita. De som vi ska börja med är __penna ned__ och __penna upp.__

6. Vi vill använda musknappen för att kontrollera pennan - alltid när musknappen är nere ska pennan vara nere, och när den är uppe ska pennan vara uppe. Vi kan göra det här genom att använda blocken om... annars och musknappen?

```scratch
när FLAGGA klickas på
för alltid
	gå till musmarkör
	om musknappen?
	penna ned
	annars
	penna upp
	(slut på om)
(slut på för alltid)
```

##Testa ditt projekt
__Klicka på den gröna flaggan.__
Följer pennan muspekaren? Vad händer om du håller nere musknappen och flyttar musen? Bry dig inte om färgen på pennan än.

7. Till slut kommer skärmen bli helt fylld med pennstreck. Blocket radera kan användas för att tömma skärmen.

```scratch
när FLAGGA klickas på
radera
för alltid
	gå till musmarkör
	om musknappen?
	penna ned
	annars
	penna upp
	(slut på om)
(slut på för alltid)
```

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Försvinner din teckning när du klickar på den gröna flaggan?

SPARA DITT PROJEKT

##STEG 2: Radera allt

Istället för att behöva starta om hela projektet för att tömma skärmen, vill vi ha en knapp som suddar ut teckningen. Den ska göra det genom att använda blocket radera.

1. Skapa en ny sprite från klädseln __resources/cancel button__.
2. Byt namn på spriten till __radera__.
3. Placera spriten någonstans i det nedre vänsta hörnet av scenen.
4. Ge raderaspriten det här enkla scriptet:

```scratch
när radera klickas på
radera
```

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Tömmer raderaknappen din skärm?

SPARA DITT PROJEKT

##STEG 3: Byta färg

Hittills kan vi bara rita blåa streck. Nu vill vi rita med fler färger! Vi lägger till lite fler sprites längst ner på skärmen. Spritearna kommer se ut som färgade knappar. Om vi klickar på en knapp kommer den byta färg på strecket vi ritar. För att låta oss hålla koll på vilken färg vi använder ska knappen även byta färg på pennspriten.

1. Lägg till en ny sprite som du kallar __röd__ Använd klädseln __resources/red-selector__.
2. Placera den någonstans längst ner på skärmen, nära __radera-knappen__.
3. När spriten klickas på, ska den skicka ut meddelandet __röd__.

```scratch
när röd klickas på
sända röd
```

__Ja, det är allt den gör. Grovjobbet görs av pennan.__

Importera en ny röd klädsel till pennan, använd __resources/red-pencil__. Fixa så att mittpunkten blir pennspetsen som vi gjorde förut.

4. Lägg till ett nytt script till pennan. När pennan tar emot meddelandet __röd__ ska den byta till den röda pennklädseln och också byta pennfärgen till röd (genom att använda blocket sätt pennans färg till).

__Tips:__ om du klickar på den färgade rutan i blocket __sätt pennans färg till__ så kan du klicka med pipetten på den röda spriten och sno dess färg till rutan.

```scratch
när jag tar emot röd
växla till klädsel röd-penna
sätt pennans färg till (röd)
```

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Börja med att rita ett streck. Klicka sen på spriten som gör pennan röd och rita lite mer. Bytter pennan klädsel? Ritar den i rött nu? Ritar den från pennspetsen?

SPARA DITT PROJEKT

5. Gör om det just gjorde för blå, gul och grön väljfärgarsprite.

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Fungerar alla färgvalknappar? Byter de pennans klädsel till rätt färg? Får de alla pennan att måla med rätt färg? Ritar alla pennans klädslar med pennspetsen?

SPARA DITT PROJEKT

##STEG 4: Rita bara inom ramarna

Du har säkert märkt att du kan måla överallt på skärmen, till och med på kanten. Så vill vi inte ha det. Vi vill ha målningen i mitten av Scenen. Vi kan lösa det genom att se till att pennan inte kan lämna ritytan - den ljusgrå delen av Scenen.

Kom ihåg att Scratch pratar om punkter på skärmen med en x- och en y-axel. Vår rityta finns mellan 230 och -230 på x-axeln och 170 och -120 på y-axeln. Vi kan vända de här värdena i ett __om__-block, då ser vi till att muspekaren är inom den här ytan innan pennan börjar rita där.

För att göra det här kan vi göra ett nytt block runt omkring ditt nuvarande __gå till... om__-block, och inuti det nya om-blocket kolla efter följande:

mus y är större än -120 och mus y är mindre än 170
och mus x är större än -230 och mus x är mindre än 230

__Obs!__ för att göra det här kommer du behöva använda flera stycken __och__-operatorblock, ett för de två villkoren för mus x, ett för de två villkoren för mux y, och så ytterligare ett för att sätta ihop alla:

```scratch
radera
för alltid
om mus y är större än -120 och mus y är mindre än 170 och mus x är större än -230 och mus x är mindre än 230
gå till musmarkör
```

Eftersom vi inte kan rita utanför ritytan kan vi gömma pennverktyget när vi lämnar ytan. För att göra det byter vi ut blocket __om__ mot ett __om annars__ -block. Behåll samma villkor för __om__, och __visa__ pennan om det är sant, göm den annars.

```scratch

när FLAGGA klickas på
penna upp
radera
för alltid
	om mus y är större än -120 och mus y är mindre än 170 och mus x är större än -230 och mus x är mindre än 230
		gå till musmarkör
		visa
		om musknappen?
			penna ned
		annars
			penna upp
		(slut på om)
	annars
		göm
	(slut på om)
(slut på för alltid)
```

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Kan du fortfarande rita inom ritytan? Kan du rita utanför ritytan? Vad händer med pennan när du lämnar ritytan och går tillbaka till den?

SPARA DITT PROJEKT

##STEG 5: Suddgummi

__Det är kul att rita streck, men det händer att man gör ett misstag och vill kunna sudda.__ Vi kan göra det med ett nytt pennverktyg som ritar med grått (samma färg som bakgrunden).

Lägg till en ny knappsprite till Scenen för att kunna välja suddgummit. Använder klädseln __resources/eraser__ som du gör lite mindre så att den passar in längst ner på Scenen. Den ska fungera på samma sätt som de andra färgvalsknapparna, och sända ut ett suddmeddelande.

Pennspriten ska svara på suddmeddelandet genom att byta pennfärg till grå (kom ihåg att du kan använda __pipetten__ för att välja färgen från bakgrunden). Den kommer även behöva en klädsel som ser ut som ett suddgummi: använd samma klädsel, __resources/eraser__. __Kom ihåg att ändra klädselns mittpunkt.

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Suddar suddgummit? Fungerar det ända fram till kanten? Kan du byta mellan penna och sudd?

SPARA DITT PROJEKT

##STEG 6: Stämplar

Det nästa vi ska göra är att skapa ett stämpelverktyg som vi kan ha för att stämpla små bilder på teckningen.
Aktivitetslista

1. Skapa en ny sprite med vilken klädsel som helst. Krymp spriten och placera den längst ner på scenen bredvid de andra verktygen. När den här spriten klickas på ska den __sända ut meddelandet stämpel__
2. Lägg till en ny klädsel till den här pennspriten, samma som du valde till __stämpel__ -knappen.
3. Välj pennspriten och skapa en ny variabel som heter __pennläge__ bara för den spriten. Vi ska använda den här variabeln för att hålla koll på om vi ritar eller stämplar.
4. Lägg till ett nytt script som svarar på stämpelmeddelandet. Det ska byta klädsel till stämpeln och sätta variabeln __pennläge__ till _falskt__.
5. Ändra i de andra scripten som svarar på verktygsväljarmeddelanden (röd, grön, blå och sudd) så att de var och en sätter __pennläge__ till __sant__.
6. Till sist ska vi se till att den här variabeln kollas __när musknappen är nere__, så att programmet vet om vi ska rita eller stämpla. Om pennläge = sant ska vi använda den befintliga __penna ned__, annars stämpeln.

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Fungerar stämpelverktyget som du vill?

Vad händer om du byter tillbaka till ett av de vanliga pennverktygen?

SPARA DITT PROJEKT

__Snyggt jobbat, nu är du klar med de grundläggande stegen i det här projektet.
Pröva de här utmaningarna!__

##Utmaning 1: Regnbågspenna

Vi lägger till en specialpenna som målar i regnbågens alla färger. Det kan man ju inte göra med riktiga pennor, så det blir kul att få datorn att göra det. Hemligheten bakom regnbågsmålning är blocket ändra pennans färg med.

Lägg först till regnbågsverktygväljarspriten och regnbågsverktygklädseln till pennspriten:

1. Skapa en ny verktygsväljarsprite och placera den längst ner på scenen, bredvid alla de andra pennfärgspritearna. Använd klädseln resources/rainbow-selector och låt den sända ut meddelandet regnbåge när den klickas på.
2. Lägg till klädseln resources/rainbow-pencil till pennspriten.

Du behöver skapa ett script som byter pennfärg många gånger varje sekund för att skapa regnbågseffekten (Att ändra siffran med 5 var 0,05:e sekund funkar bra, men testa med olika värden). Scratchkortet om timers förklarar hur du kan få något att hända med jämna mellanrum. Använd blocket "ändra pennans färg med 5" istället för blocket "ändra timer med -1" inuti loopen.

Du behöver också kontrollera den loopen så att den bara ändrar pennfärgen när du har valt regnbågspennan, annars kommer alla pennor rita regnbågsfärger! Du kan åstadkomma det här på ett sätt som är väldigt likt hur pennspriten byter mellan penn- och stämpelläge. Du behöver skapa en variabel som heter regnbågsbyte och som har värdet sant när du vill ha regnbågseffekt och falskt när du inte vill det. Varje gång pennan svarar på ett verktygsbytesmeddelande ska den sätta värdet på regnbågsbyte därefter.

Använd det du lärt dig från stämpelsteget ovan för att kontrollera regnbågseffekten. Scriptet som svarar på verktygsväljarmeddelanden kommer sätta två variabler var: pennläge och regnbågsbyte.


##Testa ditt projekt
__Klicka på den gröna flaggan.__

Fungerar regnbågsverktygen som du vill?

Vad händer när du byter tillbaka till någon av de vanliga pennverktygen?

SPARA DITT PROJEKT

##Utmaning 2: Kortkommandon

Istället för att använda verktygsväljarspritearna längst ner på scenen kan du använda tangentbordet för att välja olika verktyg.
Du kan använda [] nedtryckt?-block för att svara på tangentbordstryckningar. För varje tangent du vill använda måste du dra in ett nytt [] nedtryckt?-block, som skickar samma meddelande som respektive verktygsväljarsprite skickar när den klickas på. Lägg till dessa scripts till scenen.

Det kan vara bra att låta kortkommandot vara en bokstav som påminner om det man ska göra med det, till exempel s för stämpla.

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Har alla verktyg ett eget kortkommando nu? Fungerar alla på rätt sätt när du väljer dem med tangetbordet? Är de rätta verktyget fortfarande valda med verktygsväljarspritearna på scenen?

SPARA DITT PROJEKT

##Utmaning 3: Stor och liten
En annan funktion som de flesta ritprogram har är att kunna byta storlek på pennan. Vi lägger till det.
Det finns en svårighet dock, nämligen att ibland behöver vi ändra storlek på pennan och ibland behöver vi ändra storlek på pennspritens klädsel. Det beror på om vi använder en penna eller en stämpel.

Skapa två nya verktygsväljarsprites, som du kallar större och mindre. Den ska ha klädslarna resources/bigger-selector och resources/smaller-selector, och ska skicka meddelandena "större" och "mindre".

Pennspriten kan svara på meddelandena genom att ändra antingen pennstorlek med 1 eller klädselstorlek med 10, beroende på värdet hos variabeln pennläge (använd ett om-annars-block, ungefär på samma sätt som spriten väljer mellan att rita eller stämpla).
Glöm inte att skapa kortkommandon för förstoringen och förminskningen. T.ex. upp- och nertangenterna.

SPARA DITT PROJEKT

Du kanske har lagt märke till att varje gång du ändrar storlek på stämpeln ändras också storleken på pennan när du byter till den.
För att förhindra att det händer behöver du sätta storleken till 100% varje gång du byter till ett pennverktyg. Då får verktyget rätt storlek.

För att göra allt ännu bättre, låt stämpeln komma ihåg vilken storlek den hade innan du valde pennverktyget och gå tillbaka till den storleken när du väljer stämpelverktyget igen. Det lättaste sättet att göra det här är att skapa en ny variabel som heter "stämpelstorlek", som uppdateras med den nuvarande storleken varje gång stämpelns storlek ändras. När stämpelverktyget sen väljs kan den hämta sin storlek från den här variabeln.

##Testa ditt projekt
__Klicka på den gröna flaggan.__

Fungerar storleksförändring på pennorna?

Vad händer om du byter till en stämpel, ändrar storleken på den och sen byter tillbaka till en penna?

SPARA DITT PROJEKT


__Snyggt jobbat, nu är du klar! Varsågod och rita något vackert.__

Glöm inte att du kan dela det här spelet med kompisar och familj genom att klicka på __Dela ut__ i menyn!