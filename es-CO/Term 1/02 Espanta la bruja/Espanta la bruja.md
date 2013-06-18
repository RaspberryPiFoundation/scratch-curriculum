Nivel 1

#Espanta-la-bruja

__Introducción:__Este es un proyecto para recrear un juego muy popular en las ferias Europeas. Obtendras puntos por las brujas que logres espantar de tú pantalla. La meta es lograr el mayor puntaje en un tiempo de 30 segundos.
##￼Paso 1: Crea una bruja voladora
1. Comienza un nuevo proyecto en Scratch.2. Elimina el objeto del gato y reemplaza el fondo blanco con el fondo nature/woods3. Oprime el botón 'escoger un nuevo objeto desde archivo' para agregar un nuevo objeto a tú proyecto (utiliza fantasy/witch1). 
Ahora haremos que nuestra bruja se mueva

4. Agrega una variable solo a este objeto y llámala: velocidad.En el escenario, el monitor para esta variable debe decir “Objeto1 velocidad”.En caso que solo diga “velocidad”, borra la variable y creala de nuevo solo para este objeto. Quitale el chulito a la caja de velocidad en la paleta deVariables para que no se vea más en el escenario.La variable de velocidad controlara que tan rapido se mueve la bruja. Utilizamos una variable para así poder cambiar que tan rapido se mueve la bruja mediante va avanzando el juego.5. Queremos que la bruja se mueva no más comenzar nuestro juego así que escribiremos el siguiente programa:

```scratch
	al presionar bandera
	fijar velocidad a 5
	por siempre
		mover velocidad pasos
	(finalizar por siempre)
```		
###Prueba tú proyecto__Oprime en la bandera verde__ y observa que hace la bruja. Por qué se sale de el borde de la pantalla?
6. Para impedir que la bruja se salga de la pantalla debemos hacer que cambie de dirección en sentido contrario una vez toca al borde. Abajo de tu bloque de mover velocidad pasos coloca un if on edge, bounce block.
```scratch
	al presionar bandera
	fijar velocidad a 5
	por siempre
		mover velocidad pasos
		rebotar si está tocando un borde
	(finalizar por siempre)
```7. Para impedir que la bruja vuele patas arriba hay que oprimir el botón __solo mirar izquierda-derecha__ en la información del objeto actual.

###Prueba tú proyecto__Oprime la bandera verde.__ 
La bruja se mueve de lado a lado en la pantalla?

Guarda tú proyecto

###Variaciones￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼__Intenta cambiar el valor de la variable de velocidad para que la bruja vuele más rapido o más lento.____Como hariamos para que la bruja vuele más rapido mediante pasa el tiempo?__
(Es un poco complicado así que no te preocupes si no sabes la respuesta. Te daremos un par de pistas más adelante en el proyecto.)##PASO 2: Haz que la bruja aparezca y desaparezca al azar
Para hacer el juego aún más divertido, haremos que la bruja aparezca y desaparezca al azar. Para esto crearemos otro programa que ejecute a la vez que nuestro programa anterior. Este nuevo programa ocultara a la bruja por un tiempo al azar y luego la revelara por un tiempo también al azar y asi sucesivamente por siempre (o hasta que termine el juego)
Crea el siguiente programa para la bruja:
```scratch
	al presionar bandera
	por siempre
		esconder
		esperar número al azar entre 2 y 5 segundos
		mostrar
		esperar número al azar entre 3 y 5 segundos
	(finalizar por siempre)
```
###Prueba tú proyecto__Oprime la bandera verde.__ 
La bruja se mueve de lado a lado de la pantalla y desaparece y reaparece al azar?

Guarda tú proyecto

###Variaciones__Intenta cambiar el intervalo de los numeros. Que sucede si escoges un numero demasiado grande o demasiado pequeño?__(Esto te puede ayudar para hacer que la bruja incremente su velocidad con el paso del tiempo?)##￼PASO 3: Haz que la bruja desaparezca cuando la oprimimos
Para convertir esto en un juego debemos darle al jugador algo que hacer. Ellos deben oprimir sobre la bruja para hacerla desaparecer. Hagamos que al oprimirla desaparezca y produzca un sonido.
1. Ingresa a la pestaña de sonidos y selecciona importar: electronic/fairydust. 
2. Agrega el siguiente programa:
```scratch
	al presionar Objeto1
	esconder
	tocar sonido Fairydust
```
###Prueba tú proyecto__Oprime la bandera verde.__ 
Desaparece la bruja y escuchas el sonido cuando al oprimirla?
Guarda tú proyecto
##Paso 4: Agrega un marcador y cronómetro
Ya tenemos la bruja, pero ahora queremos hacer un juego! Queremos sumar puntos cada vez que oprimimos sobre labruja y también queremos tener un limite de tiempo. Podremos utilizar una variable para el marcador y el cronómetro.
1. Crea una nueva Variable para todos los objetos llamado: marcador y altera el programa anterior para que incremente esa variable por una unidad cuando la oprimimos.
```scratch
	al presionar Objeto1
	esconder
	tocar sonido Fairydust
	cambiar marcador por 1
```2. Regresa al escenario y crea una nueva variable (esta vez solo para el escenario) llamada: tiempo. Crea un nuevo programa que fijara el tiempo en 30 y al marcador en 0 cuando oprimamos la bandera verde. Luego utiliza un bloque de repetir hasta que espere 1 segundo y reduzca el tiempo por -1. Esto debera repetirse hasta que el tiempo sea 0 para luego utilizar detener todo para así poder parar el juego.
```scratch
	al presionar bandera
	fijar tiempo a 30
	fijar marcador a 0
	repetir hasta que tiempo = 0
		esperar 1 segundos
		cambiar tiempo por -1
	(finalizar repetir)
	detener todo
```
###Prueba tú proyecto__Oprime la bandera verde.__ 
Guarda tú proyecto

###Variaciones__Como incrementarias la velocidad de la bruja a medida que va corriendo el tiempo?__
__Muy bien hecho! has terminado un juego basico. Pero aún hay mas cosas que puedes hacer en tú juego. Intenta realizar el reto a continuación!__
##Reto: agrega más brujas
Si con una bruja es divertido con varias debe serlo aún más! Hagamos a tres brujas volar.
1. Duplica la bruja oprimiendo el botón derecho de tú ratón sobre el Objeto1 en la lista de objetos.2. Altera el tamaño de cada objeto para que así cada bruja sea de un tamaño diferente.3. Cambia la variable de velocidad de cada bruja para que cada una vuele a una velocidad distinta.4. Cambia a las brujas de posición dentro del escenario para que no esten todas agrupadas una sobre otra.
###Prueba tú proyecto__Oprime la bandera verde.__ 
Ya lograste que las tres brujas vuelen de lado a lado en la pantalla, aparecen y desaparecen como por arte de magia y desaparecen una vez oprimimos sobre ellas?Guarda tú proyecto
###Variaciones1. Cual sería el numero de brujas adecuado para este juego?
2. Puedes hacer que cada bruja tenga un look original? Podrías editar los disfraces o también utilizar uno o más bloques dentro de la paleta de apariencias para cambiarlas.
3. Puedes hacer que cada bruja valga una cierta cantidad de puntos? Que tal si hacemos que la más rapida y la más pequeña vangan 10 puntos?__Felicitaciones, has terminado! Ahora a disfrutar tú juego!__No olvides compartir el juego con tú familia y amigos a través de __Compartir__ localizado en el menú superior.