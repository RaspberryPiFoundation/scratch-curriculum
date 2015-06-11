Nivell 2

#Màquina de fruita

__Introduccció:__

Aquest és un joc semblant a les màquines escurabutxaques. Consisteix en anar canviant el vestit de tres personatges fins que els tres mostrin la mateixa imatge. 

## PAS 1: Crear un personatge que canvii de vestit

__Anem a importar imatges diferents per el nostre joc__

1. Comenceu un projecte d'Scratch nou. Esborreu el gat clicant amb el botó de la dreta i triant __Esborra__

2. Importeu un nou personatge

3. Trieu qualsevol imatge de qualsevol carpeta. Nosaltres hem utilitzat __things/bananas1__, però podeu triar qualsevol imatge que us agradi.

4. Cliqueu la pestanya Vestits i importeu dues coses més. Ara ja teniu 3 personatges (nosaltres vam utilitzar __animals/bee1__ i __things/lego__, però podeu utilitzar el que us vingui més de gust).

__Ara que tenim els vestits, volem que el personatge se'ls vagi canviant.__

##PAS 2: Fer que les imatges vagin canviant

1. Cliqueu la pestanya de __Programes__

2. Seleccioneu Control i arrossegueu el bloc  __quan la bandera verda es premi__. El que poseu a continuació passarà cada vegada que el jugador premi la bandera verda.

3. Afegiu el bloc  __per sempre__ a continuació.

4. Cliqueu la bandera verda a dalt a la dreta. Fixeu-vos que ara apareix una petita ombra blanca al voltant del nostre programa. Això significa que  el nostre programa està corrent perquè hem clicat la bandera verda.

5. cliqueu la paleta __Aspecte__ i arrossegueu dins del bloc __següent vestit__

6. Com alentiríem el programa perquè no canvii de vestit tant ràpidament? Cliqueu a la paleta de  __Control__ i arrossegueu el bloc __espera 1 segons__

7. Ajusteu el temps fins que el canvi a un pas més ràpid (normalment, un temps de 0.1s és suficient). Què passaria si no haguéssim posat el bloc espera?

```scratch

	quan la bandera verda es premi
	per sempre		
		següent vestit
		espera 0.1 segons
	(acaba per sempre)
```

###Proveu el projecte

__Premeu la bandera verda.__
Els vestits canvien a una velocitat raonable? 


###Per saber-ne més

Ajusteu el temps en el bloc __espera__. Quin temps penseu que faria el joc més fàcil o més difícil?

##PAS 3: Fer que els personatges deixin de canviar de vestit al clicar-hi a sobre

Perfecte! Ara farem que el personatge canvii el vestit per sempre, però com ho fem perquè parin de canviar de vestit quan hi cliquem a sobre?

1. Creeu una nova variable clicant a la pestanya __Dades__. Anomeneu-la __"stopped"__" i feu que sigui visible per a tots tres personatges. Després deseleccioneu la casella perquè no es mostri sobre l'escenari.

2. Feu que __"stopped"__ tingui el valor de 1 quan algú cliqui sobre la imatge utilitzant el bloc __quan es cliqui aquest personatge__ i assigneu-li el valor 0 al començar a jugar, just després del bloc __quan la bandera verda es premi__.

3. Ara volem que les imatges no canviin mentre la variable __"stopped"__ sigui igual a 1. Cliqueu a la paleta de __Control__ i canvieu el __per sempre__ pel bloc  __per sempre__ i a continuació __ si__. Llavors, utilitzeu el bloc de la paleta d'__operador__ __=__ per comprovar si la variable __"stopped"_" és igual a 0.

###Proveu el projecte

__Premeu bandera verda, espereu un moment i després cliqueu un personatge__

Els personatges, canvien de vestit mentre no hi cliqueu a sobre??
Paren quan hi heu clicat a sobre?

__Reinicieu el personatge.__ El personatge es para quan hi poseu el ratolí a sobre sense clicar-lo? Quan cliqueu en qualsevol altre posició sobre l'escenari, es para? I si cliqueu sobre algun altre lloc sobre la finestra d'Scratch? I fora de la finestra d'Scratch?


##Step 4: Crear els altres personatges 

__Ara necessitem crear els altres personatges per tal de poder jugar al nostre joc!__

1. Dupliqueu el personatge (Sprite1) clicant-hi a sobre amb el botó dret.

