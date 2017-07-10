---
title: alón Prisionero
description: Create a platform game, in which you have to dodge the moving balls and reach the end of the level.
layout: project
notes: "Dodgeball - notes.md"
---

# Introducción { .intro }

En este proyecto aprenderás a crear un juego de plataformas en el que tendrás que esquivar balones en movimiento y llegar al final del nivel.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/39740618/?autostart=false" frameborder="0"></iframe>
  <img src="dodge-final.png">
</div>

# Paso 1: Movimientos del personaje { .activity }

Empezaremos por crear un personaje que pueda moverse hacia la derecha y la izquierda, y que pueda subirse a postes.

## Lista de tareas de la actividad { .check }

+ Crea un nuevo proyecto de Scratch y borra el objeto gato para que el proyecto esté vacío. Puedes encontrar el editor online de Scratch en <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Para este proyecto, deberías de tener una carpeta llamada 'Recursos del Proyecto', en la que encontrarás la imagen de fondo que necesitas. Asegúrate de que tienes esta carpeta, y pregunta al líder del Club si no la encuentras.

	![screenshot](images/dodge-resources.png)

+ Carga la imagen 'background.png' como nuevo escenario. ¡También puedes añadir un dibujo que hayas hecho tú! Si vas a dibujar tu propio nivel, asegúrate de que los postes y las plataformas son de colores diferentes, y de que haya una puerta (o algo parecido) a la que el jugador tenga que llegar. Tu proyecto debería parecerse a éste:

	![screenshot](images/dodge-background.png)

+ Añade un nuevo objeto, que será tu personaje. Es mejor que escojas un objeto que tenga varios disfraces, así podrás crear el efecto de que está caminando.

	![screenshot](images/dodge-characters.png)

+ Usaremos las flechas del teclado para que el personaje se mueva en diferentes direcciones. Cuando el jugador pulse la flecha derecha, queremos que el personaje mire hacia la derecha, dé unos pasos en esa dirección y cambie al siguiente disfraz:

	```blocks
		al presionar bandera verde
		por siempre
			si <¿tecla [flecha derecha v] presionada?> entonces
				apuntar en dirección (90 v)
				mover (3) pasos
				siguiente disfraz
			fin
		fin
	```

+ Haz una prueba presionando la bandera y a continuación manteniendo pulsada la tecla derecha. ¿Se mueve el personaje hacia la derecha? ¿Parece que el personaje está caminando?

	![screenshot](images/dodge-walking.png)

+ Para que el personaje se mueva hacia la izquierda, tendrás que añadir otro bloque `si` {.blockcontrol} dentro del bucle `por siempre` {.blockcontrol}. ¡Recuerda probar el nuevo código para asegurarte de que funciona!

+ Para subirse a un poste, tu personaje debería moverse un poco hacia arriba siempre que se pulse la flecha arriba y esté tocando el color correcto. Añade este código al bucle `por siempre` {.blockcontrol} de tu personaje:

	```blocks
		si <<¿tecla [flecha arriba v] presionada?> y <¿tocando el color [#FFFF00]?>> entonces
			cambiar y por (4)
		fin
	```

+ Prueba los movimientos de tu personaje: ¿Puedes subirte a los postes amarillos y llegar al final del nivel?

	![screenshot](images/dodge-test-character.png)

## Guarda tu proyecto { .save }

## Reto: Acabar el nivel {.challenge}
¿Puedes añadir más código al personaje, para que diga algo `si` {.blockcontrol} llega a la puerta marrón?

![screenshot](images/dodge-win.png)

## Guarda tu proyecto { .save }

# Paso 2: Gravedad y saltos { .activity }

Vamos a hacer que tu personaje se mueva de forma más realista añadiendo gravedad y haciendo que pueda saltar.

## Lista de tareas de la actividad { .check }

+ Puede que te hayas fijado en que tu personaje puede salirse de las plataformas y quedarse suspendido en medio del aire. Intenta salirte de una plataforma a ver qué pasa.

	![screenshot](images/dodge-no-gravity.png)

+ Para arreglar esto, vamos a añadir gravedad al juego. Crea una nueva variable con el nombre `gravedad` {.blockdata}. Si quieres, puedes esconder esta variable del escenario.

	![screenshot](images/dodge-gravity.png)

+ Añade este nuevo bloque de código, que fija la gravedad en un número negativo, y de esta manera cambia la coordenada y del personaje continuamente.

	```blocks
		al presionar bandera verde
		fijar [gravedad v] a [-4]
		por siempre
			cambiar y por (gravedad)
		fin
	```

