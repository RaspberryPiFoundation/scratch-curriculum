Nivel 3

#Qué es eso

__Introducción__

Un objecto al azar aparece en la pizarra, completamente distorsionado. Tienes que adivinar qué es pinchando en la imagen correcta. Cuanto más rápido lo adivines, ¡más alta será tu puntuación!

##PASO 1: Haz que aparezcan cosas en la pizarra

Queremos que aparezcan algunas imágenes en la pizarra.

1. Crea un nuevo proyecto de Scratch y borra el objeto gato.
2. Pincha en el escenario y luego en la pestaña Fondos. Importa el fondo 'indoors/chalkboard' (que quiere decir 'interiores/pizarra').
3. Importa un nuevo objeto y ponle el disfraz que quieras. Puedes elegir alguno del directorio 'things'.
4. Posiciona el nuevo objeto en el medio de la pizarra. Si lo necesitas, puedes agrandarlo o achicarlo.
5. Pincha en la pestaña Disfraces e importa cuatro cosas más. ¡Pueden ser las que tú quieras!
Ahora hagamos que aparezca una imagen al azar.
6. Crea este programa:

```scratch

	al presionar BANDERA
	repetir número al azar entre 1 y 5		
		siguiente disfraz
	(fin repetir)
```

###Prueba tu proyecto
__Pincha en la bandera verde.__

¿El objeto muestra un disfraz distinto?

__Pínchala varias veces más.__

¿Ves distintos disfraces cada vez? A veces verás el mismo disfraz dos veces seguidas, pero esto es normal. También te vas a dar cuenta de que el objeto parpadea cuando cambia el disfraz. Vamos a arreglar eso en el paso siguiente.

##PASO 2: Distorsiona las imágenes

__Ahora hagamos que la imagen se distorsione cuando aparece, y que se vaya aclarando durante unos segundos.__

Vamos a usar una variable para controlar cuánta distorsión va a haber. Si el número es alto, habrá mucha distorsión. Si el número baja, habrá menos distorsión. El número puede actuar como contador de tiempo, como en la __Tarjeta de Scratch cronómetro__.

1. En la paleta de Variables, crea una variable llamada puntuación.

2. Cambia el programa para que se vea así:

```scratch

	al presionar BANDERA
	esconder
	repetir número al azar entre 1 y 5		
		siguiente disfraz
	(fin repetir)
	fijar puntuación a 110
	repetir hasta que puntuación = 0
		cambiar puntuación por -10
		fijar efecto pixelizar a puntuación
		fijar efecto color a puntuación
		mostrar
		esperar 1 segundos
	(fin repetir)
```

Tienes que añadir el bloque 'esconder' al principio, luego fijar la variable puntuación a 110 y todo lo que viene después.

###Prueba tu proyecto
__Pincha en la bandera verde.__

¿Aparece una imagen distorsionada?

¿La distorsión va desapareciendo poco a poco?

¿La puntuación baja a medida que la imagen se vuelve menos distorsionada?

¿La imagen se ve sin distorsión cuando la puntuación llega a cero?

¿Todavía tienes una imagen diferente cada vez que pinchas en el botón verde?

Guarda tu proyecto.

##Cosas para probar

__Prueba cambiando la puntuación inicial y cuánto cambia en cada ciclo.__ ¿Cómo cambia la apariencia de la imagen? ¿Hace más fácil o más difícil distinguir qué imagen es?

__Prueba con otros efectos gráficos.__ ¿Cómo cambian la dificultad del juego?

##PASO 3: Deja que el jugador adivine cuál es la imagen

Hasta aquí, hemos hecho que una imagen al azar aparezca lentamente y que la puntuación disminuya a medida que pasa el tiempo. Pero, ¿cómo se gana el juego? Vamos a añadir algunos objetos en la parte inferior de la pantalla para que el jugador pinche en ellos. Si pincha en el correcto, gana el juego. Si pincha en uno incorrecto, el objeto desaparece y el juego sigue.

Primero, necesitamos saber cuál es la respuesta correcta.

