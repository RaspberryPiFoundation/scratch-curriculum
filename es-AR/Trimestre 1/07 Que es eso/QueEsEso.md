Nivel 3

#Qué es eso

__Introducción__

Un objecto al azar es mostrado en el pizarrón, todo distorsionado. Tenés que adivinar qué es cliqueando en la imagen de la derecha, a continuación. Mientras más rápido lo adivines, ¡más alto será tu puntaje!

##PASO 1: Hacé que aparezcan cosas en el pizarrón

Queremos que aparezcan algunas imágenes en el pizarrón.

1. Creá un nuevo proyecto de Scratch y borrá el objeto gato.
2. Hacé clic en Escenario y luego en la pestaña Fondos. Importá el fondo "chalkboard" (que quiere decir "pizarrón") que está en la categoría "Interiores".
3. Importá un nuevo objeto y ponele el disfraz que quieras. Podés elegir cualquiera de la categoría "Cosas".
4. Posicioná el nuevo objeto en el medio del pizarrón. Si lo necesitás, podés hacerlo más grande o más chico.
5. Hacé clic en la pestaña Disfraces e importá cuatro cosas más. ¡Puede ser lo que vos quieras!
Ahora hagamos que aparezca una imagen al azar.
6. Creá este script:

```scratch

	al presionar BANDERA
	repetir número al azar entre 1 y 5		
		siguiente disfraz
	(fin repetir)
```

###Probá tu proyecto
__Hacé clic en la bandera verde.__

¿El objeto muestra un disfraz distinto?

__Clickealo varias veces más.__

¿Ves distintos disfraces cada vez? A veces vas a ver el mismo difraz dos veces seguidas, pero esto es normal. También te vas a dar cuenta que el objeto parpadea cuando cambia el disfraz. Vamos a arreglar eso en el paso siguiente.

##PASO 2: Distorsionar las imágenes

__Ahora hagamos que la imagen se distorsione cuando aparece, y que se aclare después de unos segundos.__

Vamos a usar una variable numérica para controlar cuánta distorsión va a haber. Si el número es alto, habrá mucha distorsión. Si el número baja, habrá menos y menos distorsión. El número puede actuar como contador de tiempo, como en la __Tarjeta de Scratch Timer__.

1. En la paleta Variables, crear una variable llamada Puntos.

2. Cambiá el script para que se vea así:

```scratch

	al presionar BANDERA
	esconder
	repetir número al azar entre 1 y 5		
		siguiente disfraz
	(fin repetir)
	set score to 110
	repeat until score = 0
		change score by -10
		set pixelate effect to score
		set colour effect to score
		show
		wait 1 secs
	(end repeat)
```

Tenés que agregar el bloque esconder arriba y luego poner el bloque puntaje a 110, y todo lo que viene después.

###Probá tu proyecto
__Hacé clic en la bandera verde.__

¿Aparece una imagen distorsionada?

¿La distorsión va desapareciendo de a poco?

¿El puntaje baja a medida que la imagen se vuelve menos distorsionada?

¿La imagen aparece sin distorsión cuando el puntaje llega a cero?

¿Todavía tenés una imagen diferente cada vez que hacés clic en el botón verde?

Guardá tu proyecto.

##Cosas para probar

__Probá cambiando el puntaje inicial y cuánto cambia cada vez durante el ciclo.__ ¿Qué pasa con cómo se ve la imagen? ¿Hace más fácil o más difícil darse cuenta qué imagen es?

__Probá con otros efectos gráficos.__ ¿Cómo cambian la dificultad del juego?

##PASO 3: Dejá que el jugador adivine cuál es la imagen

Hasta acá, hicimos que una imagen al azar aparezca lentamente y que el puntaje disminuya a medida que pasa el tiempo. Pero, ¿cómo se gana el juego? Vamos a agregar algunos objetos al final de la pantalla para que el jugador haga clic en ellos. Si hace clic en el correcto, gana el juego. Si hace clic en uno incorrecto, el objeto desaparece y el juego sigue.

Primero, necesitamos saber cuál es la respuesta correcta.

1. Creá una nueva variable llamada __respuesta__. Asegurate que sea para todos los objetos.
2. Cambiá el script que escribiste para que guarde la respuesta correcta. Agregá los bloques set [answer] to costume # después del primer ciclo repetir:

```scratch

	al presionar BANDERA
	esconder
	repeat pick random 1 to 5		
		next costume
	(end repeat)
	set answer to costume
	set score to 110
	repeat until score = 0
		change score by -10
		set pixelate effect to score
		set colour effect to score
		show
		wait 1 secs
	(end repeat)
```
__Ahora necesitamos agregar los objetos en los que el jugador va a poder hacer clic.__

3. Duplicá el objeto principal y arrastrá el duplicado a la esquina inferior izquierda del escenario.
4. Renombrá este objeto a __respuesta1__ (esto hará más fácil hablar de él).
5. Borrá el script de __answer1__ y todos sus disfraces excepto el primero.
6. Hacé otra vez los últimos tres pasos, pero poné el objeto __respuesta2__ al lado de __respuesta1__ y borrá todos los disfraces excepto el segundo.
7. Hacé esto tres veces más para __respuesta3__, __respuesta4__ y __respuesta5__.

Debes terminar con una fila de cinco objetos de respuesta a lo largo de la parte inferior del escenario, cada uno mostrando un disfraz distinto. __Ninguno de los objetos de respuesta debe tener scripts__.

