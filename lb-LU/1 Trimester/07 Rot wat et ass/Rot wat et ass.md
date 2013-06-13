Level 3

#Rod wat et ass

__Aleedung__.
Op der Tafel gëtt en zoufällegen Objet gewisen, ganz verzerrt. Du muss rode wat et ass, andeems du ënnen op e Bild klicks. Wat s du méi séier réids, wat s du méi Punkte kriss!

## 1. SCHRATT: Looss verschidde Saachen op der Tafel optauchen

Mir wëlle verschidde Biller op der Tafel uweisen.

1. Fänk en neie Scratch Projet un a läsch d'Kaze-Figur.
2. Klick op d'Bühn an dann op den Tab mat den Hannergrënn. Importéier den Hannergrond _chalkboard_ aus der Kategorie _Drinnen_.
3. Importéier eng nei Figur a mol hir e Kostüm deen dir gutt  gefällt. Am beschten du importéiers eppes aus der Kategorie _Dinge_.
4. Zéi d'Figur an d'Mëtt vun der Tafel. Maach se méi grouss oder méi kleng, esou dass se gutt passt.
5. Klick op den Tab _Kostümer_ an importéier nach 4 aner Saachen déi dir gefalen.
6. Stell dëse Skript op:

```scratch
    when FLAG clicked
    repeat pick random 1 to 5       
        next costume
    (end repeat)
```

###Test däi Projet
__Klick op de grénge Fändel.__

Wiesselt deng Figur de Kostüm?

__Klick nach e puer mol op de grénge Fändel.__
Kriss du all Kéiers en anere Kostüm? Heiansdo kriss du den nämlechte Kostüm zwee mol hannerteneen, mä dat mëscht näischt. Du gesäis vläit och datt deng Figur dobei flackert. Dat flécke mir am nächste Schratt.

Späicher däi Projet

2. SCHRATT: Verzerr d'Biller

__Looss eis elo d'Bild verzerre wann et optaucht, an da lues a lues méi kloer ginn.__
Mir benotzen eng Punkte Variabel fir ze bestëmme wéi verzerrt d'Bild soll sinn. Wann d'Punkten héich si, da gëtt et vill verzerrt. Wat d'Punkte manner gi, wat d'Bild manner verzerrt wäert sinn. D'Punkten zielen an engems och als Timer, wéi op der __Timer Scratch Kaart__.

1. Erstell eng Variabel mam Numm _Punkte_ an der Lëscht vun de Variablen.
2. Veränner de Skript vun der Figur, esou dass en ausgesäit wéi dësen:
```scratch
    when FLAG clicked
    hide
    repeat pick random 1 to 5       
        next costume
    (end repeat)
    set score to 110
    repeat until score = 0
        change score by -10
        set pixelate effect to score
        set colour effect to score
        show
        wait 1 secs
    (end repeat)
```

Am beschten du setz de Block _verstecke dich_ ganz uewen, an de Block _setze [Punkte] auf 110_ an all déi aner dorënner.

###Test däi Projet
__Klick op de grénge Fändel.__

Taucht en zoufällegt a verzerrtent Bild op?

Gëtt et lues a lues manner verzerrt?

Ginn d'Punkten erof wat d'Bild manner verzerrt gëtt?

Ass d'Bild net méi verzerrt wann d'Punkten op 0 sinn?

Kriss du nach ëmmer en anert Bild, all Kéiers wou s du op de grénge Fändel klicks?

Späicher däi Projet
##Saache fir ze probéieren

__Probéier den Ufankswäert vun de Punkten ze änneren, an och em wéivill en all Tour erofgeet.__ Wat ännert dat um ausgesi vum Bild? Mécht dat et méi einfach oder mßei schwéier fir eraus ze fanne wat d'Bild ass?
__Probéier déi aner Grafik-Effekter aus der Lëscht.__ Wéi wierken déi sech op de Schwieregkeetsgrad aus?

3. SCHRATT: Erméiglech dem Spiller d'Bild z'eroden

Elo hu mir en Zoufallsbild dat lues a lues méi däitlech gëtt, an e Punktestand dee mat der Zäit erof geet, mä wéi kann ee lo bei dësem Spill gewannen?
Mir setzen e puer Figuren ënnen op d'Bühn, wou de Spiller drop klicke kann. Wann en op dat richtegt klickt huet e gewonn. Wann en op dat falsch klickt, verschwënnt dat Bild an d'Spill geet weider.

Als éischt musse mir awer emol wësse wat déi richteg Äntwert ass.

