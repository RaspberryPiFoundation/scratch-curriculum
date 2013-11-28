Nivell 1

#Fèlix i Herbert

__Introducció:__
Construirem un joc on __el gat Fèlix__ i el ratolí __Herbert__ jugen a atrapar. Vosaltres controlareu en Herbert amb el ratolí i heu d'intentar evitar que en Fèlix us atrapi. Quant més temps eviteu que us atrapi més punts guanyareu, però no us deixeu agafar perquè perdreu punts!

##PAS 1: En Fèlix segueix el punter del ratolí

1. Creeu un nou projecte.
2. Feu doble clic al escenari i canvieu a la pestanya dels fons, llavors seleccioneu el fons __indoors/hall__. Suprimiu el fons blanc original.
3. Canvieu el nom del personatge per Fèlix. 
4. Assegureu-vos que en Fèlix només miri a esquerra utilitzant el bloc __"fixa la rotació a__:
5. Creeu aquest programa:

```scratch

	Quan la bandera verda es premi
	fixa la rotació a esquerra-dreta
	per sempre
		apunta cap a punter del ratolí
		mou-te 10 passos
		següent vestit
		toca la nota 62 durant 0.3 pulsacions
	(fi del per sempre)
```
		
###Proveu el projecte
__Feu clic a la bandera verda.__
En Fèlix, segueix el punter del ratolí? Quan es mou, us sembla com si caminés? Es mou a una velocitat adequada?


##PAS 2: En Fèlix persegueix en Herbert

__A continuació volem que en Fèlix persegueixi en Herbert, enlloc del punter del ratolí.__

1. Creeu un nou personatge escollint __animals-mouse1__
2. Canvieu el nom del personatge per Herbert.
3. Editeu el vestit i feu-l'ho més petit que el de'n Fèlix.
Proveu fent 6 clics al botó __encongir__.
4. Assegureu-vos que en Herbert només miri a esquerra i dreta utilitzant el bloc __"fixa la roació a"__.
5. Doneu-li aquest programa a en Herbert:


```scratch
	
	Quan la bandera verda es premi
	fixa la rotació a esquerra-dreta
	per sempre
		vés a punter del ratolí
		apunta cap a Fèlix
	(fi del per sempre)
´´´

###Proveu el projecte
__Feu clic a la bandera verda.__

En Herbert, segueix el punter del ratolí? En Fèlix persegueix al Herbert?



##PAS 3: En Fèlix diu quan ha atrapat en Herbert

__Volem que en Fèlix sàpiga quan ha atrapat en Herbert i que ens ho digui.__

1. Modifiqueu el programa d'en Felix així:
  
´´´scratch
	
	Quan la bandera verda es premi
	fixa la rotació a esquerra-dreta
	per sempre
		apunta cap al punter del ratolí
		mou-te 10 passos
		següent vestit
		toca la nota 62 durant 0.3 pulsacions
		si tocant Herbert llavors
		    digues atrapat
			espera 1 segons
		(fi del si)
	(fi del per sempre)
´´´

###Proveu el projecte
__Feu clic a la bandera verda.__

En Fèlix diu quan ha atrapat en Herbert?


##PAS 4: En Herbert es converteix en un fantasma quan l'atrapen

__En lloc de que en Fèlix digui quelcom, volem que en Herbert es converteixi en un fantasma quan l'atrapin.__

1. Canvieu el programa d'en Fèlix per tal d'enviar aquest missatge quan atrapi en Herbert.
  
´´´scratch
	
	Quan la bandera verda es premi
	fixa la rotació a esquerra-dreta
	per sempre
		apunta cap al punter del ratolí
		mou-te 10 passos
		següent vestit
		toca la nota 62 durant 0.3 pulsacions
		si tocant Herbert llavors
		    digues atrapat
			envia a tots atrapat
			toca la nota 59 durant 0.2 pulsacions
			espera 1 segons
		(fi del si)
	(fi del per sempre)
´´´


2. Importeu un nou vestit per en Herbert de __fantasy/ghost2-a__.
3. Editeu-l'ho per fer-l'ho més petit. N'hi hauria d'haver prou amb sis clics al botó __encongir__.
4. Canvieu els noms dels vestitsde'n Herbert de manera que vestit de ratolí s'anomeni __'viu'__ i el de fantasma __'fantasma__'.
5. Creeu un nou programa per tal de convertir en Herbert en un fantasma:

```scratch
	
	al rebre atrapat
	canvia el vestit a fantasma
	espera 0.5 segons
	canvia el vestit a viu
´´´	
###Proveu el projecte
__Feu clic a la bandera verda.__

Quan atrapeu en Herbert, es converteix en un fantasma?
En Fèlix fa els sons adequats en cada moment?
En Fèlix roman quiet prou temps per a que en Herbert es pugui escapar?


##PAS 5: Actualitzar el marcador

__Afegirem un marcador de manera que sabrem com de bé mantenim al Herbert en vida.
Començarem amb el marcador a zero i l'incrementarem una unitat cada segon. Si en Fèlix atrapa en Herbert, reduirem el marcador en cent unitats.__

1. Creeu una variable per a tots els personatges en el menu de dalt, i anomeneu-la __puntuació__.

2. Creeu aquests dos programes a l'escenari

```scratch
	
	Quan la bandera verda es premi
	assigna a puntuacio el valor 0
	per sempre
		augmenta puntuació en  1 
		espera 1 segons
	(fi del per sempre)
		
	al rebre atrapat
	augmenta puntuació en -100 
´´´
###Proveu el projecte
__Feu click a la bandera verda.__

El marcador, augmenta una unitat per segon?
Quan en Fèlix atrapa en Herbert, el marcador disminueix cent unitats?
Què passa quan atrapeu en Herbert abans que el marcador arrivi a cent unitats? 
Quan comenceu una nova partida, el marcador torna a zero?

Deseu el projecte

__Molt bé, heu acabat. Ara ja podeu gaudir del joc!__

No us oblideu que podeu compartir el joc amb amics i familiars fent clic a __Comparteix__ al menú.
