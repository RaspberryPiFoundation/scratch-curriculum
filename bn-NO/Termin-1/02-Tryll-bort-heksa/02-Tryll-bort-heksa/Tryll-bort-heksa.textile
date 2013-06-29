h1(nivaa1). Tryll bort heksa

h2. Introduksjon

p(intro). Dette prosjektet er inspirert av tivolispillet _whack-a-mole_, 	hvor man slår muldvarper ned igjen i hullene sine. I vårt spill er det heksene som blir borte når vi klikker på dem. Målet er å trylle bort flest mulig i løpet av 30 sekunder.


!(skjermbilde). skjermbilde-tre-hekser.png!


table(oversikt).
| %(sjekkliste)Sjekkliste%| Følg instruksjonene på lista. Huk av etter hvert.|
| %(test)Test%| Klikk på det grønne flagget for å teste koden.|
| %(lagre)Lagre%| Husk å lagre koden når du har lagt til noe nytt.|

h4(steg). Steg 1: Lag en flyvende heks

%(sjekkliste)Sjekkliste%

(x)# *Start et nytt Scratch-prosjekt*.
# *Slett kattefiguren* ved å høyreklikke på den og velge %(klikk)Slett%.<br>
*Riktig bakgrunn* får du ved å velge %(klikk)Scene%, trykke på %(klikk)Bakgrunner% og deretter %(klikk)Importere%. Velg bakgrunnen %(klikk)woods%, som ligger i %(klikk)Nature%-mappen.
# For å *legge til en heks* klikker du på %(klikk)Hent en ny figur fra fil%-knappen: !(systemdetalj). hent-en-ny-figur-fra-fil.png!
*Riktig drakt* får du ved å klikke på %(klikk)Drakter%, og deretter %(klikk)Importere% %(klikk)witch1%-kostymet, som ligger i %(klikk)Fantasy%-mappen. 
# Du skal nå *lage en variabel som styrer hvor fort heksa beveger seg*. Denne kan vi senere bruke til å endre hastigheten når spillet er i gang.
Klikk på %(klikk)Variabler% og deretter %(klikk)Lag en ny variabel%. Kall den _hastighet_. Huk av der det står _Bare for denne figuren_.
På scenen skal variabelen hete _Figur1: hastighet_. Hvis den bare heter _hastighet_ så slett den og legg den til en gang til.  
%(klikk)Fjern avhukingen% ved siden av variabelen, slik at den ikke blir med på scenen. !(systemdetalj). hastighet.png!
# Vi vil at *heksa skal bevege seg* når spillet starter. Det gjør vi ved å lage følgende skript:
!(skript). skript-1a.png!

%(test)Test prosjektet%

(x)#6 *Klikk på det grønne flagget*. Se hva heksa gjør. Blir hun fanget ved kanten av scenen? For å unngå det må vi få henne til *å gå tilbake* når hun treffer den. Dette gjøres ved å legge til blokken %(bevegelse)sprett tilbake ved kanten%  under %(bevegelse)gå% %(variabel)hastighet% %(bevegelse)steg%. Skriptet ser da slik ut:<br>!(skript). skript-1b.png!
# For å *hindre at hun snur seg opp-ned*, klikk på %(klikk)kun mot venstre eller høyre%-knappen i %(klikk)Figur%-boksen. Den ser slik ut: !(systemdetalj). kun-mot-venstre-eller-hoyre.png!

%(lagre)Lagre prosjektet%

%(prove)Ting å prøve%

(x)#8 Endre hastighetsvariabelen, slik at *heksa går raskere eller saktere*.
# Hvordan kan vi få heksa til å *gå fortere jo lenger hun flyr*? Dette er nokså vanskelig, så ikke være bekymret hvis du ikke skjønner hvordan. Du vil få flere hint underveis.

h4(steg). Steg 2: Få heksa til å dukke opp og forsvinne

p(intro). For å gjøre spillet mer gøy vil vi få heksa til å dukke opp og forsvinne. 

%(sjekkliste)Sjekkliste%

(x)# Vi lager et nytt skript, som skal kjøre samtidig med skriptet som beveger på heksa. Det nye skriptet *gjemmer bort heksa en tilfeldig periode*, og *viser henne deretter frem igjen i en tilfeldig periode*. Dette skal skje *om og om igjen*, frem til spillet er slutt. Slik lager du skriptet:<br>!(skript). skript-2.png! 

%(test)Test prosjektet%

(x)#2 *Klikk på det grønne flagget*. Flytter heksa fra side til side? Forsvinner hun og dukker opp igjen helt tilfeldig? Da er alt riktig.

%(lagre)Lagre prosjektet%


%(prove)Ting å prøve%

(x)#3 Prøv å *endre tallene i koden* der det står: %(operator)tilfeldig tall [  ] fra [  ]% %(operator)til% &nbsp; %(variabel)sekunder%. Hva skjer hvis du velger veldig store eller små tall? Dette gir deg kanskje et nytt hint for hvordan vi skal få heksa til å gå fortere jo lenger man spiller.

