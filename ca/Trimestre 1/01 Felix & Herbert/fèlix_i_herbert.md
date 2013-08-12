Nivell 1

#Fèlix i Herbert

__Introducció:__
Construirem un joc on __el gat Fèlix__ i el ratolí __Herbert__ jugen a atrapar. Vosaltres controlareu en Herbert amb el ratolí i hey d'intentar evitar que en Fèlix us atrapi. Quant més temps eviteu que us atrapi més punts guanyareu, però no us deixeu agafar perquè perdreu punts!

##PAS 1: En Fèlix segueix el punter del ratolí

1. Creeu un nou projecte.
2. Feu doble clic al escenari i canvieu a la pestanya dels Fons, llavors seleccioneu el fons indoors/hall. Suprimiu el fons blanc original.
3. Canvieu el nom del objecte per Fèlix. 
4. Assegureu-vos que en Fèlix només miri a esquerra i dreta prement aquest botó:
5. Creeu aquest programa:

```scratch
	Al prémer Senyera verda
	per sempre
		apunta cap a punter del ratolí
		mou-te 10 passos
		següent vestit
		toca el tambor 62 durant 0.3
	(fi del per sempre)
```
		
###Proveu el projecte
__Feu clic a la senyera de color verd.__
En Fèlix, segueix el punter del ratolí? Quan es mou, us sembla com si caminés? Es mou a una velocitat adequada?

Deseu el projecte

##PAS 2: En Fèlix persegueix en Herbert

__A continuació volem que en Fèlix persegueixi en Herbert, enlloc del punter del ratolí.__

1. Create another sprite using the choose new sprite from file button and selecting animals/mouse1.
2. Canvieu el nom del objecte per Herbert.
3. Editeu la disfressa i feu-la més petita que la de'n Fèlix.
Proveu fent 6 clics al botó d'reduir.
4. Assegureu-vos que en Herbert només miri a esquerra i dreta.
5. Doneu-li aquest programa a en Herbert:


```scratch
	
	Al prémer Senyera verda
	per sempre
		vés a punter del ratolí
		apunta cap a Fèlix
	(fi del per sempre)
´´´

###Proveu el projecte
__Feu clic a la senyera de color verd.__

En Herbert, segueix el punter del ratolí? En Fèlix persegueix al Herbert?

Deseu el projecte.

##PAS 3: En Fèlix diu quan ha atrapat en Herbert

__Volem que en Fèlix sàpiga quan ha atrapat en Herbert i que ens ho digui.__

1. Modifiqueu el programa de'n Felix així:

´´´scratch
	
	Al prémer Senyera verda
	per sempre
		apunta cap al punter del ratolí
		mou-te 10 passos
		següent vestit
		toca el tambor 62 durant 0.3
		si tocant Herbert
			envia caught! durant 1 segon
		(fi del si)
	(fi del per sempre)
´´´

###Proveu el projecte
__Feu clic a la senyera de color verd.__

En Fèlix diu quan ha atrapat en Herbert?

Deseu el projecte.

##PAS 4: En Herbert es converteix en un fantasma quan l'atrapen

__Enlloc de que en Fèlix digui quelcom, volem que en Herbert es converteixi en un fantasma quan l'atrapin.__

1. Canvieu el programa de'n Fèlix per tal d'enviar aquest missatge quan atrapi en Herbert.

```scratch
	
	Al prémer la Senyera verda
	per sempre
		apunta cap al punter del ratolí
		mou-te 10 passos
		següent vestit
		toca el tambor 62 durant 0.3
		si tocant Herbert
			envia a tots caught
			toca el tambor 58 durant 0.2
			espera 1 segon
		(fi del si)
	(fi del per sempre)
´´´
2. Importeu una nova disfressa per en Herbert de fantasy/ghost2-a.
3. Editeu la disfresa per fer-la més petita.
N'hi hauria d'haver prou amb sis clics al botó d'reduir.
4. Canvieu els noms de les disfresses de'n Herbert de manera que la disfressa de ratolí s'anomeni 'alive' i la de fantasma s'anomeni 'dead'.
5. Creeu un nou programa per tal de convertir en Herbert en un fantasma:

```scratch
	
	al rebre caught
	canvia el vestit a dead
	espera 0.5 segons
	canvia el vestit a alive
´´´	
###Proveu el projecte
__Feu clic a la senyera de color verd.__

Quan atrapeu en Herbert, es converteix en un fantasma?
En Fèlix fa els sons adequats en cada moment?
En Fèlix roman quiet prou temps per a que en Herbert es pugui escapar?

Deseu el projecte

##PAS 5: Actualitzar el marcador

__Afegirem un marcador de manera que sabrem com de bé mantenim al Herbert en vida.
Començarem amb el marcador a zero i l'incrementarem una unitat cada segon. Si en Fèlix atrapa en Herbert, reduirem el marcador en cent unitats.__

1. Creeu una variable per a tots els objectes i anomeneu-la Marcador. Feu clic a Variables en el menu de dalt, creeu una variable i anomeneu-la Marcador.

2. Creeu aquests dos progrmaes a l'escenari

```scratch
	
	Al prémer Senyera verda
	fixa score a 0
	per sempre
		suma 1 a score
		espera 1 segon
	(fi del per sempre)
		
	al rebre caught
	suma -100 a score
´´´
###Proveu el projecte
__Feu click a la senyera de color verd.__

Cada segon que passa el marcador augmenta una unitat?
Quan en Fèlix atrapa en Herbert el marcador disminueix cent unitats?
Què passa quan atrapeu en Herbert abans que el marcador arrivi a cent unitats? 
Quan comenceu una nova partida, el marcador torna a zero?

Deseu el projecte

__Molt bé, heu acabat. Ara ja podeu gaudir del joc!__

No us oblideu que podeu compartir el joc amb amics i familiars fent clic a __Compartir__ al menú.