1. Erstell eng nei Variabel an nenn se __Antwort__. Kontrolléier, dass se _Für alle Figuren_ ass.
2. Änner de Skript vu virdrunn esou, dass déi richteg Äntwert gespäichert gëtt. Setz de Block _setze [Antwort] auf Kostümnummer_ direkt ënner déi éischt Schläif.

```scratch
    when FLAG clicked
    hide
    repeat pick random 1 to 5       
        next costume
    (end repeat)
    set answer to costume
    set score to 110
    repeat until score = 0
        change score by -10
        set pixelate effect to score
        set colour effect to score
        show
        wait 1 secs
    (end repeat)
```
__Elo setze mir d'Figure bei op déi de Spiller klicke kann..__

3. Verduebel d'Haapt-Figur an zéi d'Kopie ënne lénks an den Eck.
4. Nenn dës Figur ëm op __Antwort1__. (Dat mëscht et méi einfach driwwer ze schwätzen.)
5. Läsch de Skript vun __Antwort1__ an all d'Kostümer, bis op den éischten.
6. Widderhuel déi läscht 3 Schrëtt, mä setz elo d'Figur __Antwort2__ nieft __Antwort1__ a läsch all Kostümer bis op den zweeten.
7. Widderhuel et nach 3 mol, fir __Antwort3__, __Antwort4__, an __Antwort5__.
Elo misst du ënnen op der Bühn eng Rei mat fënnef Figuren hunn, an all Figur sollt ee von de Kostümer hunn, déi d'Haapt-Figur kann undinn. __Keng vun dëse Figure sollt e Skript hunn.__

Elo wëlle mir, dass d'Figuren réagéiere, wann een op se klickt an, jee nodeem op et déi richteg oder falsch Äntwert war, eppes geschitt.

8. Stell dëse Skript fir d'Figur mam Numm __Antwort1__ op:
```scratch
    when answer1 clicked
    if answer=1
        broadcast won
    else
        hide
    (end if)
```
9. Zéi dëse Skript op all déi aner Figuren (Dat kopéiert en dohinner). __Änner bei all Figur de Wäert 1 op 2, 3, an esou weider.__
10. Elo musse mir eppes bei setzen, dat op d'Nooricht _gewonnen_ reagéiert. Klick op d'Haapt-Figur (déi op der Tafel). Setz hei dëse Skript nach dobei: 
```scratch
    when I receive won
    say join Congratulations! You scored score
```
(sage verbinde Glückwunsch! Dein Punktestand: Punkte)

###Test däi Projet
__Klick op de grénge Fändel.__

Wärend dem Testen kann du d'Anzeig op der Bühn benotze, fir ze gesi wat déi richteg Äntwert ass. Fir ze testen ass dat praktesch.

Wat geschitt, wann s du op déi __richteg Äntwert__ klicks?

Wat geschitt, wann s du op déi __falsch Äntwert__ klicks?

Beim Test stelle mir zwéin Problemer fest. Éischtens, wann ee falsch réid kommen d'Figure bei der nächster Ronn net erëm. An zweetens, de Punktestand hält net op erof ze goe, wa mir déi richteg Äntwert geklickt hunn.

11. Setz dëse Skript bei all fënnef Äntwert-Figure bei fir den éischte Problem ze léisen (Erënner dech wéi ee Skripter ka kopéiren):
```scratch
    when FLAG clicked
    show
```

Fir den zweete Problem ze léisen, musse mir d'_wiederhole bis__ Schläif vun der Haapt-Figur ënnerbrieche wann de Spiller op déi richteg Äntwert klickt. Dofir benotze mir eng nei Variabel. Mir setzen se op __0__ wann d'Spill ufänkt an op __1__ wann d'Spill gewonne gouf. Elo ënnerbrieche mir d'__wiederhole bis__ Schläif, entweder wa _Punkte_ op __0__ ass, OR wann d'__ gewonnen__ Variabel op __1__ ass.

12. Erstell en nei Variabel an nenn se _gewonnen_
13. Änner d'Skripter vun der Haapt-Figur esou:
```scratch
    when FLAG clicked
    hide
    repeat pick random 1 to 5       
        next costume
    (end repeat)
    set answer to costume
    set score to 110
    set won to 0
    repeat until score = 0 or won? =1
        change score by -10
        set pixelate effect to score
        set colour effect to score
        show
        wait 1 secs
    (end repeat)
    
    When I receive won
    set won to 1
    clear graphics effects
    say join Congratulations! You scored score
```

Späicher däi Projet

__Gutt gemaacht! Du hues Basis-Version vum Spill fäerdeg!__

Du kanns däi Spill awer nach ausbauen. Probéier e puer vun dësen Erausfuerderungen!

##Erausfuerderung 1: Maach d'Spill méi schwéier oder méi einfach

