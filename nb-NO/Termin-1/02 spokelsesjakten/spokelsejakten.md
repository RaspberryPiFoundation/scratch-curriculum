---
title: Spøkelsesjakten
level: 1
language: nb-NO
embeds: ["*.png"]
...

# Introduksjon { .intro}

Dette prosjektet er inspirert av tivolispillet __Whack-a-mole__, hvor man slår muldvarper ned igjen i hullene sine. I vårt spill er det spøkelsene som blir borte når vi klikker på dem. Målet er å klikke bort flest mulig i løpet av 30 sekunder.


![skjermbilde](tre_spoekelser_screenshot.png)


|Sjekkliste| Følg instruksjonene på lista. Huk av etter hvert|
|---|-----|
|**Test**| **Klikk på det grønne flagget for å teste koden**|
|**Lagre**| **Husk å lagre koden når du har lagt til noe nytt**|

# Steg 1: Lag et flyvende spøkelse { .activity}

## Sjekkliste { .check}

+ __Start et nytt Scratch-prosjekt__.
+ __Slett kattefiguren__ ved å høyreklikke på den og velge 'slett'
+ Endre bakgrunnen til __Natur/woods__.
+ For å legge til et spøkelse klikker du på ´figur fra bibliotek´-knappen. Velg __Fantasi/Ghost1__-figuren.
+ Gi spøkelset navnet __spøkelse1__.

Du skal nå __lage en variabel__ som styrer hvor fort spøkelset beveger seg. Denne kan vi senere bruke til å endre hastigheten når spillet er i gang.

+ Under ´Skript´, trykk på ´Data´ og så ´Lag en variabel´. Kall den __hastighet__. Huk av der det står ´For denne figuren´.
+ På scenen skal variabelen hete __spøkelse1: hastighet__. Hvis den bare heter __hastighet__, så slett den og legg den til en gang til.  
+ Fjern avhukingen ved siden av variabelen, slik at den ikke vises på scenen: ![](hastighet.png)
+ Vi vil at spøkelset skal bevege seg når spillet starter. Det gjør vi ved å lage følgende skript:

```blocks
	Når grønt flagg klikkes
		sett [hastighet v] til (5)
		for alltid
		gå (hastighet) steg
```

## Test Prosjektet { .flag}

__Klikk på det grønne flagget__. Hvorfor sitter spøkelset fast når det treffer kanten på skjermen?

## Sjekkliste { .check}

+ For å unngå at spøkelset sitter fast i veggen må vi få det til å snu når det treffer den. Dette gjøres ved å legge til blokken ´sprett tilbake ved kanten´. Skriptet ser da slik ut:

	```blocks
	Når grønt flagg klikkes
		sett [hastighet v] til (5)
		for alltid
			gå (hastighet) steg
			sprett tilbake ved kanten
	```

+ For å hindre at spøkelset snur seg opp-ned, klikk på ![venstre/høyre](kun-mot-venstre-eller-hoyre.png)-knappen i spøkelsets infoboks. 

## Test prosjektet{ .flag}

__Klikk på det grønne flagget__.

## Lagre prosjektet { .save}

## Ting å prøve { .try}

+ __Endre hastighetsvariabelen__, slik at spøkelset går raskere eller saktere.
+ Hvordan kan vi få spøkelset til å __fly fortere jo lenger det flyr?__ (Dette er nokså vanskelig, så ikke vær bekymret hvis du ikke skjønner hvordan. Du vil få flere hint underveis.)

# Steg 2: Få spøkelset til å dukke opp og forsvinne { .activity}

__For å gjøre spillet morsommere vil vi få spøkelset til å dukke opp og forsvinne.__ 

## Sjekkliste { .check}

+ Vi lager et nytt skript, som skal kjøre samtidig med skriptet som beveger på spøkelset. Det nye skriptet __gjemmer bort spøkelset en tilfeldig periode__ og __viser det deretter frem igjen i en tilfeldig periode__. Dette skal skje om og om igjen, frem til spillet er slutt. Slik lager du skriptet:

```blocks
	Når grønt flagg klikkes
	for alltid
		skjul
		vent (tilfeldig tall fra (2) til (5)) sekunder
		vis
		vent (tilfeldig tall fra (3) til (5)) sekunder
```

## Test prosjektet { .flag}

__Klikk på det grønne flagget__. Flytter spøkelset seg fra side til side? Forsvinner det og dukker opp igjen helt tilfeldig? Da er alt riktig.

## Lagre prosjektet { .save}

## Ting å prøve { .try}

+ Prøv å __endre tallene i koden__ der det står ```tilfeldig tall fra ( ) til ( )```. Hva skjer hvis du velger veldig store eller små tall? (Dette gir deg kanskje et nytt hint for hvordan vi skal få spøkelset til å gå fortere jo lenger man spiller.)

