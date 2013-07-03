Nivel 3

#Qué es eso

__Introducción__

Un objecto al azar es mostrado en el pizarrón, todo distorsionado. Tenés que adivinar qué es cliqueando en la imagen de la derecha, a continuación. Mientras más rápido lo adivines, ¡más alto será tu puntaje!

##PASO 1: Hacé que aparezcan cosas en el pizarrón

Queremos que aparezcan algunas imágenes en el pizarrón.

1. Creá un nuevo proyecto de Scratch y borrá el objeto gato.
2. Hacé clic en Escenario y luego en la pestaña Fondos. Importá el fondo "chalkboard" (que quiere decir "pizarrón") que está en la categoría "Interiores".
3. Importá un nuevo objeto y ponele el disfraz que quieras. Podés elegir cualquiera de la categoría "Cosas".
4. Posicioná el nuevo objeto en el medio del pizarrón. Si lo necesitás, podés agrandarlo o achicarlo.
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

¿Ves distintos disfraces cada vez? A veces vas a ver el mismo difraz dos veces seguidas, pero esto es normal. También te vas a dar cuenta de que el objeto parpadea cuando cambia el disfraz. Vamos a arreglar eso en el paso siguiente.

##PASO 2: Distorsionar las imágenes

__Ahora hagamos que la imagen se distorsione cuando aparece, y que se aclare después de unos segundos.__

Vamos a usar una variable numérica para controlar cuánta distorsión va a haber. Si el número es alto, habrá mucha distorsión. Si el número baja, habrá menos distorsión. El número puede actuar como contador de tiempo, como en la __Tarjeta de Scratch Contador de Tiempo__.

1. En la paleta Datos, crear una variable llamada puntos.

2. Cambiá el script para que se vea así:

```scratch

	al presionar BANDERA
	esconder
	repetir número al azar entre 1 y 5		
		siguiente disfraz
	(fin repetir)
	fijar puntos a 110
	repetir hasta que puntos = 0
		cambiar puntos por -10
		establecer efecto pixelizar a puntos
		establecer efecto color a puntos
		mostrar
		esperar 1 segundos
	(fin repetir)
```

Tenés que agregar la palabra esconder al principio, luego fijar la variable puntos en 110 y todo lo que viene después.

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
2. Cambiá el script que escribiste para que guarde la respuesta correcta. Agregá la sentencia fijar respuesta a # de disfraz después del primer ciclo repetir:

```scratch

	al presionar BANDERA
	esconder
	repetir número al azar entre 1 y 5			
		siguiente disfraz
	(fin repetir)
	fijar respuesta a # de disfraz
	fijar puntos a 110
	repetir hasta que puntos = 0
		cambiar puntos por -10
		establecer efecto pixelizar a puntos
		establecer efecto color a puntos
		mostrar
		esperar 1 segundos
	(fin repetir)
```
__Ahora necesitamos agregar los objetos en los que el jugador va a poder hacer clic.__

3. Duplicá el objeto principal y arrastrá el duplicado a la esquina inferior izquierda del escenario.
4. Renombrá este objeto a __respuesta1__ (esto hará más fácil hablar de él).
5. Borrá el script de __respuesta1__ y todos sus disfraces excepto el primero.
6. Hacé otra vez los últimos tres pasos, pero poné el objeto __respuesta2__ al lado de __respuesta1__ y borrá todos los disfraces excepto el segundo.
7. Hacé esto tres veces más para __respuesta3__, __respuesta4__ y __respuesta5__.

Tenés que terminar con una fila de cinco objetos de "respuesta" a lo largo de la parte inferior del escenario, cada uno mostrando un disfraz distinto. __Ninguno de los objetos de respuesta debe tener scripts__.

Ahora queremos que cada objeto responda al ser cliqueado y haga algo dependiendo de si es o no la respuesta correcta.

8. Agregá este script al objeto respuesta1:

```scratch

	al presionar respuesta1
	si respuesta = 1
		enviar a todos gano
	si no
		esconder
	(fin si)
```
9. Arrastrá este script dentro de cada uno de los objetos de respuesta. __En cada objeto, cambiá el 1 a 2, 3, y así sucesivamente__.
10. Ahora tenemos que agregar algo que muestre el mensaje ganador. Volvé al objeto1, el que está en el pizarrón. Agregá este script extra:

```scratch

	al recibir gano
	decir unir ¡Felicitaciones! Puntos: puntos
```

###Probá tu proyecto
__Hacé click en la bandera verde.__

Cuando pruebes tu juego, podés usar el monitor de la variable __respuesta__ en el escenario para que te diga cuál es la respuesta correcta. Esto está bien para probar.

¿Qué pasa cuando clickeás en la _respuesta correcta__?

¿Qué pasa cuando clickeás en la __respuesta incorrecta__?

¿Qué pasa con la respuesta correcta cuando __comienza un nuevo juego__?

Las pruebas van a evidenciar dos problemas. Primero, las respuestas incorrectas no vuelven a aparecer cuando comienza el nuevo juego. Segundo, el puntaje no deja de bajar cuando adivinás la respuesta correcta.

11. Para arreglar el primer problema, agregá este script a cada uno de los cinco objetos respuesta:

```scratch

	al presionar BANDERA
	mostrar
```