Veränner de Schwieregkeetsgrad vum Spill.

* Probéier ze verännere wéi schnell d'Bild entzerrt gëtt a wéi séier d'Punkten ofhuelen.
* Probéier d'Effekter um Bild ze wiesselen.
* Benotz aner Biller, déi sech entweder méi ähnelen oder méi verschidde sinn. (Vergiess net och d'Kostümer vun den Äntwerten ze wiesselen).

Späicher däi Projet

##Erausfuerderung 2: Verzerr d'Bild an all Partie aanescht

Bis elo gëtt an all Ronn vum Spill d'Bild nämlecht verzerrt.
Vläit hues du am 2. Schratt e puer Grafik-Effekter ausprobéiert déi genau esou gutt funktionéieren wéi d'Faarw an d'Verpixelung.

Sich dir e puer Verzerrungen eraus déi gutt an eist Spill passen.
Veränner d'Spill esou, dass d'Biller an all Ronn aanescht verzerrt ginn.

__Tipp:__ Probéier et mat enger neier Variabel déi's Du _verzerrung_ nenns. Setz déi am Uffank op en zoufällege Wäert a benotz Bedéngungs-Bléck fir d'Variabel innerhalb vun der Schläif ze änneren.

Späicher däi Projet

##Erausfuerderung 3: Maach datt d'Spill méi wéi eng Ronn dauert

Bis elo ass all Ronn vum Spill onofhängeg vun där läschter. Veränner d'Spill esou, dass et e puer Ronnen huet. Du kéins z.B. 3 Ronne maachen, esou dass e Spiller dräi Biller erode muss a bis zu 300 Punkte ka kréien.

__Tipp:__ Du brauchs eng zousätzlech Variabl fir den Total vun de Punkten iwwert all d'Ronnen ze späicheren. Du wäerts och nach eng Schläif brauche fir méi wéi eng Ronn ze hunn.

__Tipp:__ Am Uffank vun all Ronn mussen all d'Biller déi falsch gerode goufen och erem optauchen. Kanns du eventuell eng Nooriicht dofir benotzen?

Späicher däi Projet

##Erausfuerderung 4: Looss d'Spill all Ronn méi schwiereg ginn

Du kéints och d'Spill no all Ronn e bësse méi schwéier gi loossen.

Brauch all Ronn en eegene Punktestand? Soll een an de spéideren, méi schwierege Ronne méi Punkte kréie wann ee richteg réid?

__Tipp:__ Wéi weess een, a wéienger Ronn ee gerad ass? Wéi kanns du dovunner gebrauch maache fir de Schwieregkeetsgrad ze änneren an d'Punkten ze zielen?

Späicher däi Projet

##Erausfuerderung 5: Looss d'Spill esou laang lafe, bis dass e Bild falsch gerode gouf

Amplaz d'Unzuel vun de Ronne vun Uffank u fest ze leeën, versich de Spiller esou laang spillen ze loosse bis dass en eppes falsch erréit. Dat funktionéiert natierlech just, wann d'Spill och ëmmer méi schwiereg gëtt.

Späicher däi Projet

##Erausfuerderung 6: Maach d'Spill méi einfach oder méi schwéier, ofhängeg dovunner wéi gutt de Spiller spillt

Amplaz dass d'Spill ëmmer méi schwiereg gëtt, kéint et sech jo och dem Kënne vum Spiller upassen. Maach déi nächst Ronn méi schwiereg wann deen d'Biller schnell erréid, a maach se méi einfach wann en et guernet, oder erréischt ganz spéit erréit.

Dëst funktionéiert just, wann s du net d'Punkte vun all de Ronnen zesummen ziels.

##Erausfuerderung 7: Verhal den Highscore

Looss d'Spill den Highscore späicheren. Wann ee Spiller méi Punkte kritt wéi den aktuellen Highscore, fro no sengem Numm a späicher dann den neien Highscore. Weis den aktuellen Highscore, an den Numm vum Spiller deen e kritt huet am Spill un.
Späicher däi Projet

##Erausfuerderung 8: Wann ee falsch réid gi vill Punkten ofgezunn

Bis elo gi keng Punkten ofgezunn, wann een einfach esou séier wéi méiglech op all d'Figure klickt fir déi richteg ze fannen. Veränner d'Spill esou, dass een all Kéiers Punkten ofgezu kritt, wann ee falsch réid.

Gëtt d'Spill doduerch besser?

__Bravo! Elo bass du fäerdeg an du kanns dech mat dengem neie Spill ameséiren!__
Vergiess net, dass du däi Spill all denge Kollegen an denger Famill weise kanns. 
Klick dozou op __Veröffentlichen!__ ganz uewen am Menü.