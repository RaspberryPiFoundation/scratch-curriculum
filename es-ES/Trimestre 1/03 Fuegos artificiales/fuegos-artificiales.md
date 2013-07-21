Nivel 1

#Fuegos artificiales

__Introducción:__
En este proyecto vamos a crear una exhibición de fuegos artificiales sobre la ciudad.

##PASO 1: Crea un cohete que vuela hacia el ratón

__Primero, importemos las imágenes que vamos a necesitar__

1. Crea un proyecto de Scratch nuevo. Borra el objeto gato pinchando en él con el botón derecho y pinchando en 'borrar'.
2. Cambia el fondo del escenario a 'outdoor/city-with-water'.
3. Pincha el botón __Escoger un nuevo objeto desde archivo__ para añadir un cohete al proyecto (usa el disfraz 'rocket.png').
4. Haz que el cohete se esconda cuando se pincha en la bandera verde.

Ahora queremos que el cohete se mueva hacia el ratón cuando pulses el botón del ratón.

5. Añade un bloque de control cuando se pulsa la barra espaciadora, haciendo que el cohete aparezca y se deslice hacia el ratón:

```scratch

	al presionar BANDERA

	esconder

	
	al presionar tecla espacio
	mostrar
	deslizar en 1 segs a x: x del raton y: y del ratón
```
		
###Prueba tu proyecto
__Pincha en la bandera verde, pon el puntero del ratón sobre el escenario y pulsa la barra espaciadora.__

¿Aparece el cohete y se mueve hacia el puntero del ratón?
¿Qué pasa si mueves el ratón y vuelves a pulsar la barra espaciadora?

6. Los cohetes de verdad no vuelan de lado a lado, así que vamos a hacer que se deslice hacia el puntero del ratón desde el pie del escenario. Antes de mostrar el cohete, usamos un bloque 'ir a' para decirle que se mueva más abajo del pie del escenario, aún manteniendo su posición horizontal.

```scratch

	al presionar BANDERA

	esconder

	
	al presionar tecla espacio
	ir a x: x del ratón y: -200
	mostrar
	deslizar en 1 segs a x: x del ratón y: y del ratón
```

###Prueba tu proyecto
__Pincha en la bandera verde, pon el puntero del ratón sobre el escenario y pulsa la barra espaciadora.__ 
¿Vuela el cohete hacia el ratón desde la parte inferior de la pantalla? ¿Qué pasa si mueves el ratón y vuelves a pulsar la barra espaciadora?

7. Finalmente, vamos a hacer que el cohete se lance al pulsar el botón del ratón en vez de la barra espaciadora. Para lograrlo, vamos a envolver nuestro programa en un bloque 'por siempre si ¿ratón presionado?'.
Después reemplaza el bloque __al presionar tecla espacio__ por un __al presionar BANDERA__ y asegúrate de que el cohete esté escondido al principio.

```scratch

	al presionar BANDERA
	esconder
	por siempre si ¿ratón presionado?
		ir a x: x del ratón y: -200
		mostrar
		deslizar en 1 segs a x: x del ratón y: y del ratón
	(fin por siempre)
```
###Prueba tu proyecto
__Pincha en la bandera verde, y luego pincha con el ratón en el escenario. Pincha en diferentes partes del escenario.__ 

###Cosas para probar
1. Prueba a cambiar dónde se posiciona el cohete antes de deslizarse hacia el ratón, para que se mueva trazando un arco.
2. Crea varios cohetes con diferentes velocidades.

Guarda tu proyecto.

##PASO 2: Haz que el cohete explote

1. El primer paso para hacer que explote es que toque el sonido 'Resources/bang' antes de empezar a moverse, y luego se esconda al alcanzar el puntero del ratón. Para importar el sonido usa el botón 'Importar' en la pestaña de 'Sonidos'.

```scratch

	al presionar BANDERA
	esconder
	por siempre si ¿ratón presionado?
		ir a x: x del ratón y: -200
		tocar sonido bang
		mostrar
		deslizar en 1 segs a x: x del ratón y: y del ratón
		esconder
	(fin por siempre)
```
2. Después haz que el cohete envíe un nuevo mensaje al explotar. Más tarde usaremos este mensaje.