+ Presiona la bandera y arrastra a tu personaje hasta la parte superior del escenario. ¿Qué ocurre? ¿La gravedad funciona como esperabas?

	![screenshot](images/dodge-gravity-drag.png)

+ ¡La gravedad no debería hacer caer a tu personaje de las plataformas o de un poste! Añade un bloque `si` {.blockcontrol} al código para que la gravedad sólo funcione cuando el personaje esté en medio del aire. El código de gravedad debería ser así:

	```blocks
		al presionar bandera verde
		fijar [gravedad v] a [-4]
		por siempre
			si <no <<¿tocando el color [#0000FF]?> o <¿tocando el color [#FFFF00]?>>> entonces
				cambiar y por (gravedad)
			fin
		fin
	```

+ Prueba la gravedad otra vez. ¿Se cae tu personaje cuando está en una plataforma o en un poste? ¿Puedes dejarte caer del borde de las plataformas al nivel inferior?

	![screenshot](images/dodge-gravity-test.png)

+  También vamos a hacer que tu personaje salte cuando el jugador pulse la tecla de espacio. Una forma muy sencilla de hacer esto es mover al personaje hacia arriba unas cuantas veces, usando este código:

	```blocks
		al presionar tecla [espacio v]
		repetir (10)
			cambiar y por (4)
		fin
	```

	Como la gravedad está constantemente empujando a tu personaje 4 píxeles hacia abajo, necesitarás indicar un número superior a 4 en el bloque `cambiar y por (4)` {.blockmotion}. Cambia el número hasta que te parezca bien la altura a la que el personaje salta.

+ Si pruebas este código verás que funciona bien, pero el movimiento no es demasiado fluido. Para que los saltos parezcan más naturales, tendrás que mover al personaje en cantidades cada vez más pequeñas, hasta que deje de saltar.

+ Para conseguir esto, crea otra variable llamada `altura de salto` {.blockdata}. De nuevo, puedes esconder esta variable si lo prefieres.

+ Elimina el código de salto que has añadido a tu personaje, y sustitúyelo por éste:

	```blocks
		al presionar tecla [espacio v]
		fijar [altura de salto v] a [8]
		repetir hasta que <(altura de salto) = [0]>
			cambiar y por (altura de salto)
			cambiar [altura de salto v] por (-0.5)
		fin
	```

	Este código hace que el personaje se mueva hacia arriba 8 píxeles, después 7,5 píxeles, después 7 píxeles, y así hasta que el personaje acabe de saltar. Esto hará que el salto parezca mucho más fluido.

+ Cambia el valor de inicio de la variable `altura de salto` {.blockdata} y prueba hasta que te parezca bien la altura a la que el personaje salta.

## Guarda tu proyecto { .save }

## Reto: Salto mejorado {.challenge}

Has conseguido que el personaje salte cada vez que se presiona la tecla de espacio, incluso si está en medio del aire. Puedes hacer una prueba manteniendo pulsada la tecla de espacio. ¿Puedes arreglar esto, para que el personaje sólo pueda saltar `si` {.blockcontrol} está tocando una plataforma azul?

## Guarda tu proyecto { .save }

# Paso 3: Esquivar los balones { .activity .new-page}

Ahora que has conseguido que el personaje se mueva, vamos a añadir los balones que el personaje tendrá que esquivar.

## Lista de tareas de la actividad { .check }

+ Crea un nuevo objeto balón. Puedes escoger el tipo de balón que más te guste.

	![screenshot](images/dodge-balls.png)

+ Cambia el tamaño del balón para que el personaje pueda saltar por encima de él. Intenta saltar sobre el balón para probarlo.

	![screenshot](images/dodge-ball-resize.png)

+ Añade este código al balón:

	![screenshot](images/dodge-ball-motion.png)

	Este código crea un nuevo clon del balón cada 3 segundos. Cada nuevo balón se desplaza a lo largo de la plataforma superior.

+ Presiona la bandera para probar el código.

	![screenshot](images/dodge-ball-test.png)

+ Añade más código al objeto balón para que los balones se muevan a lo largo de las tres plataformas.

	![screenshot](images/dodge-ball-more-motion.png)

+ Para terminar, ¡necesitarás código para cuando un balón toque al personaje! Añade este código al objeto balón:

	```blocks
		al comenzar como clon
		por siempre
			si <¿tocando [Pico walking v]?> entonces
				enviar [tocado v]
			fin
		fin
	```

