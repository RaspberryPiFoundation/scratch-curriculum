Nivel 2

#Rescata regalos

__Introducción:__
__En este proyecto vamos a crear un juego con fondo en movimiento, un marcador y un mensaje navideño al final.__
Un accidente en la fábrica de juguetes ha hecho volar todos los juguetes por los aires. ¡Ayuda al reno Rudolph a salvar la navidad rescatando los regalos!

##PASO 1: Haz volar a Rudolph

1. Comienza un nuevo proyecto de Scratch. Borra el objeto gato pinchándolo con el botón derecho y pinchando 'borrar'.
2. Reemplaza el fondo con SkyBackground.png.
3. Pincha en __Escoger un nuevo objeto desde archivo__ y añade el objeto Rudolph al proyecto usando el archivo __Rudolph.png__.
4. Cámbiale el nombre al objeto a __Rudolph__.
5. Haz que Rudolph siga al puntero del ratón con este programa:


```scratch
al presionar BANDERA
enviar al frente
por siempre
	ir a apuntador del ratón
(fin por siempre)
```

###Prueba tu proyecto

__Pincha en la bandera verde y mueve el ratón__, ¿sigue Rudolph al ratón?

6. Vamos a hacer el juego más interesante añadiendo montes nevados que se muevan para que parezca que Rudolph está volando. Pincha en __Escoger un nuevo objeto desde archivo__ y añade el objeto Nieve al proyecto usando el archivo __SnowHills.png__.
7. Cámbiale el nombre al objeto a __Nieve1__.
8. Crea una nueva variable pinchando en 'Variables' y luego en 'Nueva variable'. Dale el nombre ScrollX, márcala 'para todos los objetos' y despeja su casilla para que no aparezca en el escenario. Esta variable controlará cómo se mueven los montes.
9. Añade este programa para hacer que se muevan los montes:

```scratch
al presionar BANDERA
fijar y a 0
por siempre
	fijar x a ScrollX
	cambiar ScrollX por -1
	si ScrollX < -480
		fijar ScrollX a 0
	(fin si)
(fin por siempre)
```

###Prueba tu proyecto

__Pincha en la bandera verde__, ¿se mueven los montes? ¿Qué ocurre cuando los montes llegan al borde del escenario?

10 Vamos a arreglar el problema de los montes que saltan cuando llegan al borde del escenario, añadiendo más montes pinchando en __Escoger un nuevo objeto desde archivo__ y añadiendo un segundo objeto usando el archivo __SnowHills.png__.
11 Cámbiale el nombre al objeto a __Nieve2__.
12 Añade este programa a __Nieve2__ para que el segundo grupo de montes vaya pegado al primero:

```scratch
al presionar BANDERA
fijar y a 0
por siempre
	fijar x a ScrollX + 479
(fin por siempre)
```

###Prueba tu proyecto

__Pincha en la bandera verde__, ¿se mueven los montes? ¿Se ha arreglado el problema de los montes que saltaban?

__Guarda tu proyecto__

##PASO 2: Regalos que caen

1. Vamos a añadir los regalos que van a caer para que Rudolph los recoja. Pincha en __Escoger un nuevo objeto desde archivo__ y añade el objeto __Regalo__ usando el archivo __Present.png__.
2. Cámbiale el nombre al objeto a __Regalo__.
3. Crea una nueva variable pinchando en 'Variables' y luego en 'Nueva variable'. Dale el nombre __Parar__, márcala 'para este objeto' y despeja su casilla para que no aparezca en el escenario. Usaremos esta variable para controlar cuándo desaparece el regalo.
4. Crea otra nueva variable. Dale el nombre __Velocidad__, márcala 'para este objeto' y despeja su casilla para que no aparezca en el escenario. Ésta controlará la velocidad a la que cae el regalo.
5. Añade este programa al objeto __Regalo__ para hacerlo caer del cielo. Verás que usaremos números al azar para que el regalo aparezca cada vez en un punto distinto.
6. Usando el comando __¿tocando Rudolph?__ haremos que el regalo desparezca cuando Rudolph lo atrapa, y así mantenemos el marcador más tarde.


```scratch
al presionar BANDERA
por siempre
	fijar Parar a 0
	ir a x: número al azar entre -230 y 230 y: número al azar entre 50 y 170
	fijar Velocidad a -1
	repetir hasta que Parar = 1
		cambiar y por Velocidad
		si posición en y de Regalo < -160
			fijar Parar a 1
		(fin si)
		si ¿tocando Rudolph?
			fijar Parar a 1
		(fin si)
	(fin repetir)
(fin por siempre)
```

###Prueba tu proyecto

__Pincha en la bandera verde,__ ¿caen los regalos del cielo? ¿Desaparecen cuando Rudolph los toca o cuando llegan al suelo?

