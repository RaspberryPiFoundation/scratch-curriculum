Niveau 1

#Gëff der Hex eng op den Deckel

__Aleedung:__
Bäi dësem Spill geet et drëms op all d'Hexen ze klicken, déi um Bildschierm optauchen. Wat s du méi Hexen ewechklicks, wat s du méi Punkte kriss. D'Zil ass et, fir esou vill wéi méiglech Punkten an 30 Sekonnen ze sammelen!

##￼1 SCHRATT: Erstell eng fléiend Hex
1. Fänk en neie Projet un.
2. Huel d'Kazefigur ewech an ersetz den Hannergrond mam Bild _woods_ aus der Bibliothéik an der Kategorie _Natur_.
3. Benotz de Knäppchen _Figur aus der Bibliothek laden_ fir eng Hex an däi Projet eran ze huelen (Benotz d'Figur _Witch_ an der Kategorie _Fantasie_).
Elo brénge mir eis Hex un d'Beweegen.
4. Setz eng Variabel nëmme fir des Figur dobäi an nenn se _Geschwindigkeit_.
Op der Bühn sollt elo "Sprite1 Geschwindigkeit" stoen. Wann do just "Geschwindigkeit" steet, da läsch dës Variabel an erstell se nach eng Kéier, dës Kéier _Nur für diese Figur_ uklicken.
Klick dann de Krop virum Numm vun der Variabel an der Variabel-Lëscht ewech, esou dass d'Variabel net méi op der Bühn ugewise gëtt.
Dës Variabel kontrolléiert, wéi séier dass d'Hex sech beweegt. Mir benotzen eng Variabel, fir dass mir während dem Spill d'Geschwindegkeet, mat där se sech beweegt, verännere kënnen.
5. Esoubal d'Spill ufänkt soll d'Hex och ufänken sech ze beweegen. Benotz dofir dëse Skript:

```scratch
    Wenn FLAG angeklickt
    setze Geschwindigkeit auf 5
    wiederhole fortlaufend
        gehe Geschwindigkeit-Schritt
    (Ende wiederhole fortlaufend)
```

###Test däi Projet
__Klick op de grénge Fändel__ a kuck wat d'Hex mëscht. Firwat bleift se um Bord vun der Bühn hänken?
6. Fir dass d'Hex net méi hänke bleift, musse mir se dozou bréngen d'Kéier ze man, esoubal se de Bord beréiert. Setz dofir en _pralle vom Rand ab_ Block ënnert de Block _gehe Geschwindigkeit er-Schritt_.

```scratch
    Wenn FLAG angeklickt
    setze Geschwindigkeit auf 5
    wiederhole fortlaufend
        gehe Geschwindigkeit-Schritt
        pralle vom Rand ab
    (Ende wiederhole fortlaufend)
```

7. Fir dass d'Hex net d'ënnescht-iewescht flitt, klick op den entspriechenden __Drehmodus__ am Informatiouns-Beräich vun der Figur.

###Test däi Projet
__Klick op de grénge Fändel__
Beweegt sech d'Hex vun engem Bord vun der Bühn zum aneren?

Späicher däi Projet

###Saache fir ze probéieren
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼__Veränner de Wäert vun der _Geschwindigkeit_ Variabel fir d'Hex méi séier oder méi lues fléien ze loossen.__

__Wat kéint ee maachen, fir dass d'Hex vum selwen ëmmer méi séier gëtt?__
(Dat ass guer net esou einfach. Maach dir näischt draus, wann s du dat net direkt eraus fënns. Am Laf vum Projet gi mir dir nach e puer Tipps.)

##2. SCHRATT: Looss d'Hex zoufälleg verschwannen an optauchen
Fir d'Spill méi spannend ze maachen, soll d'Hex zoufälleg verschwannen an erëm optauchen. Dat maache mir mat engem zweete Skript dee parallel zum éischte leeft, deen d'Hex beweegt. Den neie Skript soll d'Hex fir eng zoufälleg laang Zäit verstoppen, se da fir eng zoufälleg laang Zäit erëm uweisen, an dat onendlech widderhuelen (op d'mannst bis dass d'Spill eriwwer ass).
Erstell dëse Skript fir d'Hex:
```scratch
    Wenn FLAG angeklickt
    wiederhole fortlaufend
        verstecke dich
        warte Zufallszahl von 2 bis 5 Sek.
        zeige dich
        warte Zufallszahl von 3 bis 5 Sek.
    (Ende wiederhole fortlaufend)
```
###Test däi Projet
__Klick op der grénge Fändel.__
Beweegt sech d'Hex vu Bord zu Bord vun der Bühn a verschwënnt oder weist sech dobäi nom Zoufallsprinzip?

Späicher däi Projet

###Saache fir ze probéieren
__Probéier d'Wäerter am Zufallszahlengenerator ze veränneren. Wat geschitt wann s du ganz kleng oder ganz grouss Zuelen hëls?__
(Vläit hëlleft dat dir, eraus ze fannen, wéi s du d'Hex méi séier gi loosse kanns, wat d'Spill méi laang amgaangen ass?)

##￼3. SCHRATT: Looss d'Hex verschwannen, wann s du drop klicks
Fir dass dëst wierklech e Spill gëtt, musse mir natierlech dem Spiller eppes ze di ginn. De Spiller muss op d'Hex klicke, fir se verschwannen ze dinn. Wann op d'Hex geklickt gouf, soll se verschwannen an e Geräich vu sech ginn.
1. Importéier (Klang aus der Bibliothek wählen) am Tab _Klänge_ d'Geräisch _fairydust_ aus dem Beräich _Elektronik_.
2. Setz dëse Script bäi d'Hex dobäi (niewt déi zwee aner):
```scratch
    Wenn Sprite1 angeklickt
    verstecke dich
    spiele Klang Fairydust
```
###Test däi Projet
__Klick op de grénge Fändel.__
Mëscht d'Hex e Geräisch a verschwënnt, wann s du op si klicks?
Späicher däi Projet
##4. SCHRATT: Punkten zielen an Zäit stoppen
Lo hu mir eng Hex, mä mir wollten dach e Spill maachen! All Kéiers wa mir op d'Hex klicke wëlle mir Punkte bäi kréie, mä mir wëllen awer och, dass d'Spill no enger gewëssen Zäit eriwwer ass.

1. Erstell en nei Variabel fir all Figuren an nenn se _Punkten_. Veränner de läschte Skript vun der Hex esou, dass d'Punkten, all Kéiers wou op si geklickt gëtt, ëm 1 an d'Lut ginn.
```scratch
    Wenn Sprite1 angeklickt
    verstecke dich
    spiele Klang Fairydust
    ändere Punkten um 1
```

2. Wiel d'Bühn un an erstell eng nei Variabel déi s du _Stoppuhr_ nenns.
Setz en neie Skript dobäi, deen duerch d'Klicke vum grénge Fändel ausgeléist gëtt, d'Variabel _Stoppuhr_ op 30 setzt a _Punkte_ op 0. Benotz e _wiederhole bis_ Block fir all Kéiers no enger Sekonn d'Variabel _Zeit_ ëm 1 erof ze setzen. Wann d'Stoppauer ofgelaf ass stoppe mir d'Spill mat _stoppe alles_.
```scratch
    Wenn FLAG angeklickt
    setze Stoppuhr auf 30
    setze Punkten auf 0
    wiederhole bis Stoppuhr = 0
        warte 1 Sek.
        ändere Stoppuhr um -1
    (Ende wiederhole)
    stoppe alles
```


###Test däi Projet
__Klick op de grénge Fändel.__
Späicher däi Projet

###Saache fir ze probéieren
__Wéi kéints du d'Hex méi séier gi loosse wat d'Spill méi laang dauert?__

__Däi Spill ass fäerdeg, gutt gemaacht! Du kanns däi Spill allerdéngs nach e bëssen ausbaue wann s du wëlls. Hei sinn e puer Erausfuerderungen!__
##Erausfuederung: Méi wéi eng Hex
Wat méi Hexe wat besser! Komm mir loossen dräi Hexen doruechter fléien.
1. Klon deng Hex andeems du mat der rietser Maustast op déi éischt klicks an _Duplizieren_ auswiels. Maach dat zwee Mol.
2. Zéi d'Hexe mat denger Maus op ennerschiddlech Plazen op der Bühn, esou dass se net all hannertenee fléien.
3. Änner d'Gréisst vun all Hex, esou dass se allen dräi verschidde Gréissten hunn (z.B. déi ënnen am gréissten an déi uewen am klengsten).
4. Änner bei all Hex d'Variabel _Geschwindigkeit_, esou dass se ënnerschiddlech schnell fléien
###Test däi Projet
__Klick op de grénge Fändel.__
Sinn op denger Bühn elo dräi ënnerschiddlech grouss a schnell Hexen, déi vu Bord zu Bord fléien, zoufälleg verschwannen an erëm optauchen, a verschwanne wann s du op si klicks?
Späicher däi Projet
###Saache fir ze probéieren
1. Mat wéi villen Hexen ass d'Spill am flottsten?
￼￼2. Kanns du d'Hexen anescht ausgesi loossen? Du kéints z.B. hier Kostümer veränneren, oder Bléck aus der _Aussehen_ Palett benotzen.
3. Kanns du maachen, dass d'Hexen ënnerschiddlech vill Punkte wäert sinn? Du kéints z.B. 10 Punkten op déi schnellst (a klengst) Hex setzen.

__Bravo! Elo bass du fäerdeg an du kanns dech mat dengem neie Spill ameséiren!__
Vergiess net, dass du däi Spill all denge Kollegen an denger Famill weise kanns. Klick dozou op __Veröffentlichen!__ ganz uewen am Menü.