1. Crea una nueva variable llamada __respuesta__. Asegúrate de que sea para todos los objetos.
2. Cambia el programa que escribiste para que guarde la respuesta correcta. Añade el bloque 'fijar respuesta a # de disfraz' después del primer bloque 'repetir':

```scratch

	al presionar BANDERA
	esconder
	repetir número al azar entre 1 y 5			
		siguiente disfraz
	(fin repetir)
	fijar respuesta a # de disfraz
	fijar puntuación a 110
	repetir hasta que puntuación = 0
		cambiar puntuación por -10
		fijar efecto pixelizar a puntuación
		fijar efecto color a puntuación
		mostrar
		esperar 1 segundos
	(fin repetir)
```
__Ahora necesitamos añadir los objetos en los que el jugador va a poder pinchar.__

3. Duplica el objeto principal y arrastra el duplicado a la esquina inferior izquierda del escenario.
4. Renombra este objeto a __respuesta1__ (esto hará más fácil hablar de él).
5. Borra el programa de __respuesta1__ y todos sus disfraces excepto el primero.
6. Haz otra vez los últimos tres pasos, pero pon el objeto __respuesta2__ al lado de __respuesta1__ y borra todos los disfraces excepto el segundo.
7. Haz esto tres veces más para __respuesta3__, __respuesta4__ y __respuesta5__.

Acabarás con una fila de cinco objetos de "respuesta" a lo largo de la parte inferior del escenario, cada uno mostrando un disfraz distinto. __Ninguno de los objetos de respuesta debe tener programas__.

Ahora queremos que cada objeto responda al pinchar en él y haga algo dependiendo de si es o no la respuesta correcta.

8. Añade este programa al objeto respuesta1:

```scratch

	al presionar respuesta1
	si respuesta = 1
		enviar a todos gano
	si no
		esconder
	(fin si)
```
9. Arrastra este programa sobre de cada uno de los objetos de respuesta. __En cada objeto, cambia el 1 a 2, 3, y así sucesivamente__.
10. Ahora tenemos que añadir algo que muestre el mensaje de victoria. Vuelve al objeto1, el que está en la pizarra. Añade este programa extra:

```scratch

	al recibir gano
	decir unir ¡Felicitaciones! puntuación: puntuación
```

###Prueba tu proyecto
__Pincha en la bandera verde.__

Cuando pruebes tu juego, puedes usar el monitor de la variable __respuesta__ en el escenario para que te diga cuál es la respuesta correcta. Esto está bien para probar.

¿Qué pasa cuando pinchas en la __respuesta correcta__?

¿Qué pasa cuando pinchas en la __respuesta incorrecta__?

¿Qué pasa con la respuesta correcta cuando __comienza un nuevo juego__?

Las pruebas van a demostrar dos problemas. Primero, las respuestas incorrectas no vuelven a aparecer cuando comienza el nuevo juego. Segundo, la puntuación no deja de bajar cuando adivinas la respuesta correcta.

11. Para arreglar el primer problema, añade este programa a cada uno de los cinco objetos respuesta:

```scratch

	al presionar BANDERA
	mostrar
```

Para arreglar el segundo problema, necesitamos detener la repetición del ciclo del __objeto pregunta__ cuando el jugador pincha en la respuesta correcta. Vamos a usar una nueva variable para hacerlo. Vamos a ponerla a __cero__ cuando el juego comienza y luego la pondremos a __uno__ cuando el jugador haya ganado. Vamos a hacer que el ciclo __repetir hasta__ se detenga cuando la puntuación alcance __cero__ o la variable __gano?__ se ponga a __uno__.

12. Crea una nueva variable llamada __gano?__
13. Modifica los programas para que queden así:

```scratch

	al presionar BANDERA
	esconder
	repetir número al azar entre 1 y 5			
		siguiente disfraz
	(fin repetir)
	fijar respuesta a # de disfraz
	fijar puntuación a 110
	fijar gano? a 0
	repetir hasta que puntuación = 0 o gano? = 1
		cambiar puntuación por -10
		fijar efecto pixelizar a puntuación
		fijar efecto color a puntuación
		mostrar
		esperar 1 segundos
	(fin repetir)
	
	al recibir gano
	fijar gano? en 1
	quitar efectos gráficos
	decir unir ¡Felicitaciones! puntuación: puntuación
```

