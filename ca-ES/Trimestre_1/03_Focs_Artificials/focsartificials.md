Nivell 1

#Focs artificials

__Introducció:__

En aquest projecte, llençarem focs artificials al cel d'una ciutat.


## PAS 1: Crear un coet que vola apuntant el ratolí

__Importem les imatges necessàries per el nostre joc__

1. Creeu un nou projecte Scratch. Esborreu el gat clicant-lo amb el botó dret i seleccionant __Esborra__
2. Canvieu l'escenari per __outdoor/city-with-water__
3. Utilitzeu el botó __escull un personatge des d'un fitxer__ per afegir el personatge __coet__ al projecte (utilitzeu el vestit __recursos/coet.png__)
4. Feu que el coet desaparegui quan es premi la bandera verda

__Ara volem que el coet apunti el ratolí quan el cliquem__

5. Afegiu el bloc __quan es cliqui la tecla espai__. En aquest bloc feu que el coet aparegui i llisqui en direcció al punter del ratolí

```scratch

	Quan la  bandera verda es premi
	amaga
	
	al prémer tecla espai
	mostra
	llisca en 1 segons fins a x: ratolí x y: ratolí y
```	

###Proveu el projecte
__Premeu la bandera verda, poseu el ratolí sobre l'escenari i premeu la tecla espai.__

Us apareix el coet movent-se en la direcció del ratolí?Què passa si moveu el ratolí i premeu la tecla espai una segona vegada?

6. Els focs artificials no es solen moure de costat a costat. Assegureu-vos que el vostre coet llisca en direcció el ratolí sortint sempre des de la part de baix de la pantalla. Abans de mostrar el coet, utilitzeu el bloc __vés a__ per dir-li al coet que es mogui cap a la part baixa de la pantalla conservant la seva posició horitzontal.

```scratch

	Quan la  bandera verda es premi
	amaga
	
	al prémer tecla espai
	vés a x: ratolí x y: -200
	mostra
	llisca en 1 segons fins a x: ratolí x y: ratolí y	
```
###Proveu el projecte

__Premeu la bandera verda, poseu el ratolí sobre l'escenari i premeu la tecla espai.__
El coet vola des de la part baixa de la pantalla en direcció al ratolí? què passa si moveu el ratolí i torneu a prémer la tecla espai?

7. Finalment, feu aquesta operació utilitzant el botó del ratolí en comptes de la tecla espai. Per fer això, podem inserir el nostre codi dins el bloc __per sempre si ratolí clicat? llavors__.

8. Després canvieu el bloc __quan la tecla espai es premi__ per __quan la bandera verda es premi__ i finalment, assegureu-vos que el coet s'amaga cada vegada que tornem a començar. 

```scratch
	
	quan la bandera verda es premi
		amaga
		per sempre 
		   si ratolí premut? llavors
		     vés a x: ratolí x y: -200
			 mostra
			 llisca en 1 segons fins a x: ratolí x y: ratolí y
		(acaba per sempre)
```
###Proveu el projecte

__Premeu la bandera verda, i després cliqueu el ratolí sobre l'escenari. Torneu a clicar el ratolí en un altre punt.__ 

###Per saber-ne més:

1. Intenteu canviar el moviment del coet: en comptes de lliscar recte cap on és el ratolí feu que faci una trajectòria una mica corbada.

2. Intenteu que alguns coets vagin més lents que d'altres.

  
##PAS 2: Fer explotar el coet


1. El primer que us cal per fer explotar el coet és fer que soni una explosió just abans que comenci a moure's. El so el podeu trobar a la carpeta __Recursos/bang__.  Llavors es tracta que s'amagui un cop arribi on és el ratolí. Per importar un so aneu a la __pestanya Sons__ i cliqueu __importa__.


```scratch

	quan la bandera verda es premi
		amaga
		per sempre 
		   si ratolí premut? llavors
		     vés a x: ratolí x y: -200
			 toca el so bang
			 mostra
			 llisca en 1 segons fins a x: ratolí x y: ratolí y
			 amaga
		(acaba per sempre)
```

2. Finalment, feu que el coet envii un missatge quan explota. Utilitzarem aquest missatge més endavant.