7 Hagámoslo más interesante cambiando el color de cada regalo. Lo hacemos usando el comando __cambiar efecto color__.
8 Cambia la velocidad de cada regalo fijando la Velocidad a un número al azar en vez de siempre a -1. Prueba distintas velocidades.


```scratch
al presionar BANDERA
por siempre
	fijar Parar a 0
	ir a x: número al azar entre -230 y 230 y: número al azar entre 50 y 170
	cambiar efecto color por número al azar entre 1 y 100
	fijar Velocidad a número al azar entre -10 y -1
	repetir hasta que Parar = 1
		cambiar y por Velocidad
		si posición en y de Regalo < -160
			fijar Parar a 1
		(fin si)
		si ¿tocando Rudolph?
			fijar Parar a 1
		(fin si)
	(fin repetir)
(fin por siempre)
```

###Prueba tu proyecto
__Pincha en la bandera verde,__ ¿tiene cada regalo un color y una velocidad distintos?

##PASO 3: Marcador y efectos de sonido

1. __Cambiemos el programa para mantener la puntuación durante el juego.__ Entonces podremos utilizar el marcador para decidir cuándo termina el juego y aparece el mensaje navideño.
2. Crea una nueva variable pinchando en 'Variables'. Llámala __Puntos__ y márcala 'para todos los objetos'. Deja la casilla marcada para que aparezca en pantalla.
3. Cambia el programa del objeto __Regalo__ como aparece a continuación. Fíjate en que hemos añadido efectos de sonido con el comando `tocar tambor` y también hacemos `cambiar Puntos por 1` cuando Rudolph toca el regalo.


```scratch
al presionar BANDERA
por siempre
	fijar Parar a 0
	ir a x: número al azar entre -230 y 230 y: número al azar entre 50 y 170
	cambiar efecto color por número al azar entre 1 y 100
	fijar Velocidad a número al azar entre -10 y -1
	repetir hasta que Parar = 1
		cambiar y por Velocidad
		si posición en y de Regalo < -160
			tocar tambor 57 durante 0.2 pulsos
			fijar Parar a 1
		(fin si)
		si ¿tocando Rudolph?
			tocar tambor 39 durante 0.2 pulsos
			cambiar Puntos por 1
			fijar Parar a 1
		(fin si)
	(fin repetir)
(fin por siempre)
```

4 Añádele música al juego importando el sonido __Jingle_Bells.mp3__ para el __Escenario__.

```scratch
al presionar BANDERA
fijar ScrollX a 0
fijar Puntos a 0
tocar sonido Jingle_Bells
```

5 Añade este programa al __Escenario__ para reiniciar el marcador de 0 cuando comienza el juego. También tocará la música durante todo el juego.

Nota: si la música suena entrecortada, prueba guardar el proyecto, cerrar Scratch y volver a abrir el proyecto.

###Prueba tu proyecto

__Pincha en la bandera verde,__ ¿cambia el marcador cuando Rudolph toca cada regalo?

__Guarda tu proyecto__

##PASO 4: Fin del juego

1. __Vamos a cambiar el programa para alertar cuando se llega a una cierta puntuación.__ Luego usaremos esta alerta para mostrar el mensaje al final del juego.
2. Cambia el programa del __Escenario__ para que cuando el marcador llega a 10 enviamos a todos un mensaje __Fin__.

```scratch
al presionar BANDERA
fijar ScrollX a 0
fijar Puntos a 0
tocar sonido Jingle_Bells
por siempre 
	si Puntos = 10
		enviar a todos GameOver y esperar
	(fin si)
(fin por siempre)
```

3. Ahora añadimos el mensaje del fin del juego. Pincha en __Escoger un nuevo objeto desde archivo__ y añade el objeto __Fin__ al proyecto usando el archivo __GameOver.png__.
4. Cámbiale el nombre al objeto a __Fin__.
5. __Añádele este programa__ que `esconde` la imagen cuando comienza el juego y la `muestra` cuando se recibe el mensaje __Fin__.


```scratch
al presionar BANDERA
esconder

al recibir Fin
enviar al frente
mostrar
detener todo
```

###Prueba tu proyecto

__Pincha en la bandera verde,__ ¿aparece el mensaje navideño al final del juego?

__Guarda tu proyecto__

##Desafío: Hazlo más difícil

* ¿Puedes hacer que los regalos se tambaleen al caer por la pantalla?
* ¿Puedes hacer que haya más de un regalo a la vez en pantalla?
* Cambia el mensaje del fin del juego para que aparezca después de rescatar 20 regalos.
* ¿Puedes cambiar el marcador para que pierda 1 punto por cada regalo que caiga al suelo?

__Bien hecho, hemos terminado. ¡Ahora a disfrutar de tu juego!__
¡Te deseamos una feliz navidad!
