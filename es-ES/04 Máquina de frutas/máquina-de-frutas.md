Nivel 2

#Máquina de frutas

__Introducción:__
Este juego muestra tres objetos que cambian de disfraz. Debes intentar detenerlos cuando coincidan en la misma imagen (¡como una máquina tragaperras!).

##PASO 1: Crea un objeto que cambia de disfraces

__Vamos a importar las distintas imágenes del juego__

1. Comienza un proyecto de Scratch nuevo. Borra el objeto gato pinchando en él con el botón derecho y pinchando en 'borrar'.
2. Importa un nuevo objeto.
3. Elige cualquier imagen. Aquí hemos usado 'things/bananas1', pero puedes usar cualquier imagen que quieras.
4. Pincha en la pestaña 'Disfraces' e importa dos imágenes más, para tener un total de tres (hemos usado 'animals/bee1' y 'things/lego', pero elige las que prefieras).

__Ahora que tenemos disfraces, queremos que el objeto intercambie entre ellas.__

##PASO 2: Haz que la imagen cambie

1. Pincha en la pestaña 'Programas'.
2. Abre la paleta de bloques de control y arrastra el bloque 'al presionar BANDERA' al área de programas.
3. Añade un bloque 'por siempre' y encájalo debajo del anterior.
4. Pincha en la bandera verde de la esquina superior derecha.  Notarás que aparece un borde blanco alrededor del programa: eso indica que la bandera verde ejecuta el programa.
5. Ahora abre la paleta de apariencia y arrastra un bloque 'siguiente disfraz'.
6. ¿Cómo hacemos que cambie un poco más despacio? Añade un bloque 'esperar 1 segundos' de la paleta de control.
7. Ajusta el número de segundos para que se repita a la velocidad que quieras (0.1 segundos parece ideal). ¿Qué ocurriría sin ese bloque de espera?

```scratch

	al presionar BANDERA
	por siempre		
		siguiente disfraz
		esperar 0.1 segundos
	(fin por siempre)
```

###Prueba tu proyecto
__Pincha en la bandera verde.__ 
¿Cambia el objeto de disfraz a una velocidad adecuada?

Guarda tu proyecto

###Cosas para probar

Ajusta el tiempo en el bloque de espera. ¿Qué valores hacen que el juego sea demasiado fácil o difícil?

##PASO 3: Haz que se detenga cuando pinchamos en él

Muy bien, hemos hecho que el objeto cambie de disfraz para siempre, ¿ahora cómo hacemos para que se detenga cuando pinchamos en él?

1. Crea una nueva variable pinchando en 'Variables' y luego en 'Nueva variable'. Dale el nombre 'detenido', márcalo 'para todos los objetos' y despeja su casilla para que no aparezca en el escenario.
2. Fija el valor de la variable 'detenido' a 1 cuando alguien pincha en la imagen, usando un bloque 'al presionar Objeto1'.
3. Tenemos que asegurarnos de que la imagen deje de cambiar cuando la variable 'detenido' tenga el valor 1. Usando la paleta de bloques de control, reemplaza el bloque 'por siempre' con un 'por siempre si detenido=0'.
4. Finalmente, añade un 'fijar detenido a 0' debajo de 'al presionar BANDERA'.

###Prueba tu proyecto
__Pincha en la bandera verde, espera unos momentos y pincha en el objeto.__ 

¿Cambia continuamente de disfraz antes de pinchar en él?
¿Se detiene cuando pinchas en él?
__Empieza el juego de nuevo.__ ¿Se detiene el objeto cuando pones el puntero del ratón sobre él sin pinchar? ¿Se detiene cuando pinchas en alguna otra parte del escenario? ¿En otra parte de la ventana de Scratch? ¿Fuera de la ventana de Scratch?

Guarda tu proyecto

##PASO 4: Crea otros objetos
__¡Añadamos otros objetos para completar el juego!__

1. Duplica el objeto 'Objeto1' pinchando en él con el botón derecho.
2. Duplícalo de nuevo para acabar con tres objetos en el escenario.
3. Muévelos para que queden alineados. Disminuye su tamaño si hace falta.

###Prueba tu proyecto
__Pincha en la bandera verde.__ Todos los objetos deben empezar a cambiar. ¡Intenta detenerlos todos en la misma imagen!

Guarda tu proyecto

###Cosas para probar

Cuando el juego empieza por primera vez todos los objectos muestran el mismo disfraz y cambian a la vez. ¿Sabes hacer que cada objeto elija un disfraz al azar cuando pinchas en la bandera verde?
__Muy bien, has completado el juego básico. Hay más elementos que añadir: ¡atrévete con estos desafíos!__


##Desafío 1: Hazlo más difícil

Cambia el nivel de dificultad. La manera más sencilla es acelerar los cambios de disfraz. Prueba algo más imaginativo, como por ejemplo:

1. Cambia el número de disfraces por objeto.
2. Haz que algunos objetos tengan disfraces únicos.
3. Haz que distintos disfraces cambien a distintas velocidades.
4. Haz que el orden de los disfraces sea al azar.

__¡Diviértete inventando tus propias ideas!__

Cada vez que cambies algo, considera si hace el juego más fácil o más difícil. ¿Resulta demasiado fácil el juego? ¿Puedes encontrar el nivel de dificultad ideal?

##Desafío 2: Haz que la dificultad cambie según se juega

A distintos jugadores se les dará mejor o peor el juego. __¿Cómo puedes hacer que el juego adapte su dificultad a cada jugador?__

Quizás puedes alterar la velocidad a la que los disfraces cambian. Usa una variable llamada 'retraso' que controle el tiempo de espera de cada objeto. Si la jugadora gana una partida, reduce el valor del 'retraso' para hacer la siguiente partida más difícil. Si la jugadora pierde, incrementa el 'retraso' un poco.

##Desafío 3: Detecta si todos los objetos se han detenido en la misma imagen

__El objetivo del juego es detener los objetos en la misma imagen. Convendría que el escenario detectase cuando todos los objetos se han detenido en el mismo disfraz para decirte si has ganado.__

En primer lugar el escenario tiene que saber cuando el jugador ha acabado. Para ello, cuando alguien pincha en un objeto, el escenario verifica si todos los objetos están detenidos. Modifica el bloque 'al presionar ObjetoX' de cada objeto haciendo que envíen un mensaje 'verificarFin'.

El escenario puede responder a este mensaje y verificar si la variable 'detenido' de cada objeto tiene el valor 1, usando el bloque 'detenido de ObjetoX' en la paleta de 'Sensores'. Si todas las variables tienen el valor 1, sabemos que la partida ha concluido y podemos verificar si hemos ganado.

Para comparar los disfraces, usamos el mismo bloque, esta vez comparando el '# de disfraz de ObjetoX' de cada objeto.

Así, tendrás un bloque 'si' que verifique las variables 'detenido', y dentro de ese bloque otro 'if' comparando los '# de disfraz'.

Una vez verificado el resultado, puedes anunciarlo enviando mensajes 'ganador' o 'perdedor', y haciendo que otro objeto los reciba. ¿Quizás el gato Félix podría felicitar al jugador?

__Bien hecho, hemos terminado. ¡Ahora a disfrutar de tu juego!__
No olvides que puedes compartir tu juego con amigos y familiares pinchando en __Compartir__ en el menú.