```scratch

	quan la bandera verda es premi
		amaga
		per sempre 
		   si ratolí premut? llavors
		     vés a x: ratolí x y: -200
			 toca el so bang
			 mostra
			 llisca en 1 segons fins a x: ratolí x y: ratolí y
			 amaga
			 envia a tots explode i espera 
		(acaba per sempre)
```


###Proveu el projecte

__Premeu la bandera verda.__ 
Assegureu-vos que el coet toca un so i s'amaga quan arriba al ratolí.

3. Importa un nou personatge des de __Recursos/focartificial1.png__

4. Quan rebi el missatge __explode__, s'ha d'amagar i moure's a la posició del coet fent servir la instrucció __vés a__, després s'ha de mostrar i finalment s'ha d'amagar una altra vegada al cap d'un segon.


```scratch
	
	Al rebre explode
	amaga
	vés a x:posició x del coet  y:posició y del coet
	mostra
	espera 1 segons
	amaga
```
	
###Proveu el projecte

__Llenceu un altre coet.__ 
Es canvia per un personatge d'explosió quan explota?
Què passa si manteniu el botó del ratolí clicat mentre moveu el ratolí? (No us preocupeu, ja arreglarem això més tard).

##PAS 3: Fer que cada explosió sigui única

1. Ara podem fer que cada explosió sigui única utilitzant el bloc efectes de color i triant un color aleatori entre 1 i 200 abans de mostrar-lo.

```scratch
	
	al rebre explode
	amaga
	fixa l'efecte color a nombre a l'atzar entre 1 i 200
	vés a x: posició x del coet y: posició y del coet
	mostra
	espera 1 segons
	amaga```


###Proveu el projecte
__Premeu la bandera verda.__ 

Cada explosió té un color diferent?

  2. Afegim ara diferents vestits per l'explosió amb les imatges de __Recursos/focartificial2.png__ i __Recursos/focartificial3.png__. Intercanvia'ls per a cada coet abans de mostrar-los.

###Proveu el projecte

__Premeu bandera verda.__ 

Cada coet té un gràfic diferent quan explota?


3. Finalment, fem que cada explosió creixi amb el temps en comptes que aparegui i prou. Enlloc d'esperar un segon, fixeu el tamany del personatge al 5% abans de mostrar-lo, i una vegada l'hàgiu mostrat, augmenteu el tamany en 2 unitats cinquanta vegades, utilitzant el bloc __repeteix__.


```scratch

	al rebre explode
	amaga
	fixa l'efecte color a nombre a l'atzar entre 1 i 200
	vés a x: posició x del coet y: posició y del coet
	fixa la mida a 5%
	mostra
	repeteix 50
	   augmenta 2 la mida
	(acaba el repeteix)
	amaga	
```
  
###Proveu el projecte

__Premeu la bandera verda.__ 

El gràfic d'explosió d'escampa des del centre del coet i creix lentament?


###Per saber-ne més

Per què no proveu de fer encara més úniques les explosions? Proveu-ho alterant la mida i velocitat de cada explosió.



##PAS 4: Arreglar l'error de transmissió de missatges

Recordeu que abans hi havia un error quan manteníem el botó del ratolí clicat? Això passa perquè quan el coet envia el missatge que ha explotat, repetirà immediatament el bloc __per sempre si ratolí clicat__ i enviarà un altre missatge d'explosió abans que l'anterior hagi acabat de mostrar-se.

1. Per arreglar-ho, s'ha de substituir el bloc __envia a tots__ amb un bloc __envia a tots i espera__. D'aquesta manera, el bloc no es repetirà fins que l'explosió hagi acabat.


```scratch
	
	al prémer bandera verda
	amaga
	per sempre si ratolí clicat?
	vés a x: ratolí x y: -200
	  toca el so bang
	  mostra
	  llisca en 1 segons fins a x: ratolí x y: ratolí y
	  amaga
	  envia a tots explode i espera
	(acaba per sempre)	
```

###Proveu el projecte

__Premeu la bandera verda, mantingueu apretat el botó dret del ratolí i moveu el ratolí per tot l'escenari.__ 

El gràfic d'explosió apareix en el lloc i el temps correcte?

Deseu el projecte
