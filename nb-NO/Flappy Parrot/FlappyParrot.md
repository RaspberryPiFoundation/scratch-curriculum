---
title: Flaksefugl
level: Level 2
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

# Introduksjon { .intro}
__I denne oppgaven skal vi lage vår egen versjon av spillet Flappy Bird.__
Trykk på mellomromstasten for å flakse og prøv å styre mellom rørene!

![screenshot](flappy_screenshot.png)

#**Steg 1:** Få Flakse til å falle {.activity}

## Sjekkliste { .check}

+ Start et nytt Scratch-prosjekt. Slett katten ved å høyreklikke den og velge "Slett".
+ Bytt ut bakgrunnen med et utendørslandskap. **desert** er et bra valg.
+ Legg til Flapppy-figuren. Du trenger en figur med drakter for vinger opp og vinger ned. **parrot** er et bra forslag.
+ Bytt navn på figuren til __Flakse__.
+ Gi Flappy dette scriptet:

```blocks
når Grønt flagg klikkes
	gå til x: (-50) y: (0)
	for alltid
		endre y med (-3)
```

## Test prosjektet ditt { .flag}

__klikk det grønne flagget__: starter Flakse midt på skjermen og faller mot bunnen?

## Lagre prosjektet ditt hvis du kan { .save}

#**Steg 2:** Få Flakse til å fly {.activity}

*Nå vil vi at Flakse skal fly oppover når du trykker mellomrom.*

##Sjekkliste { .check}

+ Klikk på __Drakter__ og gi de to draktene navnene **Vinger opp** og **Vinger ned**.
+ Gå tilbake til __Skript__ og legg til dette skriptet:

```blocks
Når [mellomrom] trykkes
	bytt drakt til [Vinger ned]
	gjenta (10) ganger
		endre y med (6)
	end
	bytt drakt til [Vinger opp]
	gjenta (10) ganger
		endre y med (6)
	end
```

## Test prosjektet ditt { .flag}

__Klikk det grønne flagget__: klarer du å kontrollere Flakse med mellomromstasten? La du merke til at noen ganger så flytter ikke Flakse seg når du trykker mellomrom? Det er det neste vi skal fikse.

## Lagre prosjektet ditt { .save}

#**Steg 3:** Gjør kontrollen bedre {.activity}

*Vi vil at Flakse skal reagere hver gang vi trykker mellomrom. Men når vi trykker mellomrom så starter to løkker etterhverandre. Hvis vi trykker mellomrom før disse to løkkene er ferdig så skjer det ikke noe. For å løse dette problemet skal vi bruke en variabel til å telle hvor mange flaks vi trenger å gjøre.*

##Sjekkliste { .check}

+ Ta fra hverandre skriptet som starter med `når mellomrom trykkes` {.blockbrown} og legg de til siden. Vi skal bruke klossene straks.
+ Lag en ny variabel `For denne figuren` {.blockgrey} og kall den `flaks` {.blockorange}.
+ Legg til dette skriptet ved å bruke blokkene du la til siden:

```blocks
når grønt flagg klikkes
	sett [flaks] til [0]
	bytt drakt til [Vinger opp]
	for alltid
		gjenta til <(flaks) = [0]>
			endre [flaks] med (-1)
			bytt drakt til [Vinger ned]
			gjenta (10) ganger
				endre y med (6)
			slutt
			bytt drakt til [Vinger opp]
			gjenta (10) ganger
				endre y med (6)
			slutt

```

+ Til slutt, legg til dette skriptet på `når mellomrom trykkes` {.blockbrown} blokken:

```blocks
når [mellomrom] trykkes
	endre [flaks] med (1)
```

## Test prosjektet{ .flag}

__Klikk det grønne flagget__: Flakser Flakse en gang for hver gang du trykker mellomrom??

## Lagre prosjektet ditt om det trengs { .save}

#**Steg 4:** Legg til rørene {.activity}