```scratch

	al presionar BANDERA
	esconder
	por siempre si ¿ratón presionado?
		ir a x: x del ratón y: -200
		tocar sonido bang
		mostrar
		deslizar en 1 segs a x: x del ratón y: y del ratón
		esconder
		enviar a todos explota
	(fin por siempre)

```
###Prueba tu proyecto
__Pincha en la bandera verde.__ 
Confirma que el cohete toca el sonido y se esconde al alcanzar el puntero del ratón.

3. Importa un nuevo objecto usando el disfraz 'Resources/firework1.png'.
4. Cuando recibe el mensaje 'explota', este objeto debe esconderse y moverse a la posición del cohete usando un bloque 'ir a', mostrarse, y desaparecer otra vez después de un segundo.

```scratch

	al recibir explota

	esconder

	ir a x: posición en x de cohete y: posición en y de cohete

	mostrar

	esperar 1 segundos

	esconder
```
###Prueba tu proyecto
__Lanza otro cohete.__ 
Cuando el cohete explota, ¿desaparece el cohete y aparece la imagen de la explosión?
¿Qué ocurre si mantienes el botón del ratón presionado mientras mueves el ratón? (No te preocupes, arreglaremos este problema más tarde).

Guarda tu proyecto

##PASO 3: Haz que cada explosión sea distinta

1. Ahora podemos hacer que cada explosión sea única usando el bloque 'fijar efecto color', eligiendo un número al azar entre el 1 y el 200, antes de mostrar cada explosión.

```scratch

	al recibir explota

	esconder
	
	fijar efecto color a número al azar entre 1 y 200

	ir a x: posición en x de cohete y: posición en y de cohete

	mostrar

	esperar 1 segundos

	esconder
```

###Prueba tu proyecto
__Pincha en la bandera verde.__ 

¿Es cada explosión de un color distinto?

2. Vamos a añadir varios tipos de explosión distintos, usando los disfraces 'Resources/firework2.png' y 'Resources/firework3.png', intercambiando entre ellos en cada cohete, de nuevo antes de mostrar cada explosión.

###Prueba tu proyecto
__Pincha en la bandera verde.__ 

¿Muestra cada cohete una explosión distinta?

3. Finalmente, hagamos que cada explosión crezca después de aparecer. En vez de esperar un segundo, fija el tamaño del objeto al 5% antes de mostrarlo, y una vez que lo has mostrado, incrementa el tamaño un 2% cincuenta veces, usando un bloque 'repetir'.

```scratch

	al recibir explota

	esconder
	
	fijar efecto color a número al azar entre 1 y 200

	ir a x: posición en x de cohete y: posición en y de cohete

	fijar tamaño a 5%
	
	mostrar

	repetir 50
		cambiar tamaño por 2
	(fin repetir)

	esconder
```
###Prueba tu proyecto
__Pincha en la bandera verde.__ 

¿Comienza la explosión pequeña en el centro del cohete y se expande lentamente?

###Cosas para probar
Puedes intentar hacer que cada explosión sea más única cambiando su tamaño y velocidad de expansión.

Guarda tu proyecto

##PASO 4: Arreglando el error en el envío del mensaje
¿Recuerdas cómo había un problema antes cuando mantenías presionado el botón del ratón?
La causa es que después de enviar el mensaje 'explota', el cohete vuelve a repetir el bloque 'por siempre si', mandando otro mensaje 'explota' antes de que el anterior haya acabado de actuar.


1. Para solucionar este problema, podemos reemplazar el bloque 'enviar a todos' con uno 'enviar a todos y esperar'. De esta manera, le ciclo no se repite hasta que la explosión haya acabado.

```scratch

	al presionar BANDERA
	esconder
	por siempre si ¿ratón presionado?
		ir a x: x del ratón y: -200
		tocar sonido bang
		mostrar
		deslizar en 1 segs a x: x del ratón y: y del ratón
		esconder
		enviar a todos explota y esperar
	(fin por siempre)
```
###Prueba tu proyecto
__Pincha en la bandera verde, mantén presionado el botón del ratón y mueve el ratón por el escenario.__ 

¿Aparece cada explosión en el lugar y momento correcto?

Guarda tu proyecto
