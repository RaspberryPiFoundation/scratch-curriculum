Level 1

#Felix & Herbert

__Introductie:__
We gaan een tikspelletje maken met __Felix de kat__ en __Herbert__ de muis. Je bestuurt Herbert met de muis en moet proberen niet gepakt te worden door Felix. Hoe langer je dat weet vol te houden, des te meer punten je verdient, maar zorg ervoor dat je niet gepakt wordt, want dan raak je punten kwijt!
## STAP 1: Felix volgt de muisaanwijzer
1. Start een nieuw project.
Houd je voortgang in de gaten door de vakjes hieronder af te vinken:
2. Klik op het scherm naast de sprite en open de tab achtergronden, importeer daarna de achtergrond indoors/hall. Verwijder de originele lege achtergrond.
3. Verander de naam van de sprite naar Felix.
4. Zorg ervoor dat Felix alleen naar links en rechts wijst door op deze knop te klikken:
5. Maak dit script aan:

```scratch

    wanneer VLAG wordt aangeklikt
    herhaal
        richt naar muisaanwijzer
        neem 10 stappen
        volgende uiterlijk
        speel slagwerk 62 0.3 tellen
    (einde herhaal)
```
        
###Test Je Project
__Klik op het groene vlaggetje.__
Volgt Felix de muisaanwijzer? Lijkt het alsof hij loopt wanneer hij beweegt? Beweegt hij op de goede snelheid?
Sla je project op
##STAP 2: Felix achtervolgt Herbert
__Nu willen we dat Felix Herbert de muis achtervolgt, in plaats van de muisaanwijzer.__
1. Maak nog een sprite aan door te klikken op de knop een sprite uit een bestand kiezen en animals/mouse1 te selecteren.
2. Verander de naam van de sprite naar Herbert.
3. Wijzig het kostuum en maak het kleiner dan Felix.
Probeer zes keer te klikken op de verkleinknop:
4. Zorg ervoor dat Herbert alleen naar links en rechts wijst. Geef Herbert dit script:

```scratch
    
    wanneer VLAG wordt aangeklikt
    herhaal
        ga naar muisaanwijzer
        richt naar Felix
    (einde herhaal)
```
###Test Je Project
__Klik op het groene vlaggetje.__
Volgt Herbert de muisaanwijzer? Achtervolgt Felix Herbert?
Sla je project op.
##STAP 3: Felix zegt wanneer hij Herbert heeft gevangen
__We willen dat Felix weet wanneer hij Herbert heeft gevangen, en dat hij ons dat vertelt.__

1. Verander Felix’s script naar het volgende:

```scratch
    
    wanneer VLAG wordt aangeklikt
    herhaal
        richt naar muisaanwijzer
        neem 10 stappen
        volgende uiterlijk
        speel slagwerk 62 0.3 tellen
        als raak ik Herbert?
            zeg 1 tellen Gevangen!
        (einde als)
    (einde herhaal)
```

###Test Je Project
__Klik op het groene vlaggetje.__
Zegt Felix wanneer hij Herbert heeft gevangen?
Sla je project op.

##STAP 4:￼Herbert verandert in een geest als hij gevangen is

__In plaats van dat Felix iets zegt, willen we dat Herbert een geest wordt als hij gevangen is.__

1. Verander Felix’s script zodat hij dit bericht stuurt als hij Herbert vangt.

```scratch

    wanneer VLAG wordt aangeklikt
    herhaal
        richt naar muisaanwijzer
        neem 10 stappen
        volgende uiterlijk
        speel slagwerk 62 0.3 tellen
        als raak ik Herbert?
            zend signaal gevangen
            speel slagwerk 58 0.2 tellen
            wacht 1 tellen
        (einde als)
    (einde herhaal)
```
2. Importeer een nieuwe uiterlijk naar Herbert vanuit fantasy/ghost2-a.
3. Wijzig het uiterlijk zodat het kleiner is.
Zes keer klikken op de verkleinknop moet genoeg zijn.
4. Verander de namen van Herbert’s
uiterlijken zodat het uiterlijk van de muis
‘levend’ heet en het uiterlijk van de geest ‘dood’ heet.
5. Maak een nieuw script voor Herbert om een geest van hem te maken:
```scratch
    
    wanneer ik signaal gevangen ontvang
    wissel naar uiterlijk dood
    wacht 0.5 tellen
    wissel naar uiterlijk levend
```
    
###Test Je Project
__Klik op het groene vlaggetje.__
Verandert Herbert in een geest als hij gevangen is?
Maakt Felix de goede geluiden op het goede moment?
Blijft Felix nog lang genoeg stilstaan zodat Herbert kan vluchten?
Sla je project op.
##￼STAP 5: Score bijhouden
__Laten we een score toevoegen zodat we weten hoe goed we zijn in het levend houden van Herbert.
We laten de score bij nul beginnen en verhogen die iedere seconde. Als Felix Herbert pakt, verlagen we de score met honderd.__
1. Maak voor alle sprites een variabele aan die Score heet. Klik op Variabelen in het menu bovenaan, maak een variabele aan en noem die score
2. Maak op het scherm de volgende twee scripts aan
```scratch
    
    wanneer VLAG wordt aangeklikt
    maak score 0
    herhaal
        verander score met 1
        wacht 1 tellen
    (einde herhaal)
    
   wanneer ik signaal gevangen ontvang
   verander score met -100
```
    
###Test Je Project
__Klik op het groene vlaggetje.__
Gaat de score iedere seconde met een omhoog?
Gaat de score met honderd naar beneden als Herbert wordt gevangen?
Wat gebeurt er met de score als Herbert wordt gevangen voordat de score honderd is? Gaat de score terug naar nul als je een nieuw spel start?
Sla je project op.
__Goed gedaan, je bent klaar, je kan nu genieten van het spel!__
Vergeet niet op je spel met al je vrienden en familie te delen door te klikken op __Publiceren__ in de menubalk.