h4(steg). Steg 3: Tryll bort heksa med et klikk!

p(intro). For å gjøre dette til et ordentlig spill må vi gi spilleren noe å gjøre - for eksempel å trylle bort heksa. Når det skjer vil vi også at det skal komme en stilig tryllelyd!

%(sjekkliste)Sjekkliste%

(x)# Fra %(klikk)Lyd%-boksen henter du lyden %(klikk)Electronic/Fairydust%.
# Så lager du skriptet som får *heksa til å forsvinne* når hun blir klikket på:

!(skript). skript-3a.png!

%(test)Test prosjektet%

(x)#3 Klikk på det grønne flagget. Forsvinner heksa med en tryllelyd når du klikker på henne? 

%(lagre)Lagre prosjektet%

%(prove)Ting å prøve%

(x)#4 Spør hjelperen din om du kan ta opp en egen lyd. Denne kan brukes istedenfor tryllelyden.

h4(steg). Steg 4: Legg til tid og poeng

p(intro). Vi har en heks å trylle bort, så nå vil vi ha _poeng_ for å gjøre det! Vi vil også ha en _tidsfrist_, slik at det er om å gjøre å få flest mulig poeng på denne tiden. Vi løser begge deler ved å bruke variabler.

%(sjekkliste)Sjekkliste%

(x)# Lag en ny %(klikk)variabel% som heter _poeng_. Denne skal gjelde %(klikk)for alle figurer%. Legg til en ny blokk som gjør at *poengvariabelen økes* med 1 poeng, for hver gang spilleren klikker på heksa.
!(skript). skript-3b.png!
# Bytt til %(klikk)Scene% og lag en ny variabel som heter _tid_. Velg %(klikk)vis på scenen% og %(klikk)bare for denne figuren%. 
Lag et nytt skript som kjører når det grønne flagget klikkes. Legg inn følgende blokker:<br> %(variabel)sett tid til% 30 (sekunder)<br> %(variabel)sett tid til%  0
Bruk så en %(styring)gjenta til% -blokk %(styring)for å vente% 1 %(styring)sekunder% og deretter redusere tiden med 1 sekund ( %(variabel)endre tid med% -1 ). Denne skal kjøre fram til tiden er ute ( %(operator)tid = 0% ). <br>Til slutt stopper du hele spillet med en %(styring)stopp alle% -blokk.<br>!(skript). skript-4.png!

%(test)Test prosjektet%

%(lagre)Lagre prosjektet%

%(prove)Ting å prøve%

(x)#3 Hvordan får du heksa til å gå fortere når spillet er i gang?

p(utro). Bra jobba! Nå er du egentlig ferdig med spillet, men prøv deg gjerne på neste steg også.

h4(utfordring). En ekstra utfordring: Flere hekser!

p(intro). Hvis én heks er bra, må vel flere være bedre! La oss ha tre hekser flyvende rundt! 

(x)# *Lag flere hekser* ved å %(klikk)høyreklikke% på den du allerede har, og så %(klikk)kopiere% denne:<br>!(systemutsnitt). lag-kopi.png!
# *La heksene få ulik størrelse*. Dette gjør du ved først å klikke på %(klikk)Drakter% og deretter %(klikk)Rediger%. Velg så én av knappene under. Den til venstre forstørrer figuren og den til høyre forminsker:!(systemdetalj). endre-storrelse.png!
# Du kan også *endre heksenes flyvefart*. Dette gjøres i  %(variabel)hastighet%-variabelen i det øverste skriptet for hver enkelt figur.
# For at nedtellingen skal gå i riktig tempo må det nederste skriptet (det som teller ned sekunder) slettes fra to av figurene.
# Til slutt kan du *spre heksene* litt bedre ut på scenen. Dette gjør du ved å klikke og dra figurene rundt i selve skjermbildet.

%(test)Test prosjektet%

(x)#6 *Klikk på det grønne flagget.* Har du nå tre hekser som: <br>1. flyr fra side til side?<br>2. plutselig forsvinner og dukker opp igjen?<br>3. forsvinner når du klikker på dem?
Gratulerer! Da har du gjort alt riktig!

%(lagre)Lagre prosjektet%

%(prove)Ting å prøve%

(x)#7 Hvor mange hekser synes du spillet fungerer best med? *Legg til flere* og prøv!
# Klarer du å få heksene til *å se forskjellige ut*? Klikk på %(klikk)Drakter% og prøv deg frem. Du kan også velge noen av blokkene under %(klikk)Utseende%.
# Kan du få heksene til *å bli verdt forskjellige poenger*? Hva med å få den minste og raskeste til å gi 10 poeng?

p(utro). Bra jobba! Nå er du ferdig, og det er på tide med litt seriøs spilling.<br>Husk også at du kan dele spillet med vennene dine. Det gjør du ved å klikke på %(klikk)Legg ut% i toppmenyen.


