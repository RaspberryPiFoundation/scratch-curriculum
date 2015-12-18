Nivel 1

#Caza de brujas

__Introducción:__
En este proyecto vamos a cazar unas brujas. Obtenés puntos al golpear a las brujas que aparecen en pantalla. ¡A ver cuántos puntos conseguís en 30 segundos!

##PASO 1: Creá una bruja voladora

1. Creá un proyecto de Scratch nuevo.
2. Borrá el objeto gato y cambiá el fondo del escenario al llamado 'nature/woods'.
3. Usá el botón 'Escoger un nuevo objeto desde archivo' para añadir una bruja con el disfraz 'fantasy/witch1'. 

Ahora queremos que la bruja se mueva.

4. Creá una nueva variable llamada 'velocidad'.
En el escenario aparecerá un recuadro llamado 'Objeto1 velocidad'.
Si sólo dice 'velocidad', borrá la variable y creala otra vez, pero sólo para este objeto. Después, quitá la marca de la casilla al lado de la palabra 'velocidad' en la paleta de Variables, para que desaparezca el recuadro del escenario.
Esta variable controla la velocidad de la bruja. Usamos una variable para poder cambiar su velocidad según avanza el juego.
5. Queremos que la bruja se mueva en cuanto empiece el juego; para ello, escribí este programa:

```scratch

	al presionar BANDERA

	fijar velocidad a 5

	por siempre

		mover velocidad pasos

	(acabar por siempre)
```
		
###Probá tu proyecto
__Hacé clic en la bandera verde__ y observá lo que hace la bruja. ¿Por qué se queda atascada en el borde de la pantalla?

6. Para evitar que la bruja se atasque tenemos que hacer que dé la vuelta al llegar al borde del escenario. Después del bloque 'mover velocidad pasos' agregá un 'rebotar si está tocando el borde'.

```scratch

	al presionar BANDERA

	fijar velocidad a 5

	por siempre

		mover velocidad pasos

		rebotar si está tocando el borde

	(acabar por siempre)
```
7. Para que la bruja no se ponga del revés, hacé clic en el botón __solo mirar izquierda-derecha__ en la zona de sumario del objeto.

###Probá tu proyecto
__Hacé clic en la bandera verde.__ 
¿Se mueve la bruja de lado a lado del escenario?

Guardá tu proyecto

###Cosas para probar
__Probá cambiar el valor de la variable 'velocidad' para que vuele más rápido o más despacio.__

__¿Cómo harías que la bruja acelere según va volando?__
(Esto es más difícil, no te preocupes si no ves cómo hacerlo. Te daremos más pistas durante el resto del proyecto.)

##PASO 2: Hacé que la bruja aparezca y desaparezca al azar

Para hacer el juego más divertido, queremos que la bruja aparezca y desaparezca al azar. Lo haremos con otro programa que se ejecuta a la vez que el que mueve a la bruja. Este nuevo programa esconde la bruja durante un tiempo, luego la muestra durante otro tiempo, y repite por siempre (o hasta que acabe el juego).

Creá este programa para la bruja:

```scratch

	al presionar BANDERA

	por siempre

		esconder

		esperar número al azar entre 2 y 5 segundos

		show

		esperar número al azar entre 3 y 5 segundos

	(acabar por siempre)
```
###Probá tu proyecto
__Hacé clic en la bandera verde.__ 
¿Se mueve la bruja de lado a lado del escenario, apareciendo y despareciendo al azar?

Guardá tu proyecto

###Cosas para probar
__Probá cambiar el rango de números. ¿Qué ocurre si escoges números muy grandes o muy pequeños?__
(¿Te da esto alguna pista para hacer que la bruja acelere según avanza el juego?)

##PASO 3: Hacé que la bruja desaparezca cuando alguien hace clic en ella

Para convertirlo en un juego, tenemos que darles algo que hacer a los jugadores. Tienen que cliquear en la bruja para hacerla desaparecer. Cuando se hace clic en la bruja, queremos que desaparezca y haga algún sonido.

1. En la pestaña de Sonidos, importá el sonido 'electronic/fairydust'.

2. Agregá este programa a la bruja:

```scratch

	al presionar Objeto1

	esconder

	tocar sonido Fairydust
```
###Probá tu proyecto
__Hacé clic la bandera verde.__ 

Cuando cliqueás la bruja, ¿desaparece y se oye el sonido?

Guardá tu proyecto

##PASO 4: Agregá un marcador y cronómetro

Tenemos una bruja, ¡hagamos un juego! Queremos que los jugadores reciban puntos cada vez que cliquean en la bruja, pero también queremos que la partida tenga un límite de tiempo. Usamos variables para el marcador y el cronómetro.


1. Creá una variable para todos los objetos llamada 'marcador', y cambia el programa de la bruja para incrementar esta variable cuando se hace clic.

```scratch

	al presionar Objeto1

	esconder

	tocar sonido Fairydust

	cambiar marcador por 1
```
2. Hacé clic en el escenario y crea una nueva variable (esta vez solo para el escenario) llamada 'tiempo'. Agregá un nuevo programa que actúe cuando alguien hace clic en la bandera verde, para fijar el tiempo a 30 y poner el marcador a 0. Usá un bloque de repetición para restarle 1 al tiempo cada segundo. Esto se repite hasta que el tiempo llegue a 0, cuando detenemos el juego.

```scratch

	al presionar BANDERA

	fijar tiempo a 30

	fijar marcador a 0

	repetir hasta que tiempo = 0

		esperar 1 segundos

		cambiar tiempo por -1

	(acabar repetir)

	detener todo
```


###Probá tu proyecto
__Hacé clic en la bandera verde.__ 

Guardá tu proyecto

###Cosas para probar
__¿Cómo harías que la bruja acelere según avanza la partida?__


__Bien hecho, has completado el juego básico. Hay más cosas que podés hacer con tu juego. ¿Te atrevés con este desafío?__

##Desafío: Agrega más brujas

¡Cuantas más brujas, mejor! Agreguemos dos brujas.
1. Duplicá la bruja haciendo clic en el objeto con el botón derecho.
2. Cambiá el tamaño de cada bruja.
3. Cambiá la variable 'velocidad' de cada bruja para que vuelen a distintas velocidades.
4. Cambiá la posición de cada bruja en el escenario para que no vuelen juntas.

###Probá tu proyecto
__Hacé clic en la bandera verde.__ 

¿Tenés tres brujas que se mueven independientemente de lado a lado de la pantalla, aparecen y desaparecen al azar, y desaparecen cuando hacés clic en ellas?

Guardá tu proyecto

###Cosas para probar
1. ¿Qué número de brujas es el ideal para este juego?
2. ¿Podés cambiar la apariencia de cada bruja? Podés editar sus disfraces, o experimentar con los bloques la paleta de Apariencia.
3. ¿Podés hacer que las brujas valgan más o menos puntos? ¿Quizás la bruja más pequeña y rápida debería valer 10 puntos?


__Bien hecho, has terminado, ahora podés disfrutar de tu juego.__
¡No olvides que podés compartir tu juego con tus amigos y familia haciendo clic en __Compartir__ en el menú!