*Vi vil legge til noen hindringer som Flakse kan fly igjennom.*

##Sjekkliste { .check}

+ Klikk på `tegn ny figur` {.blockgrey} knappen.
+ Gi den nye figuren navnet **rør**.
+ Hvis drakten er i `Punktgrafikk` {.blockgrey} klikk på `Bytt til vektorgrafikk` {.blockgrey} knappen.
+ Klikk på `Zoom -` {.blockgrey} så du kan se hele tegneområdet.
+ Klikk på `Rektangel` {.blockgrey}, velg en farge og klikk på `Fylt rektangel` {.blockgrey} knappen nederst til venstre.
+ Klikk og dra to bokser, en fra toppen og en fr bunn i midten av tegneflaten. Det skal se sånn ut:

![screenshot](pipe_design.png)
 
+ Du kan skyggelegge røra ved å klikke på `Fyll farge` {.blockgrey} og klikke på en av skyggemetodene i firkantene nede til venstre. Velg to varianter av samme farge: en for forgrunnen og en for bakgrunnen. Når du klikker på en firkant med fylleverktøyet får du en fin effekt.
+ Gi figuren navnet **Rør**.

## Lagre prosjektet ditt { .save}

#**Steg 5:** Få røra til å bevege seg{.activity}

*Nå skal vi få røra til å flytte seg og gjøre plasseringen tilfeldig slik at vi får en hinderløype til Flakse.*

##Sjekkliste { .check}

+ Klikk på **rør**-figuren og velg `Skript` {.blockgrey}.
+ Legg til dette skriptet:

```blocks
når grønt flagg klikkes
	skjul
	sett størrelse til (200)%
	for alltid
		lag klon av [meg]
		vent (2) sekunder

når jeg starter som klon
	gå til x: (240) y: (tilfeldig tall fra(-80) til (80))
	vis
	gjenta (120) ganger
		endre x med (-4)
	slutt
	slett denne klonen
```

## Test prosjektet { .flag}

__Klikk det grønne flagget__: Kommer det mange rør flygende mot Flakse? Har rørene åpninger til å fly gjennom? Om du synes det er vanskelig å fly Flakse gjennom åpningene kan du endre på åpningen mellom rørene med tegneverktøyet, eller du kan lage Flakse mindre.

## Lagre prosjektet { .save}

#**Steg 6:** Finn ut om Flakse kræsjer med rørene {.activity}

*For at spillet skal bli vanskelig må spilleren styre Flakse gjennom åpningene mellom rørene uten å komme borti hverken rør eller kanten av skjermen. Vi skal legge til noen blokker for å merke om Flakse kræsjer.*

##Sjekkliste { .check}

+ Vi legger til en lyd som vi kan spille når Flakse kræsjer. Kliukk på **Flakse** og så på `Lyder` {.blockgrey}.
+ Klikk på `Velg lyd fra biblioteket` {.blockgrey}.
+ Velg en kræsjelyd for **Flakse**.  **screech** er en kul lyd.
+ Klikk deg tilbake til `Skript` {.blockgrey} fliken.
+ Legg til dette skriptet:

```blocks
når grønt flagg klikkes
	vent til ((berører [kant]?) eller (berører [Rør]?))
	spill lyden [screech v]
	si [Du tapte!]
	send melding [Tap]
	stopp [andre skript i figuren]
```

+ Klikk på **Rør** og legg til dette skriptet:

```blocks
når jeg mottar [Tap]
	stopp [andre skript i figuren]
```

## Test prosjektet ditt { .flag}

__Klikk det grønne flagget__: Stopper spillet når Flakse kommer borti et rør eller kanten av brettet?

## Lagre prosjektet ditt { .save}

#**Steg 7:** Legg til poeng {.activity}

*Spilleren skal score ett poeng hver gang Flakse flyr gjennom en røråpning.*

##Sjekkliste { .check}