Ahora queremos que cada objeto responda al ser cliqueado y haga algo dependiendo de si es o no la respuesta correcta.

8. Agregá este script al objeto respuesta1:

```scratch

	when answer1 clicked
	if answer=1
		broadcast won
	else
		hide
	(end if)
```
9. Arrastrá este script dentro de cada uno de los objetos de respuesta. __En cada objeto, cambiá el 1 a 2, 3, y así sucesivamente__.
10. Ahora tenemos que agregar algo que muestre el mensaje ganador. Volvé al objeto1, el que está en el pizarrón. Agregá este script extra:

```scratch

	when I receive won
	say join Congratulations! You scored score
```

###Prueba tu proyecto
__Hacé click en la bandera verde.__

Cuadno pruebes tu juego, podés usar el __answer monitor__ en el escenario para que te diga cuál es la respuesta correcta. Esto está bien para probar.

¿Qué pasa cuando clickeás en la _respuesta correcta__?

¿Qué pasa cuando clickeás en la __respuesta incorrecta__?

¿Qué pasa con la respuesta correcta cuando __comienza un nuevo juego__?

Las pruebas van a mostrar dos problemas. Primero, las respuestas incorrectas no vuelven a aparecer cuando comienza el nuevo juego. Segundo, el puntaje no deja de bajar cuando adivinás la respuesta correcta.

11. Para arreglar el primer problema, agregá este script a cada uno de los cinco objetos respuesta:

```scratch

	when FLAG clicked
	show
```

Para arreglar el segundo problema, necesitamos detener la repetición del ciclo del __objeto pregunta__ cuando el jugador hace clic en la respuesta correcta. Vamos a usar una nueva variable para hacerlo. Vamos a ponerla en __cero__ cuando el juego comienza y luego la pondremos en __uno__ cuando el jugador haya ganado. Vamos a hacer que el ciclo repetir hasta se detenga cuando el puntaje alcance __cero__ o la __bandera juego-ganado__ se ponga en __uno__.

12. Creá una nueva variable llamada gano?
13. Cambiá los scripts para que queden así:is:

```scratch

	when FLAG clicked
	hide
	repeat pick random 1 to 5		
		next costume
	(end repeat)
	set answer to costume
	set score to 110
	set won to 0
	repeat until score = 0 or won? =1
		change score by -10
		set pixelate effect to score
		set colour effect to score
		show
		wait 1 secs
	(end repeat)
	
	When I receive won
	set won to 1
	clear graphics effects
	say join Congratulations! You scored score
```

Guardá tu proyecto.

__Cuando termines, ¡vas a haber hecho un juego básico!__

Hay algunas cosas más que podés hacer con tu juego. ¡Tomá estos desafíos!

##Desafío 1: Hacé el juego más fácil o más difícil

Cambiá la dificultad es el juego.

* Intentá cambiar qué tan rápido la imagen es revelada y qué tan rápido el puntaje baja.
* Intentá cambiar las distorsiones de la imagen.
* Intentá cambiar las imagenes a adivinar, para hacerlas más similares o más diferentes. Si lo hacés, no olvides cambiar el disfraz del objeto respuesta.

Guardá tu proyecto.

##Desafío 2: Distorsioná la imagen de forma diferente en cada juego

Por el momento, cada fase del juego usa la misma distorsión. En el Paso 2, probaste varios tipos diferentes de distorsiones que anda bie ncon el color y la pixelación que usamos.

Encontrá otras distorsiones que anden bien.

Cambiá el juego de modo que cada jugada use una distorsión diferente en el ciclo repetir hasta.

__Pista:__ Probá creando una nueva variable llamada distorsion a usar. Fijala a un valor al azar al inicio del juego. Usá bloques si en el cuerpo del ciclo repetir hasta para aplicar la distorsión correcta al juego.

Guardá tu proyecto.

##Challenge 3: Make a game have a few rounds

At the moment, each game is independent. Change it so that the game proceeds in several rounds. For instance, have one game take three rounds, so the player has to guess three pictures and can score up to 300 points.

__Hint:__ You’ll need an extra variable to store the grand total across all the rounds. You’ll also need a loop to go through the different rounds.

__Hint:__ You’ll also have to make the wrong guesses reappear at the start of each round. Perhaps you could use a broadcast message to do that?

Save your project

##Challenge 4: Make later rounds more difficult

As you go through different rounds, make the game harder each time.

Does each round need to score the same? Should you get more points for guessing quickly in the later, more difficult rounds?

__Hint:__ How will you know which round you’re in? How can you use that to change the difficulty and the score?

Save your project

##Challenge 5: Keep playing until the player gets it wrong

Instead of using a fixed number of rounds, keep playing the game until the player doesn’t get a picture right. This probably only works if the game gets harder in later rounds.

Save your project

##Challenge 6: Make the game harder or easier depending on how well the player does

Rather than always making the game harder, make the game adjust the difficulty depending on the skill of the player. If they get the right picture quickly, make the next game a bit harder. If they don’t get the right picture, or only get it late, make the next game a bit easier.

This idea only really works if you don’t add up someone’s score over several rounds.

Save your project

##Challenge 7: Keep track of the highest score

Keep track of the highest score. If someone manages to beat it, ask for their name and update the highest score. Make sure the highest score, and the name of the person who scored it, are displayed.

Save your project


##Challenge 8: Make wrong guesses expensive

At the moment, there’s no penalty to just clicking on all the answer sprites as quickly as you can. Change the game so that the score goes down a bit every time you make an incorrect guess.

Does this make the game better?

Save your project


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!