# Steg 3: Tryll bort spøkelset med et klikk! { .activity}

__For å gjøre dette til et ordentlig spill må vi gi spilleren noe å gjøre - for eksempel å klikke bort spøkelset. Når det skjer vil vi også at det skal komme en stilig tryllelyd!__

## Sjekkliste { .check}

+ Fra ´Lyd´-boksen henter du lyden __Elektronisk/fairydust__.
+ Så lager du skriptet som får __spøkelset til å forsvinne__ når det blir klikket på:

```blocks
	når denne figuren klikkes
		skjul
		spill lyden [fairydust v]
```
  
## Test prosjektet { .flag}

__Klikk på det grønne flagget__. Forsvinner spøkelset med en tryllelyd når du klikker på det? 

## Lagre prosjektet {.save}

## Ting å prøve { .try}

+ Spør hjelperen din om du kan ta opp en egen lyd. Denne kan brukes istedenfor tryllelyden.

# Steg 4: Legg til tid og poeng { .activity}

__Vi har et spøkelse å trylle bort, så nå vil vi ha poeng for å gjøre det! Vi vil også ha en tidsfrist, slik at det er om å gjøre å få flest mulig poeng på denne tiden. Vi løser begge deler ved å bruke variabler.__

## Sjekkliste { .check}

+ Lag en ny variabel som heter __poeng__. Denne skal gjelde for alle figurer. Legg til en ny blokk som gjør at __poengvariabelen økes__ med 1 poeng for hver gang spilleren klikker på spøkelset.

```blocks
	når denne figuren klikkes
		skjul
		spill lyden [fairydust v]
		endre [poeng v] med (1)
```

+ Klikk på 'Scene' og lag en ny variabel som heter __tid__. La variablen vises på skjermen. 
+ Lag et nytt skript som setter ´tid´-variabelen til __30__ og ´poeng´-variablen til __0__ når det grønne flagget klikkes. 
+ Bruk så en ´gjenta til < >´-blokk for å vente i __1__ sekund og deretter redusere tiden med 1 sekund. Denne skal kjøre fram til tiden er ute. Til slutt stopper du hele spillet med en ´stopp alle´-blokk.

```blocks   
	Når grønt flagg klikkes
	sett [tid v] til (30)
	sett [poeng v] til (0)
	gjenta til ((tid) = (0))
		vent (1) sekunder
		endre [tid v] med (-1)
        slutt
	stop [alle v]
```

## Test prosjektet { .flag}

## Lagre prosjektet { .save}

## Ting å prøve { .try}

+ Hvordan kan du få spøkelset til å gå fortere når spillet er i gang?
+ __Bra jobba!__. Nå er du egentlig ferdig med spillet, men prøv deg gjerne på neste steg også.

## En ekstra utfordring: Flere spøkelser! { .challenge}

Hvis ett spøkelse er bra, må vel flere være enda bedre! La oss ha tre spøkelser flyvende rundt! 

+ __Lag flere spøkelser__ ved å høyreklikke på den du allerede har, og så kopiere denne.
+ __La spøkelsene få ulik størrelse__. Dette gjør du ved først å klikke på ´Drakter´, og så én av knappene under. Den til venstre forstørrer figuren og den til høyre forminsker:![](endre-storrelse.png)
+ Du kan også __endre spøkelsenes flyvefart__. Dette gjøres i ´hastighet´-variabelen i det øverste skriptet for hver enkelt figur.
+ Til slutt kan du __spre spøkelsene__ litt bedre ut på scenen. Dette gjør du ved å klikke og dra figurene rundt i selve skjermbildet.

## Test prosjektet { .test}

+__Klikk på det grønne flagget.__ Har du nå tre spøkelser som flyr fra side til side? Som plutselig forsvinner og dukker opp igjen? Forsvinner når du klikker på dem?
Gratulerer! Da har du gjort alt riktig!

## Lagre prosjektet { .save}

## Ting å prøve { .try}

+ Hvor mange spøkelser synes du spillet fungerer best med? __Legg til flere__ og prøv!
+ Klarer du å få spøkelsene til __å se forskjellige ut__? Klikk på 'Drakter' og prøv deg frem. Du kan også velge noen av blokkene under 'Utseende'.
+ Kan du få spøkelsene til __å bli verdt forskjellige antall poeng?__ Hva med å få den minste og raskeste til å gi 10 poeng?

Bra jobba! Nå er du ferdig, og det er på tide med litt seriøs spilling. Husk også at du kan dele spillet med vennene dine. Det gjør du ved å klikke på ´Legg ut´ i toppmenyen.