+ Vi legger til en lyd hver gang Flakse scorer ett poeng. Klikk på **Rør** og legg til en lyd. **bird** er et lurt valg.
+ Gå tilbake til `Skript` {.blockgrey} .
+ Lag en ny variabel `for alle figurer` {.blockgrey} og kall den `poeng` {.blockorange}.
+ Legg til et skript som setter poengene til 0 når det grønne flagget klikkes.
+ Legg til dette skriptet:

```blocks
når jeg starter som klon
	vent til <(x posisjon) < ([x posisjon] av [Flakse])>
	endre [poeng] med (1)
	spill lyden [bird]
```

## Test prosjektet ditt { .flag}

__Klikk det grønne flagget__: scorer du poeng når Flakse flyr forbi en åpning mellom rørene?

## Lagre prosjektet ditt { .save}

##Ting du kan prøve{ .try}
1. __Kan du lage dette spillet lettere eller vanskeligere?__
2. __Supert, du har laga ferdig spillet i sin enkleste form. Her er noen flere ting du kan prøve:__

##Utfordring 1: legg til rekorder { .challenge}

+ Lag en ny variabel og klikk `Nett variabel (lagret på nett)` {.blockgrey} boksen. Kall variabelen `Rekord` {.blockorange}
+ når spillet er ferdig må du sjekke om det er en ny rekord:

```blocks
når jeg mottar [Tap]
	hvis <(poeng) > (rekord)> 
		sett [rekord] til (poeng)
	slutt
	stopp [andre skript i figuren]
```

##Test prosjektet { .flag}
__Klikk det grønne flagget__: Oppdaterer rekorden seg for hver gang du setter ny rekord?

##Lagre prosjektet ditt { .save}

##Utfordring 2: legg til tyngdekraft { .challenge}

Når noe faller på grunn avtyngdekraft øker farten jo lenger fallet varer. Vi skal prøve å etterligne denne måten å falle på.

+ Legg til en ny variabel `for denne figuren` {.blockgrey} for **Flakse** og kall den `løft` {.blockorange}.
+ Endre Flakses falleskript:

```blocks
når grønt flagg klikkes
	sett [løft] til [0]
	gå til x: (-50) y: (0)
	for alltid
		endre y med (løft)
		endre [løft] med (-0.4)
```

+ og endre Flakses flakseskript:

```blocks
når grønt flagg klikkes
	sett [flaks] til [0]
	bytt drakt til [vinger opp]
	for alltid
		gjenta til <(flaks) = [0]>
			endre [flaks] med (-1)
			bytt drakt til [vinger ned]
			endre [løft] med (8)
			vent (0.2) sekunder
			bytt drakt til [vinger opp]
			vent (0.2) sekunder
```

##Test prosjektet ditt { .flag}
__Klikk det grønne flagget__: detter Flakse fortere jo lenger han detter?

##Lagre prosjektet ditt { .save}

##Utfordring 3: dett ut av skjermen { .challenge}

Når spilleren taper skal Flakse dette ned og ut av skjermen.

+ Bytt ut `send meldingen Tap` {.blockbrown}  blokka med `send meldingen fall` {.blockbrown}
+ Legg til dett eskriptet:

```blocks
når jeg mottar [Fall]
	gjenta (10) ganger
		vend høyre (5) grader

når jeg mottar [Fall]
	gjenta til <(y posisjon) < [-180]>
		endre y med (løft)
		endre [løft] med (-0.4)
	slutt
	skjul
	send melding [Tap]
```

+ ikke glem å legge til en `vis` {.blockpurple}-blokk og sett Flakses retning når spillet starter på nytt.

##Test prosjektet ditt { .flag}
__Klikk det grønne flagget__: detter Flakse ut av skjermen når han treffer et rør? Flyr Flakse riktig vei når spillet starter igjen?

##Lagre prosjektet ditt { .save}

__Gratulerer, du er ferdig med spillet! Hva er rekorden din?__
ikke glem å dele spillet med vennene dine. Trykk på __Legg ut__ for at andre skal få prøve!