Para arreglar el segundo problema, necesitamos detener la repetición del ciclo del __objeto pregunta__ cuando el jugador hace clic en la respuesta correcta. Vamos a usar una nueva variable para hacerlo. Vamos a ponerla en __cero__ cuando el juego comienza y luego la pondremos en __uno__ cuando el jugador haya ganado. Vamos a hacer que el ciclo repetir hasta se detenga cuando el puntaje alcance __cero__ o la __bandera gano?__ se ponga en __uno__.

12. Creá una nueva variable llamada __gano?__
13. Modificá los scripts para que queden así:

```scratch

	al presionar BANDERA
	esconder
	repetir número al azar entre 1 y 5			
		siguiente disfraz
	(fin repetir)
	fijar respuesta a # de disfraz
	fijar puntos a 110
	fijar gano? a 0
	repetir hasta que puntos = 0 o gano? = 1
		cambiar puntos por -10
		fijar efecto pixelizar a puntos
		fijar efecto color a puntos
		mostrar
		esperar 1 segundos
	(fin repetir)
	
	al recibir gano
	fijar gano? en 1
	quitar efectos gráficos
	decir unir ¡Felicitaciones! Puntos: puntos
```

Guardá tu proyecto.

__Cuando termines, ¡vas a haber hecho un juego básico!__

Hay algunas cosas más que podés hacer con tu juego. ¡Aceptá estos desafíos!

##Desafío 1: Hacé el juego más fácil o más difícil

Cambiá la dificultad es el juego.

* Intentá cambiar qué tan rápido la imagen es revelada y qué tan rápido el puntaje baja.
* Intentá cambiar las distorsiones de la imagen.
* Intentá cambiar las imagenes a adivinar, para hacerlas más similares o más diferentes. Si lo hacés, no olvides cambiar el disfraz del objeto respuesta.

Guardá tu proyecto.

##Desafío 2: Distorsioná la imagen de forma diferente en cada juego

Por el momento, cada fase del juego usa la misma distorsión. En el Paso 2 probaste varios tipos diferentes de distorsiones que andan bien con el color y la pixelación que usamos.

Encontrá otras distorsiones que anden bien.

Cambiá el juego de modo que cada jugada use una distorsión diferente en el ciclo __repetir hasta__.

__Pista:__ Probá creando una nueva variable llamada __distorsion_a_usar__. Fijala a un valor al azar al inicio del juego. Usá bloques __si__ en el cuerpo del ciclo __repetir hasta__ para aplicar la distorsión correcta al juego.

Guardá tu proyecto.

##Desafío 3: Hacé que el juego tenga varias rondas

Por el momento, cada juego es independiente. Cambiá eso así el juego tiene varias rondas. Por ejemplo, que el juego tenga tres rondas, de modo que el jugador tenga que adivinar tres imagenes y sumar hasta 300 puntos.

__Pista:__ Vas a necesitar una variable extra para guardar el gran total de todas las rondas. También vas a necesitar un ciclo para ir por cada ronda.

__Pista:__ Podrías hacer que cada respuesta incorrecta reaparezca al comienzo de cada ronda. Quizás podrías enviar un mensaje para hacer eso.

Guardá tu proyecto.

##Desafío 4: Hacé que las rondas siguientes sean más difíciles

A medida que el jugador vaya avanzando de ronda, el juego debe volverse más difícil.

¿En cada ronda se tienen que calcular igual los puntos? ¿Deberían valer más puntos las rondas más difíciles?

__Pista:__ ¿Cómo sabés en qué ronda estás? ¿Cómo podés usar eso para cambiar la dificultad y el puntaje?

Guardá tu proyecto.

##Desafío 5: Seguí jugando hasta que el jugador se equivoque

En lugar de usar un número fijo de rondas, seguí jugando hasta que el jugador no adivine una imagen. Esto probablemente sólo funcione si el juego se vuelve difícil a medida que se avanza de ronda.

Guardá tu proyecto.

##Desafío 6: Hacé el juego más fácil o más difícil dependiendo de qué tan bien le va al jugador

En lugar de siempre hacer el juego más difícil, hacé que el juego ajuste la dificultad dependiendo de la habilidad del jugador. Si adivina una imagen rápido, hacé que el próximo sea un poquito más difícil. Si no adivina la imagen, o sólo lo hace lento, hacé que la próxima ronda sea un poquito más fácil.

La idea sólo funciona realmente si no sumás los puntos entre rondas.

Guardá tu proyecto.

##Desafío 7: Mantené el puntaje más alto

Mantené el registro de cuál es el puntaje más alto. Si alguien lo supera, preguntale su nombre y actualizá el puntaje más alto. Asegurate que el puntaje y el nombre de la persona se muestren.

Guardá tu proyecto.

##Desafío 8: Hacé que las respuestas incorrectas sean caras

Por el momento, no se penaliza a los que cliquean en las imágenes lo más rápido que puedan. Cambiá el juego así el puntaje baja un poquito cada vez que el jugador elige una respuesta incorrecta.

¿Esto mejora el juego?

Guardá tu proyecto.

__Bien hecho, hemos terminado. ¡Ahora a disfrutar de tu juego!__
No olvides que podés compartir tu juego con amigos y familiares haciendo clic en __Compartir__ en el menú.