2. Dupliqueu-lo una altra vegada. Ara heu de tenir 3 personatges sobre l'escenari.

3. Moveu cada personatge per tal que estiguin en línia. Feu-los una mica més petits si ho necessiteu.


###Proveu el projecte
__Premeu bandera verda.__ Totes les animacions haurien de canviar. Proveu de parar-les totes de cop!


###Per saber-ne més

Quan engegueu el joc just després de carregar-lo, tots els personatges mostren el mateix vestit i canvien a l'uníson. Com ho faríeu per tal que els personatges canviessin de vestit aleatòriament quan premeu bandera verda? Pista: proveu d'agafar un vestit a l'atzar per a cada personatge un cop hagi començat el joc.

__Molt bé per aquells que han finalitzat el joc bàsic. Tota manera, hi ha més coses que es poden afegir al joc. Proveu els reptes següents!__


##Repte 1: Fer el joc més difícil

Penseu en una manera de fer el joc més difícil. Per exemple, fent que els vestits canviin més depressa. Intenteu després coses més imaginatives:

1. Canviar el nombre de vestits que té cada personatge..

2. Fer que alguns personatges tinguin vestits únics.

3. Introduir diferents temps entre els canvis de vestit.

4. Fer que cada personatge canvii a un vestit aleatori enlloc del vestit següent.


__Divertiu-vos amb tots aquests canvis!__

Cada cop que feu un canvi, penseu si fa el joc més difícil o més senzill. Com es pot ajustar la dificultat del joc per tal que sigui la justa?


##Repte 2: Fer que el joc sigui més difícil i senzill amb el temps

A l'hora de jugar, us trobareu amb persones de diferents habilitats. __Com ajustareu la dificultat del joc depenent del jugador?__

Una manera de fer-ho és __ajustar la velocitat de canvi dels vestits__. Podeu utilitzar una variable, que s'anomeni *retard*, que ens doni la durada de cada bloc __espera__ per a cada personatge. Si el jugador guanya la partida, la variable __"retard"__ es pot escurçar una mica (per fer el joc més difícil). Si el jugador perd la partida, la variable __"retard"__ es pot augmentar una mica (per fer el joc més fàcil).


##￼Repte 3: Detectar que els 3 personatges s'han aturat amb el mateix vestit
__La finalitat del joc és clicar sobre els personatges en el moment que aquestes mostren el mateix vestit. Estaria bé que l'escenari detectés l'estatus del joc quan es paren els personatges i que et digués si heu guanyat o perdut tot comprovant si els 3 personatges porten el mateix vestit.__

Primer de tot, l'escenari ha de saber quan acaba el jugador. Podem fer això fent que l'escenari comprovi si els 3 personatges han parat de moure's quan hi cliquem a sobre. Modifiqueu per a cada personatge el bloc __quan es cliqui sobre aquest personatge__ per enviar a tots un nou missatge, "checkforEnd".

L'escenari pot respondre a aquest missatge i comprovar si el joc s'ha acabat mirant que les 3 variables __"stopped"__ dels 3 personatges valen 1. Per fer-ho, utilitzem el bloc __posició x del personatge__ per a cada personatge i canviem __"posició x"__ per la variable __"stopped"__. Si tots 3 personatges tenen el valor de __"stopped"__ a 1, sabem que el joc s'ha acabat i podem comprovar si el jugador ha guanyat o no.

Per fer-ho, podem utilitzar el mateix bloc __posició x del personatge__ però enlloc de comprovar la variable __"stopped"__, podem comprovar el número de vestit i veure si el personatge Sprite1 té el mateix vestit que Sprite2, i si el personatge Sprite2 té el mateix vestit que Sprite3.

Necessitareu doncs un bloc __si__ per comprovar cada variable __"stopped"__ i dins d'aquest bloc un altre bloc __si...si no__ per comprovar si el jugador ha guanyat o no comparant cada vestit de cada personatge.

Arribats a aquest punt, podeu anunciar el resultat del joc utilitzant un bloc __digues__ i fer-ho utilitzant una altre personatge. Podeu utilitzar el gat Fèlix perquè digui al jugador si ha guanyat o ha perdut. 

__Ara que heu acabat, ja podeu disfrutar del vostre joc!__
No us oblideu de compartir-lo amb la vostra família i amics!
