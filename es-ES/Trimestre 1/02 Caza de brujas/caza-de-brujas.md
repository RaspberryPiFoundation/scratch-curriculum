Nivel 1

#Caza de brujas

__Introducción:__
En este proyecto vamos a cazar unas brujas. Obtienes puntos al golpear a las brujas que aparecen en pantalla. ¡A ver cuántos puntos consigues en 30 segundos!
##PASO 1: Crea una bruja voladora
1. Crea un proyecto de Scratch nuevo.2. Borra el objeto gato y cambia el fondo del escenario al llamado 'nature/woods'.3. Usa el botón 'Escoger un nuevo objeto desde archivo' para añadir una bruja con el disfraz 'fantasy/witch1'. 
Ahora queremos que la bruja se mueva.

4. Crea una nueva variable llamada 'velocidad'.En el escenario aparecerá un recuadro llamado 'Objeto1 velocidad'.
Si solo dice 'velocidad', borra la variable y créala otra vez, pero solo para este objeto. Después, quita la marca de la casilla al lado de la palabra 'velocidad' en la paleta de Variables, para que desaparezca el recuadro del escenario.
Esta variable controla la velocidad de la bruja. Usamos una variable para poder cambiar su velocidad según avanza el juego.5. Queremos que la bruja se mueva en cuanto empiece el juego; para ello, escribe este programa:

```scratch
	al presionar BANDERA
	fijar velocidad a 5
	por siempre
		mover velocidad pasos
	(acabar por siempre)
```		
###Prueba tu proyecto__Pincha en la bandera verde__ y observa lo que hace la bruja. ¿Por qué se queda atascada en el borde de la pantalla?
6. Para evitar que la bruja se atasque tenemos que hacer que de la vuelta al llegar al borde del escenario. Después del bloque 'mover velocidad pasos' añade un 'rebotar si está tocando el borde'.
```scratch
	al presionar BANDERA
	fijar velocidad a 5
	por siempre
		mover velocidad pasos
		rebotar si está tocando el borde
	(acabar por siempre)
```7. Para que la bruja no se ponga del revés, pincha el botón __solo mirar izquierda-derecha__ en la zona de sumario del objeto.

###Prueba tu proyecto__Pincha en la bandera verde.__ 
¿Se mueve la bruja de lado a lado del escenario?

Guarda tu proyecto

###Cosas para probar__Prueba cambiar el valor de la variable 'velocidad' para que vuele más rápido o más despacio.____¿Cómo harías que la bruja acelere según va volando?__
(Esto es más difícil, no te preocupes si no ves cómo hacerlo. Te daremos más pistas durante el resto del proyecto.)##PASO 2: Haz que la bruja aparezca y desaparezca al azar
Para hacer el juego más divertido, queremos que la bruja aparezca y desaparezca al azar. Lo haremos con otro programa que se ejecuta a la vez que el que mueve a la bruja. Este nuevo programa esconde la bruja durante un tiempo, luego la muestra durante otro tiempo, y repite por siempre (o hasta que acabe el juego).
Crea este programa para la bruja:
```scratch
	al presionar BANDERA
	por siempre
		esconder
		esperar número al azar entre 2 y 5 segundos
		show
		esperar número al azar entre 3 y 5 segundos
	(acabar por siempre)
```
###Prueba tu proyecto__Pincha en la bandera verde.__ 
¿Se mueve la bruja de lado a lado del escenario, apareciendo y despareciendo al azar?

Guarda tu proyecto

###Cosas para probar__Prueba cambiar el rango de números. ¿Qué ocurre si escoges números muy grandes o muy pequeños?__(¿Te da esto alguna pista para hacer que la bruja acelere según avanza el juego?)##PASO 3: Haz que la bruja desaparezca cuando alguien pincha en ella
Para convertirlo en un juego, tenemos que darles algo que hacer a los jugadores. Tienen que pinchar en la bruja para hacerla desaparecer. Cuando se Pincha en la bruja, queremos que desaparezca y haga algún sonido.
1. En la pestaña de Sonidos, importa el sonido 'electronic/fairydust'.
2. Añade este programa a la bruja:
```scratch
	al presionar Objeto1
	esconder
	tocar sonido Fairydust
```
###Prueba tu proyecto__Pincha en la bandera verde.__ 
Cuando pinchas en la bruja, ¿desaparece y se oye el sonido?
Guarda tu proyecto
##PASO 4: Añade un marcador y cronómetro
Tenemos una bruja, ¡hagamos un juego! Queremos que los jugadores reciban puntos cada vez que pinchan en la bruja, pero también queremos que la partida tenga un límite de tiempo. Usamos variables para el marcador y el cronómetro.
1. Crea una variable para todos los objetos llamada 'marcador', y cambia el programa de la bruja para incrementar esta variable cuando se pincha en ella.
```scratch
	al presionar Objeto1

	esconder

	tocar sonido Fairydust
	cambiar marcador por 1
```2. Pincha en el escenario y crea una nueva variable (esta vez solo para el escenario) llamada 'tiempo'. Añade un nuevo programa que actúa cuando alguien pincha en la bandera verde, para fijar el tiempo a 30 y poner el marcador a 0. Usa un bloque de repetición para restarle 1 al tiempo cada segundo. Esto se repite hasta que el tiempo llegue a 0, cuando detenemos el juego.
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
###Prueba tu proyecto__Pincha en la bandera verde.__ 
Guarda tu proyecto

###Cosas para probar__¿Cómo harías que la bruja acelere según avanza la partida?__
__Bien hecho, has completado el juego básico. Hay más cosas que puedes hacer con tu juego. ¿Te atreves con este desafío?__
##Desafío: Añade más brujas
¡Cuantas más brujas, mejor! Añadamos dos brujas.1. Duplica la bruja pinchando en el objeto con el botón derecho.2. Cambia el tamaño de cada bruja.3. Cambia la variable 'velocidad' de cada bruja para que vuelen a distintas velocidades.
4. Cambia la posición de cada bruja en el escenario para que no vuelen juntas.
###Prueba tu proyecto__Pincha en la bandera verde.__ 

¿Tienes tres brujas que se mueven independientemente de lado a lado de la pantalla, aparecen y desaparecen al azar, y desaparecen cuando pinchas en ellas?
Guarda tu proyecto
###Cosas para probar1. ¿Qué número de brujas es el ideal para este juego?2. ¿Puedes cambiar la apariencia de cada bruja? Puedes editar sus disfraces, o experimentar con los bloques la paleta de Apariencia.3. ¿Puedes hacer las brujas valgan más o menos puntos? ¿Quizás la bruja más pequeña y rápida debería valer 10 puntos?
__Bien hecho, has terminado, ahora puedes disfrutar de tu juego.__¡No olvides que puedes compartir tu juego con tus amigos y familia pinchando en __Compartir__ en el menú!