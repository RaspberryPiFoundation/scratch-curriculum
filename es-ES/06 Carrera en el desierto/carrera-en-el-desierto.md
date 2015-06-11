Nivel 2

#Carrera en el desierto

__Introducción:__
Este es un juego para dos jugadores en el que compiten un loro y un león a través del desierto. Cada jugador pulsa una tecla lo más rápido posible para mover a su animal; el primero en llegar al borde de la pantalla gana.

##PASO 1: Crea la escena y añade los objetos

1. Pincha en el escenario y añade el escenario 'nature/desert'.
2. Añade un nuevo objeto, seleccionando la imagen del león en el fichero 'animals'.
3. Añade otro objeto con la imagen del loro.



##PASO 2: Haz que el león y el loro se muevan


Queremos que el objeto se mueva cuando pulsamos una tecla.


1. Selecciona el león y haz que se mueva 4 pasos cuando se pulsa la tecla 'L'.

```scratch

	al presionar tecla l
	mover 4 pasos
```

2. Después, selecciona el loro y haz que se mueva 4 pasos cuando se pulsa la tecla 'A'.

```scratch

	al presionar tecla a
	mover 4 pasos
```

###Prueba tu proyecto
__Pincha en la bandera verde__ 
¿Se mueven el león y el loro cuando pulsas las teclas 'A' y 'L'?

Guarda tu proyecto


##PASO 3: Comienza la carrera

Necesitamos alguna forma de comenzar la carrera y saber quién ha ganado. __Primero vamos a crear un botón de inicio.__

1. Añade un nuevo objeto desde archivo. Elige la imagen 'things/button'.
2. Edita el disfraz de ese nuevo objeto, añade el texto 'inicio' y pincha en 'Aceptar'. Coloca el botón en el centro del escenario.
3. Ahora añade el programa que muestra el botón cuando empieza el juego.

```scratch

	al presionar BANDERA
	mostrar
```
4. Queremos que al pulsar el botón, haga una cuenta atrás desde 3, luego diga 'YA!' y se esconda. Añade otro programa así:

```scratch

	al presionar inicio
	decir 3 por 1 segundos
	decir 2 por 1 segundos
	decir 1 por 1 segundos
	decir YA! por 1 segundos
	esconder
```
###Prueba tu proyecto
__Pincha en la bandera verde.__

Cuando pinchas el botón de inicio, ¿hace la cuenta atrás antes de desaparecer?

Guarda tu proyecto

Queremos que los competidores solo se muevan una vez que haya empezado la carrera, y queremos saber cuándo ha acabado la carrera: necesitamos una variable para mantener esa información.

5. Añade una variable llamada 'corriendo' para todos los objetos. Despeja su casilla para que no aparezca en el escenario.
6. Haz que 'corriendo' tenga el valor 0 cuando comienza el juego por primera vez. Cambia el programa `al presionar BANDERA` de antes a:

```scratch

	al presionar BANDERA
	mostrar
	fijar corriendo a 0
```
7. Dale el valor 1 a 'corriendo' cuando acaba la cuenta atrás.
8. Ahora tenemos que evitar que el león y el loro se muevan hasta que la variable tenga el valor 1. Pincha en el loro. __Añade un bloque de control al programa__ que solo le permite moverse si __corriendo = 1__.

```scratch

	al presionar tecla a
	si corriendo = 1
		mover 4 pasos
	(fin si)
```
9. Haz lo mismo con el león.

###Prueba tu proyecto
__Pincha en la bandera verde.__

¿Se mueven los animales solo después de acabar la cuenta atrás?

Queremos saber quién ha ganado cada carrera y volver al inicio para poder competir de nuevo.

##PASO 4: Termina la carrera

1. Añade un bloque al programa del loro que cambia la variable 'corriendo' a 0 cuando el objeto toca el borde de la pantalla.

```scratch

	al presionar tecla a
	si corriendo = 1
		mover 4 pasos
		si ¿tocando borde?
			fijar corriendo a 0
		(fin si)
	(fin si)
```
2. Ahora queremos que el loro nos avise si gana la carrera. Graba un nuevo sonido que sonará si el loro gana. ¡Pincha en la pestaña 'Sonidos' y graba el sonido que hará el loro al ganar la carrera!
3. Añade los bloques que tocan el sonido y hacen que el loro diga que ha ganado:

```scratch

	al presionar tecla a
	si corriendo = 1
		mover 4 pasos
		si ¿tocando borde?
			fijar corriendo a 0
			tocar sonido grabación1
			decir ¡el loro gana! por 3 segundos
		(fin si)
	(fin si)
```
4. Ahora repite estos pasos para el león.

###Prueba tu proyecto
__Pincha en la bandera verde.__

¿Puedes presionar el botón de inicio y comenzar a correr presionando las teclas 'A' y 'L'?
¿Al acabar la carrera, el ganador anuncia que ha ganado y se oye su sonido?

Guarda tu proyecto

##PASO 5: Reinicia el juego

Tenemos que avisar a los competidores cuando acaba la carrera y reiniciar el juego para poder competir de nuevo.

__El ganador tiene que enviar un mensaje anunciando su victoria.__

1. Pincha el loro.
Añade un bloque que envía el mensaje 'fin' para avisar de que ha ganado.

```scratch

	al presionar tecla a
	si corriendo = 1
		mover 4 pasos
		si ¿tocando borde?
			fijar corriendo a 0
			tocar sonido grabación1
			decir ¡el loro gana! por 3 segundos
			enviar a todos fin
		(fin si)
	(fin si)
```
2. Tenemos que añadir un programa que espera recibir el mensaje 'fin' y devuelve al loro a la salida. ¿Qué pasa si cambias el valor que le das a x?

```scratch

	al recibir fin
	fijar x a -175
```
3. Ahora añade el mismo programa al león. Intenta con distintos valores de x para asegurarte de que el león y el loro estén alineados en la salida.
4. También queremos que el león y el loro estén alineados al principio del programa, así que añade otro programa que los mueva a esa posición cuando pinchamos en la bandera verde.

```scratch

	al presionar BANDERA
	fijar x a -175
```
5. Pincha en el botón de inicio y añade un programa que lo muestra cuando recibe el mensaje 'fin'.

###Prueba tu proyecto
__Pincha en la bandera verde.__


¿Puedes competir con tus amigos y amigas, con uno de vosotros moviendo el loro pulsando la tecla 'A' y el otro moviendo el león pulsando la tecla 'L'?

Guarda tu proyecto

##Desafío: Añade un turbo

* __Intenta añadir un turbo__ que se puede disparar una vez por carrera y que haga saltar al animal __30 pasos de un tirón.__
* __Añade un nuevo disfraz__ con fuego saliendo por detrás del animal, y haz que aparezca cuando se pulsa el turbo.
* __Crea otro sonido__ que sonará cuando se dispara el turbo.

###Prueba tu proyecto

Guarda tu proyecto


__Bien hecho, hemos terminado. ¡Ahora a disfrutar de tu juego!__
No olvides que puedes compartir tu juego con amigos y familiares pinchando en __Compartir__ en el menú.
