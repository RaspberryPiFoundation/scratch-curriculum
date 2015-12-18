<!--

Utilitzeu vs Useu vs feu servir
script vs tros de codi
"Comproveu que la bruixa es segueix movent de banda a banda de la pantalla" vs "La bruixa es segueix movent de banda a banda de la pantalla?"
fer clic/clicar vs prémer
Al prémer vs en prémer (al codi ha de ser "al" perque SCratch ho te aixi, pero i al text? )
 
6
 
Nivell 
Whack-a-Witch

 * Pas 1: Crear una bruixa voladora
* Pas 2: Fer aparèixer i desaparèixer la bruixa de manera al.leatòria
* Pas 3: Fer desaparèixer la bruixa després de cliclar-hi al damunt
* Pas 4: Afegir el marcador i el temps (score, timer)

 -->

Nivell 1

#Caça la Bruixa

__Introducció:__Aquest projecte s´inspira en el joc de fira d´origen anglès anomenat  __Whack-a-Mole__. Obtindreu punts en clicar les bruixes que apareixen a la pantalla. L'objectiu del joc és obtenir el màxim de punts en 30 segons!

##PAS 1: Crear una bruixa que voli

1.  Comenceu un nou projecte de Scratch. 

2.  Esborreu el personatge del gat i afegiu un nou fons d'escenari carregant el que trobareu a __nature/woods__.

3.  Feu servir el botó  __escull un personatge des d’un fitxer__  per afegir
la bruixa al projecte (vestit  __fantasy/witch1__). El primer que farem és fer que es mogui.
 
4.  Afegiu una __variable__ només per aquesta animació que es digui __velocitat__. A l´escenari,  el monitor d’aquesta variable ha de dir  “Personatge1 velocitat”. Si només diu “velocitat”,  elimineu la variable i torneu-la a crear, però només per aquesta animació. Desmarqueu la casella de la variable a la paleta de variables perquè no es vegi a l’escenari.
La variable velocitat controlarà la velocitat de la bruixa. Fem servir una variable, perquè així més endavant podrem canviar la velocitat.

5.  El primer que volem és  que la bruixa es comenci a moure en començar el joc.
Per fer-ho escriviu aquest script:


```
	quan la BANDERA VERDA es premi
	assigna a velocitat el valor 5
	per sempre
		mou-te velocitat passos
	(fi del per sempre)
```		
###Proveu el projecte
 
__Feu clic a  la bandera verda__ 

Observeu què fa la bruixa. Com és que s'encalla a la vora de la pantalla?

 6.  Per tal de que la bruixa no s'encalli, feu que giri cua en tocar la vora de la pantalla. Sota el bloc __"mou-te velocitat passos"__ afegiu-hi el bloc  __"rebota en tocar una vora"__.


 7. A més a més, per tal que la bruixa no es giri de caps per avall, utilitzeu el bloc __"fixa la rotació a" on seleccionarem esquerra-dreta.
 
```
	quan la BANDERA VERDA es premi
	fixa la rotació a esquerra-dreta
	assigna a velocitat el valor 5
	per sempre
		mou-te velocitat passos
		rebota al tocar una vora
	(fi del per sempre)
```	


###Proveu el Projecte

__Feu clic a la bandera verda__.

Comproveu que la bruixa es mou de banda a banda de la pantalla.


###Per saber-ne més
__Proveu de canviar el valor de la velocitat per fer que la bruixa vagi més ràpida o més lenta.__
 
__Com us ho faríeu per fer que la bruixa voli cada vegada més ràpid?__
(Fer que la bruixa vagi cada cop més ràpid té truc, no us preocupeu si no veieu la manera de fer-ho. Anirem donant més pistes al llarg del projecte.)


##PAS 2: Fer desaparèixer la bruixa en qualsevol moment

