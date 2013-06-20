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
###Prueba tu proyecto__Pincha la bandera verde__ y observa lo que hace la bruja. ¿Por qué se queda atascada en el borde de la pantalla?
6. Para evitar que la bruja se atasque tenemos que hacer que de la vuelta al llegar al borde del escenario. Después del bloque 'mover velocidad pasos' añade un 'rebotar si está tocando el borde'.
```scratch
	al presionar BANDERA
	fijar velocidad a 5
	por siempre
		mover velocidad pasos
		rebotar si está tocando el borde
	(acabar por siempre)
```7. Para que la bruja no se ponga del revés, pincha el botón __solo mirar izquierda-derecha__ en la zona de sumario del objeto.

###Prueba tu proyecto__Pincha la bandera verde.__ 
¿Se mueve la bruja de lado a lado del escenario?

Guarda tu proyecto

###Cosas para brobar__Prueba cambiar el valor de la variable 'velocidad' para que vuele más rápido o más despacio.____¿Cómo harías que la bruja acelere según va volando?__
(Esto es más difícil, no te preocupes si no ves cómo hacerlo. Te daremos más pistas durante el resto del proyecto.)##PASO 2: Haz que la bruja aparezca y desaparezca al azar
Para hacer el juego más divertido, queremos que la bruja parezca y desparezca al azar. Lo haremos con otro programa que se ejecuta a la vez que el que mueve a la bruja. Este nuevo programa esconde la bruja durante un tiempo, luego la muestra durante otro tiempo, y repite por siempre (o hasta que acabe el juego).
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
###Prueba tu proyecto__Pincha la bandera verde.__ 
¿Se mueve la bruja de lado a lado del escenario, apareciendo y despareciendo al azar?

Guarda tu proyecto

###Cosas para brobar__Prueba cambiar el rango de números. ¿Qué ocurre si escoges números muy grandes o muy pequeños?__(¿Te da esto alguna pista para hacer que la bruja acelere según avanza el juego?)##PASO 3: Haz que la bruja desaparazce cuando alguien pincha en ella
Para convertirlo en un juego, tenemos que darle algo que hacer al jugador. Tiene que 
1. In the Sounds tab, import the sound electronic/fairydust. 
2. Add this script to the witch:
```scratch
	when sprite1 clicked
	hide
	play sound Fairydust
```
###Prueba tu proyecto__Pincha la bandera verde.__ 
Does the witch disappear and play the sound when you click it?
Guarda tu proyecto
##PASO 4: Add a score and timer
We’ve got a witch, but now we want to make a game! We want to score points every time we click on the witch but we also want to have a time limit on the game. We can use a variable for the score and the timer.
1. Create a new Variable for all sprites called score, and alter the script for the witch to increase this variable by one when she is clicked.
```scratch
	when sprite1 clicked
	hide
	play sound Fairydust
	change score by 1
```2. Switch to the Stage and create a new variable (this time just for the stage) called timer. Add a new script that occurs when the green flag is clicked to set timer to 30 and reset the score to 0. Then use a repeat until block to wait a second and then reduce timer byone. This should repeat until timer is 0, at which point use stop all to stop the game.
```scratch
	al presionar BANDERA
	set timer to 30
	set score to 0
	repeat until timer = 0
		wait 1 secs
		change timer by -1
	(end repeat)
	stop all
```
###Prueba tu proyecto__Pincha la bandera verde.__ 
Guarda tu proyecto

###Cosas para brobar__How might you make the witch speed up as the game goes on?__
__Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at this challenge!__
##Challenge: add more witches
If one witch is good, more must be better! Let’s have three witches flying around.1. Duplicate the witch by right-clicking it in the sprite list.2. For each witch adjust the size of the sprite so the witches are different sizes.3. For each witch change the speed variable so that they fly at different speeds.4. Move the witches around the canvas so that they are not all together.
###Prueba tu proyecto__Pincha la bandera verde.__ 
Do you have three witches that move from side to side across the screen, randomly appear and disappear, and disappear when you click on them?
Guarda tu proyecto
###Cosas para brobar1. How many witches is a good number for the game?￼￼2. Can you make the witches look different? You could either edit their costumes, or use some blocks from the Looks palette to change them.3. Can you make the witches be worth different points? How about making the fastest (and smallest) witch worth 10 points?
__Well done you’ve finished, now you can enjoy the game!__Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!