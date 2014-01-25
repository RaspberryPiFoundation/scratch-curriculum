#NOTES FOR CLUB LEADERS
##(Målarlådan)

###Introduktion

I det här projektet skapar vi ett enkelt ritverktyg. Det ritar en linje när man drar musen över skärmen. Man kan ändra färg på linjen och tömma skärmen.

###Färdigheter

Det här projektet täcker

* Att flytta på sprites
* Att rita med pennan
* Att sända ut meddelanden och lyssna efter events
* Att byta klädsel
* Att sätta begränsningar
* Att skapa och använda booleanska uttryck

###Material

Det här projektet använder sig av material från projektets mapp. Se till att den mappen finns på varje dators skrivbord så att de kan komma åt den.

##Övningar

Steg 1: Dra och rita

Steg 2: Tömma skärmen

Steg 3: Byta färg

Steg 4: Bara måla innanför kanten

Steg 5: Sudda bort

Steg 6: Stämplar

##Utmaningar

1. Regnbågspenna
2. Kortkommandon
3. Stort och litet

##Saker att tänka på

Vissa har rapporterat att de haft svårt att få pennan att rita en jämn linje. Det här beror på att när scenen inte fyller hela skärmen så fångar Scratchmiljön upp att du klickar på och drar en sprite, eftersom den tror att du försöker flytta på den, vilket gör att eventen inte hanteras korrekt av vår kod. (Om du har problem med det här kommer du märka att det hjälper att köra målarprogrammet i fullscreen.)
Lösningen? När du redigerar pennspriten och centrerar klädseln i steg 1, se till att du gör att så att mittpunkten blir på en transparent pixel (t.ex. en punkt precis till vänster och nedåt om pennspetsen). Genom att göra detta ser du till att Scratchmiljön inte fångar upp musdragningen när din kod flyttar spriten till muspekarens position.