Per fer el joc més interessant, farem que la bruixa aparegui i desaparegui en qualsevol moment. Crearem un altre script que corri al mateix temps que es mou la bruixa. El nou script amagarà la bruixa durant un temps qualsevol, llavors la mostrarà durant un altre interval de temps, i ho anirà repetint per sempre (o fins que s'acabi el joc). Creeu aquest script per la bruixa:

```
	quan la BANDERA VERDA es premi
	per sempre
		amaga
		espera nombre a l'atzar entre 2 i 5 segons
		mostra
		espera nombre a l'atzar entre 2 i 5 segons
	(fi del per sempre)
```

###Proveu el projecte

__Feu clic a la bandera verda.__ 
Comproveu si la bruixa es segueix movent de banda a banda de la pantalla.
Apareix i desapareix en qualsevol moment?
 

###Per saber-ne més
__Proveu de canviar el rang dels nombres a l'atzar. Què passa si agafeu números molt grans? i molt petits?__(Potser això us dóna alguna pista de com fer que la bruixa voli més ràpid a mesura que passa el temps …)


##PAS 3: Fer que la bruixa desaparegui al clicar-la
 
Per fer que això sigui un joc, hem de donar als jugadors alguna cosa a fer. Hauran de clicar damunt la bruixa per fer-la desaparèixer. Quan li facin clic a sobre, volem que desaparegui i que s'escolti un so.
 
1.  A la pestanya __Sons__,  importeu el so  __electronic/fairydust__.
 

2.  Afegiu aquest script a la bruixa:

```
	quan es cliqui aquest personatge
	amaga
	toca el so Fairydust
```

###Proveu el projecte

__Feu clic a  la bandera verda.__ 
Comproveu que la bruixa desapareix i produeix el so escollit en clicar-la.

DESEU EL PROJECTE

##PAS 4: Afegir un marcador i un cronòmetre 

Tot i que ja tenim llesta la  bruixa, el nostre objectiu és crear un joc! Afegirem un marcador que ens servirà per anar anotant els punts cada cop que cliquem a sobre de la bruixa abans no s'acabi un temps. Per tant, necessitarem una variable per al temps i una altra per al marcador.

1. Creeu una nova variable __per tots els personatges__ que es digui __marcador__ i retoqueu l'script perquè s'incrementi en un punt el marcador cada cop que s'atrapa la bruixa.

```
	quan es cliqui aquest personatge
	amaga
	toca el so Fairydust
	augmenta marcador en 1
```

2.  Aneu a l'__escenari__ i creeu una nova variable (aquesta __només per l'escenari__) que es digui __temps__. Afegiu un script que posi el temps a 30 i el marcador a 0 al prémer la bandera verda. Feu servir un bloc __repeteix fins que__ per esperar un segon i reduir el temps un segon. Això s'hauria de repetir fins que el temps arribi a 0. En arribar a zero, cridarem __atura tot__ per aturar el joc.
 

```
	quan la BANDERA es premi
	assigna a  temps el valor 30
	assigna a  marcador el valor 0
	repeteix fins temps = 0
		espera 1 segons
		augmenta temps en  -1
	(fi del repeteix)
	atura tot
```
###Proveu el projecte
	
__Feu clic a la bandera verda.__ 


###Per saber-ne més

__Molt bé, heu completat el joc bàsic!!!__

__Sabeu ja com fer-ho perquè la bruixa vagi cada vegada més i més ràpid?__


###Repte: Poseu-hi més bruixes!

1.  Dupliqueu la bruixa prement el botó dret del ratolí damunt la llista de personatges.
2.  Ajusteu la mida de cada bruixa, perquè tinguin dimensions diferents.
3.  Canvieu la variable velocitat de cada bruixa per fer que volin a velocitats diferents.
4.  Per tal que no estiguin juntes, moveu-les a diferents punts de l'escenari. 
 
###Proveu el projecte

__Feu clic a  la bandera verda.__ 

Teniu unes quantes bruixes movent-se d'un costat a l'altre de l'escenari? Apareixen i desapareixen a l'atzar? 

DESEU EL PROJECTE
 

###Per saber-ne encara més
1.  Quin creieu que seria el número de bruixes que podríem afegir al joc per fer-lo encara més divertit?
2.  Podríeu canviar l'aspecte de les bruixes? Proveu a editar-ne els vestits, o utilitzar els blocs d'efectes de la paleta Vestits.
3.  Podríeu fer que algunes bruixes donessin més puntuació que d’altres?

__Ben fet, heu completat el joc, ara a jugar!!!__	

Recordeu que podeu compartir el joc amb els vostres amics i família prement a __Compartir__ a la barra de menú!
