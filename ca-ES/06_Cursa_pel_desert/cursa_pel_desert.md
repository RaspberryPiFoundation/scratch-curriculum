<!--
******************************************************************************************
CURSA PEL DESERT

Traducció per Sergi Valverde
Repàs a 2.0 de Mireia Dosil

******************************************************************************************
-->


Nivell 2

#Cursa pel desert

__Introducció:__
Aquest és un joc per dos jugadors on competeixen un lloro i un lleó pel desert. Cada jugador ha de prémer una tecla tant ràpid com pugui per fer moure l'animal i guanya el primer que arribi a la vora de la pantalla.

##PAS 1: Creeu l'escenari i afegiu-hi els objectes

1. Seleccioneu l'escenari i afegiu-hi el fons 'natura/desert'
2. Esborreu el personatge 'Félix'
3. Afegiu-hi el personatge lleó que trobareu a la carpeta 'animals'.
4. Seguidament, afegiu-hi el personatge 'parrot' (lloro) que també trobareu a la carpeta 'animals'.


##PAS 2: Feu que el lleó i el lloro es moguin

Volem que els objectes es moguin quan premem una tecla.

1. Primer, seleccioneu l'objecte lleó i feu que faci 4 passes quan premeu la tecla 'L'.

```scratch

	al prémer la tecla l
	mou-te 4 passes	
```

2. Seguidament, seleccioneu l'objecte lloro i feu que també es mogui 4 passes quan premeu la tecla 'A'. 



```scratch

	al prémer la tecla a
	mou-te 4 passes	
```

###Proveu el projecte
__Feu clic la bandera verda__

El lleó i el lloro, es mouen per la pantalla quan premeu les tecles 'L' i 'A'?


##PAS 3: Comenceu la cursa

Necessitem un sistema per començar la cursa i saber qui l'ha guanyat. __Primer, crearem un botó d'inici.__

1. Afegiu un nou personatge. De la carpeta 'coses' escolliu el personatge 'Button1'. Canvieu-li el nom per 'ComenceuCursa'
2. Modifiqueu el vestit del personatge, afegiu-hi el text 'inici' i feu clic a 'd'acord'. Moveu el personatge al mig de l'escenari.
3. Afegiu un programa que mostri l'objecte 'ComenceuCursa' quan comenci el joc.


```scratch

	al prémer BANDERA
	mostreu
```

4. Finalment, volem que quan premem el botó, compti enrere a partir de 3, digui 'endavant' i s'amagui.  

```scratch

	quan es cliqui aquest personatge
	digues 3 per 1 segon 
	digues 2 per 1 segon 
	digues 1 per 1 segon 
	digues Endavant! per 1 segon
	amaga
```

###Proveu el projecte
__Feu clic a la bandera verda.__

Al fer clic sobre el botó d'inici, comença a comptar enrere fins donar la sortida? 


Volem que els corredors només es moguin després de que s'hagi donat l'inici de la cursa. També volem saber quan la cursa s'ha acabat. Per tant, necessitem una variable que mantingui aquesta informació. 

5. Afegiu una variable visible per tots els objectes anomenada 'corrent'. Feu que no sigui visible a l'escenari desmarcant-la al panell de variables.

6. Fixeu la variable 'corrent' a 0 a l'inici del joc. Llavors, a l'anterior programa 'al prémer BANDERA' afegiu-hi:


```scratch

	al prémer BANDERA
	mostra
	assigna a 'corrent' el valor 0
```

7. A continuació, fixeu la variable 'corrent' a 1 quan el rellotge de sortida hagi finalitzat.

8. Mentre la variable 'corrent' no sigui 1, el lleó i el lloro han d'estar aturats. Feu clic a l'objecte Lloro. __Afegiu un bloc de control a l'objecte__ que només permeti al lloro moure's si __corrent = 1__. 


```scratch

	quan la tecla a es premi
	si corrent = 1 llavors
		mou-te 4 passos
	(fi de si)
```

9. Ara cal que feu el mateix per l'objecte lleó.

###Proveu el projecte
__Feu clic a la bandera verda.__