Guarda tu proyecto.

__Bien hecho, ¡has creado el juego básico!__

Hay algunas cosas más que puedes hacer con tu juego. ¡Acepta estos desafíos!

##Desafío 1: Haz el juego más fácil o más difícil

Cambia la dificultad del juego.

* Intenta cambiar la velocidad a la que la imagen es revelada y la puntuación baja.
* Intenta cambiar las distorsiones de la imagen.
* Intenta cambiar las imágenes a adivinar, para hacerlas más similares o más diferentes. Si lo haces, no olvides cambiar el disfraz del objeto respuesta.

Guarda tu proyecto.

##Desafío 2: Distorsiona la imagen de forma diferente en cada juego

Por el momento, cada ronda del juego usa la misma distorsión. En el Paso 2 probaste varios tipos diferentes de distorsiones que funcionaban tan bien como el color y la pixelación que usamos.

Encuentra otras distorsiones que vayan bien.

Cambia el juego de modo que cada jugada use una distorsión diferente en el ciclo __repetir hasta__.

__Pista:__ Prueba creando una nueva variable llamada __distorsion_a_usar__. Fíjala a un valor al azar al inicio del juego. Usa bloques __si__ en el cuerpo del ciclo __repetir hasta__ para aplicar la distorsión correcta al juego.

Guarda tu proyecto.

##Desafío 3: Haz que el juego tenga varias rondas

Por el momento, cada juego es independiente. Cámbialo para que tenga varias rondas. Por ejemplo, que tenga tres rondas, de modo que el jugador tenga que adivinar tres imágenes y sumar hasta 300 puntos.

__Pista:__ Vas a necesitar una variable extra para guardar el total de todas las rondas. También vas a necesitar un ciclo para pasar de ronda a ronda.

__Pista:__ Podrías hacer que cada respuesta incorrecta reaparezca al comienzo de cada ronda. ¿Quizás mandando un mensaje?

Guarda tu proyecto.

##Desafío 4: Haz que cada ronda sea más difícil

A medida que el jugador vaya avanzando de ronda, el juego debe volverse más difícil.

¿Tiene que calcularse igual la puntuación en todas las rondas? ¿Deberían valer más puntos las rondas más difíciles?

__Pista:__ ¿Cómo sabes en qué ronda estás? ¿Cómo puedes usar eso para cambiar la dificultad y la puntuación?

Guarda tu proyecto.

##Desafío 5: Sigue jugando hasta que el jugador se equivoque

En lugar de usar un número fijo de rondas, sigue jugando hasta que el jugador no adivine una imagen. Esto probablemente sólo funcionará si el juego se vuelve más difícil a medida que se avanza de ronda.

Guarda tu proyecto.

##Desafío 6: Haz el juego más fácil o más difícil dependiendo del éxito del jugador

En lugar de siempre hacer el juego más difícil, haz que el juego ajuste la dificultad dependiendo de la habilidad del jugador. Si adivina una imagen rápido, haz que la próxima sea un poquito más difícil. Si no adivina la imagen, o tarda mucho en adivinar, haz que la próxima ronda sea un poquito más fácil.

Esta idea sólo funciona bien si no sumas la puntuación entre rondas.

Guarda tu proyecto.

##Desafío 7: Mantén la puntuación más alta

Mantén un registro de cuál es la puntuación más alta. Si alguien la supera, pregúntale su nombre y actualiza la puntuación más alta. Asegúrate de que la puntuación y el nombre de la persona se muestren.

Guarda tu proyecto.

##Desafío 8: Haz que las respuestas incorrectas salgan caras

Hasta ahora no se penaliza a los que pinchan en las imágenes lo más rápido que pueden. Cambia el juego para que la puntuación baje un poquito cada vez que el jugador elige una respuesta incorrecta.

¿Esto mejora el juego?

Guarda tu proyecto.

__Bien hecho, hemos terminado. ¡Ahora a disfrutar de tu juego!__
No olvides que puedes compartir tu juego con amigos y familia pinchando en __Compartir__ en el menú.