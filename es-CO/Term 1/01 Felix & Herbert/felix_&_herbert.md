Nivel 1

#Felix & Herbert

__Introducción:__Vamos a crear un juego que se conoce en muchos paises como el juego de 'al gato y al ratón' con __Felix el gato__ y __Herbert__ el ratón como protagonistas. Tú controlaras a Herbert con el apuntador de tú ratón y debes evitar ser capturado por Felix.
Entre más tiempo logres evadirlo mayor sera tú puntaje, pero ten cuidado con dejarte capturar porque perderas puntos!
##￼PASO 1: Felix persigue el apuntador del ratón
Marca con un chulito cada vez que completes una de las siguientes tareas:
1. Comienza un nuevo proyecto.2. Oprime sobre el escenario donde se encuentra tú objeto y seleciona la etiqueta de fondos, luego debes importar el siguiente fondo: indoors/hall. Esta acción eliminara el fondo blanco original.3. Cambia el nombre del objeto a Felix.4. Asegurate que Felix solo pueda mirar de izquierda-derecha oprimir este botón:5. Crea el siguiente programa:

```scratch
	al presionar Bandera
	por siempre
		apuntar hacia apuntador del ratón
		mover 10 pasos
		siguiente disfraz
		tocar tambor 62 durante 0.3 pulsos
	(finalizar por siempre)
```		
###Prueba tú proyecto__Oprime en la bandera verde.__Felix persigue el cursor del mouse? Te da la impresión que camina cuando se mueve? Se mueve a una velocidad adecuada?
Guarda tú proyecto
##STEP 2: Felix persigue a Herbert
__A continuación haremos que Felix persiga a Herbert y no al apuntador del ratón.__
1. Crea un nuevo objeto utilizando el botón 'escoger un nuevo objeto desde archivo' y selecciona animals/mouse1.2. Cambia el nombre del objeto a Herbert.3. Edita el disfraz y haz que su tamaño sea menor que Felix. Intenta oprimir seis veces el botón de achicar objeto:4. Asegurate que Herbert unicamente pueda mirar de izquierda-derecha. 
5. Dale a Herbert el siguiente programa:


```scratch
	
	al presionar bandera
	por siempre
		ir a apuntador del ratón
		apuntar hacia Felix
	(finalizar para siempre)
```
###Prueba tú proyecto__Oprime en la bandera verde.__
Herbert se mueve con el apuntador del ratón? Felix persigue a Herbert?
Guarda tú proyecto.
##PASO 3: Felix avisa cuando capture a Herbert
__Queremos que Felix sepa cuando atrapa a Herbert y nos avise.__
1. Agrega lo sigueinte a tú programa de Felix:

```scratch
	
	al presionar bandera
	por siempre
		apuntar hacia apuntador del ratón
		mover 10 pasos
		siguiente disfraz
		tocar tambor 62 durante 0.3 pulsos
		si ¿tocando Herbert?
			decir Te atrapé! por 1 segundos
		(finalizar si)
	(finalizar por siempre)
```

###Prueba tú proyecto__Oprime en la bandera verde.__
Felix nos avisa cuando captura a Herbert?
Guarda tú proyecto.

##PASO 4:￼Herbert se transforma en fantasma cuando es capturado

__Queremos que Herbert se transforme en fantasta cuando es atrapado y no que Feliz nos avise.__

1. Corrige el programa de Felix para que envie el siguiente mensaje cuando captura a Herbert.

```scratch
	
	al presionar bandera
	por siempre
		apuntar hacia apuntador del ratón
		mover 10 pasos
		siguiente disfraz
		tocar tambor 62 durante 0.3 pulsos
		si ¿tocando Herbert?
			enviar a todos capturado
			tocar tambor 58 durante 0.2 pulsos
			esperar 1 segundos
		(finalizar si)
	(finalizar por siempre)
```2. Importemos un nuevo disfraz para Herbert del siguiente lugar fantasy/ghost2-a.3. Edita el disfraz y haz su tamaño más pequeño.Con oprimir seis veces el botón de achicar objeto sera suficiente.4. Cambia el nombre del disfraz de Herbert a ‘vivo’ en su estado normal y 'muerto' cuando se convierta en fantasma.5. Crea un nuevo programa para convertir a Herbert en un fantasma:
```scratch
	
	al recibir capturado
	cambiar el disfraz a muerto
	esperar 0.5 segundos
	cambiar el disfraz a vivo
```
	
###Prueba tú proyecto__Oprime en la bandera verde.__
Herbert se convierte en fantasma cuando es capturado?Felix ejecuta los sonidos indicados en el momento preciso?Felix permanece quieto lo suficiente como para permitirle a Herbert escapar?
Guarda tú proyecto
##￼PASO 5: Puntaje
__Agreguemos un puntaje para saber que tan bien lo estamos haciendo con Herbert.
Comenzaremos con el puntaje en cero y lo incrementaremos cada segundo. Si Felix logra capturar a Herbert, descontaremos cien puntos del puntaje.__
1. Crea una variable para todos los objetos y llámala Puntaje. Oprime sobre Variables en el menú principal y crea una variable llamada Puntaje2. Dentro del 'stage', crearemos dos scripts
```scratch
	
	al presionar bandera
	fijar Puntaje a 0
	por siempre
		cabiar Puntaje por 1
		esperar 1 segundos
	(finalizar por siempre)
	
	al recibir capturado
	cambiar puntaje por -100
```
	
###Prueba tú proyecto__Oprime en la bandera verde.__
El puntaje incrementa un punto cada segundo?Se restan cien puntos del puntaje cuando capturan a Herbert?Que sucede cuando capturan a Herbert antes de alcanzar los cien puntos? 
Perdemos nuestro puntaje cada vez que iniciamos un nuevo juego?
Guarda tú proyecto
__Felicitaciones, has terminado! Ahora a disfrutar tú juego!__No olvides compartir el juego con tú familia y amigos a través de __Compartir__ localizado en el menú superior.