El lleó i el lloro, es mouen únicament quan el compte enrere s'ha acabat?

Volem saber qui ha guanyat la cursa per a continuació reiniciar-la i poder començar de nou una partida. 

##STEP 4: Acabant la cursa

1. Afegiu un nou bloc a l'objecte lloro que fixi la variable 'corrent' a 0 quan l'objecte toqui la vora de la pantalla. 

```scratch

	quan la tecla a es premi
	si corrent = 1 llavors
		mou-te 4 passos
		si tocant vora? llavors
			assigna a 'corrent' el valor 0
		(fi de si)
	(fi de si)
```

2. Volem que el lloro ens indiqui si ha guanyat la cursa. Enregistreu un so nou per al lloro que ens avisi en el cas que l'hagi guanyat. Feu clic a __sons__ i graveu el so del lloro guanyant la cursa! 

3. A continuació, afegiu els blocs que faran reproduir el so que heu enregistrat i que faran dir al lloro que ha guanyat la cursa. 


```scratch

	quan la tecla a es premi
	si corrent = 1 llavors
		mou-te 4 passos
		si tocant vora? llavors
			assigna a 'corrent' el valor 0
			toca el so gravació1 fins que acabi
			digues El lloro ha guanyat! durant 3 segons
		(fi de si)
	(fi de si)
```

4. Finalment, repetiu els mateixos passos pel lleó. 

###Proveu el projecte
__Feu clic a la bandera verda.__
Podeu fer clic al botó d'inici i seguidament començar a córrer prement les tecles 'A' i 'L'? Els objectes, toquen el seu corresponent so i missatge de victòria quan arriben al final de la cursa?


##PAS 5: Reiniciant la partida

A l' acabar la partida necessitem dir-li a la resta d'objectes que hem guanyat la cursa i reiniciar el joc per poder tornar a jugar-hi.

__Necessitem que l'objecte que guanyi enviï un missatge a la resta dient que ha guanyat.__


1. Feu clic a l'objecte Lloro. Afegiu un bloc que enviï "finalitzat" després de que l'objecte digui que ha guanyat. 


```scratch

	al prémer una tecla
	si corrent = 1
		mou-te 4 passos
		si tocant vora?
			fixa 'corrent' a 0
			toca so enregistrament 1
			digues El lloro ha guanyat! durant 3 segons
			envia a tots 'acabat'
		(fi de si)
	(fi de si)
```

2. Necessitem afegir un nou bloc que escolti els missatges d'acabament i mogui de nou el lloro a la línia de sortida. Què passa si canvieu el valor fixat a x?


```scratch

	quan rebi acabat 
	assigna el valor -150 a x
```

3. Afegiu el mateix programa a l'objecte Lleó. Proveu diferents valors de x per assegurar-vos que el lleó i el lloro tornen a la línia de sortida. 

4. També ens interessa posar al lleó i el lloro a la mateixa posició de sortida, per tant afegiu un altre programa als dos objectes que els mogui a la línia de sortida al fer clic sobre la bandera. 

```scratch
	
	al prémer BANDERA
	assigna el valor -150 a x
```

5. Finalment, feu clic a l'objecte botó i afegiu-hi un programa que el torni a mostrar quan rep el missatge 'acabat'.

###Proveu el projecte
__Feu clic a la bandera verda.__

Podeu competir contra amics si un de vosaltres prem la tecla 'A' per moure el lloro i l'altre la tecla 'L' pel lleó?

Deseu el projecte

##Desafiament: Afegiu-hi un turbo

* __Intenteu a afegir-hi un turbo__ que es pugui fer servir un cop per cursa i faci que el lleó o el lloro es moguin 30 passos de cop. 
* __Afegiu un nou vestit__ pels animals, amb foc sortint pel darrera i que apareixerà en el moment que premeu el turbo. 
* __Enregistreu nous sons__ pels animals, que es sentin quan premeu el turbo.

### Proveu el projecte

__Ben fet, ja heu acabat. Ara podeu gaudir del joc!__ No oblideu de que podeu compartir el vostre joc amb tots els vostres amics i familiars fent clic  __Comparteix__ a la barra de menú.