+ También tendrás que añadir este código al personaje, para que vuelva al principio cuando un balón le toque:

	```blocks
		al recibir [tocado v]
		apuntar en dirección (90 v)
		ir a x:(-210) y:(-120)
	```

+ Haz una prueba con el personaje para ver si vuelve al principio cuando un balón le toca.

## Guarda tu proyecto { .save }

## Reto: Balones aleatorios {.challenge}
Todos los balones que tu personaje tiene que esquivar son iguales, y siempre aparecen cada 3 segundos. Intenta mejorar los balones, para que:

+ no sean todos iguales
+ aparezcan después de un tiempo aleatorio
+ sean de tamaño aleatorio

![screenshot](images/dodge-ball-random.png)

## Guarda tu proyecto { .save }

# Paso 4: ¡Láseres! { .activity .new-page}

¡Vamos a añadir láseres para que sea un poco más difícil acabar el juego !

## Lista de tareas de la actividad { .check }

+ Añade un nuevo objeto al juego, con el nombre 'Láser'. Debería tener 2 disfraces, llamados 'on' y 'off'.

	![screenshot](images/dodge-lasers-costume.png)

+ Coloca tu nuevo láser donde quieras, entre dos plataformas.

	![screenshot](images/dodge-lasers-position.png)

+ Añade código al láser para que cambie entre los dos disfraces.

	```blocks
		al presionar bandera verde
		por siempre
			cambiar disfraz a [on v]
			esperar (2) segundos
			cambiar disfraz a [off v]
			esperar (2) segundos
		fin
	```

	Si lo prefieres, puedes `esperar` {.blockcontrol} un tiempo `al azar` {.blockoperators} entre el cambio de disfraces.

+ Para finalizar, añade código al láser para que el mensaje 'tocado' se envíe cuando el láser toque al personaje. Este código es el mismo que el que has añadido al objeto balón.

	No necesitas añadir más código al personaje, ¡ya sabe lo que tiene que hacer cuando algo le toca!

+ Prueba el juego para ver si eres capaz de pasar a través del láser. Cambia los tiempos en el código `esperar` {.blockcontrol} si los láseres son demasiado fáciles o difíciles.

## Reto: Más obstáculos {.challenge}
Si todavía crees que el juego es demasiado fácil, puedes añadir más obstáculos al nivel. Puedes añadir cualquier cosa, pero te damos algunas ideas:

+ Una mariposa voladora asesina;
+ Plataformas que aparecen y desaparecen;
+ Pelotas de tenis que caen y que el personaje debe evitar.

![screenshot](images/dodge-obstacles.png)

Incluso podrías crear más de un fondo, y hacer que el personaje pase al siguiente nivel cuando llega a la puerta marrón:

```blocks
	si <¿tocando el color [#714300]?> entonces
		cambiar fondo a [siguiente fondo v]
		ir a x:(-210) y:(-120)
		esperar (1) segundos
	fin
```

## Guarda tu proyecto { .save }

## Reto: Gravedad mejorada {.challenge}
Hay otro pequeño error en el juego: la gravedad no funciona si _cualquier_ parte de tu personaje está tocando una plataforma azul, ¡incluso su cabeza!. Puedes comprobarlo si haces subir al personaje casi hasta arriba de un poste y después lo mueves hacia la izquierda.

![screenshot](images/dodge-gravity-bug.png)

¿Puedes arreglar este error? Para hacerlo, tienes que cambiar el color de los pantalones del personaje (en _todos_ los disfraces)...

![screenshot](images/dodge-trousers.png)

...y a continuación sustituir el código:

```blocks
	< ¿tocando el color [#0000FF]? >
```

por:

```blocks
	< ¿color [#00FF00] tocando [#0000FF]? >
```

¡Recuerda probar estas mejoras para asegurarte de que has arreglado el error!

## Guarda tu proyecto { .save }

## Reto: Más vidas {.challenge}
¿Puedes dar al jugador 3 `vidas` {.blockdata}, en lugar de simplemente devolverlo al principio cada vez? El juego podría funcionar así:

+ El jugador empieza con 3 vidas;
+ Cuando algo toca al jugador, pierde una vida y vuelve al principio;
+ Si no le quedan vidas, el juego acaba.

## Guarda tu proyecto { .save }

## Community Contributed Translation { .challenge .pdf-hidden }

This project was translated by Montse Verdaguer. Our amazing translation volunteers help us give children around the world the chance to learn to code.  You can help us reach more children by translating a Code Club project via [Github](https://github.com/CodeClub/curriculum_documentation/blob/master/contributing.md) or by getting in touch with us at hello@codeclubworld.
