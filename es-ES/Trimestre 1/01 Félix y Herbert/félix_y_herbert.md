
Nivel 1

#Félix y Herbert

__Introducción:__Vamos a crear un juego en el que el gato Félix y el ratón Herbert juegan a pillar. Tú controlarás a Herbert con el ratón para evitar que lo pille Félix. Cuanto más tiempo puedas evitarlo, más puntos te dará el juego, pero ten cuidado porque ¡perderás puntos si te pilla! 

##￼PASO 1: Félix sigue el puntero del ratón

Marca cada casilla para indicar tu progreso.

1. Crea un proyecto nuevo.
2. Haz doble-clic en el escenario y cambia a la pestaña de Fondos, y luego importa el fondo indoors/hall. Borra el fondo blanco original.
3. Cambia el nombre del objeto a Félix.
4. Asegúrate de que Félix solo mire a la izquierda y derecha pinchando en este botón:
5. Crea este programa:

```scratch

	al presionar BANDERA

	por siempre

		apuntar hacia apuntador del ratón

		mover 10 pasos

		siguiente disfraz

		tocar tambor 62 durante 0.3 pulsos

	(fin por siempre)
```		
###Prueba Tu Proyecto
__Pincha en la bandera verde.__
¿Sigue Félix al puntero del ratón? ¿Camina al moverse? ¿Se mueve a la velocidad adecuada?

Guarda tu proyecto

##PASO 2: Félix persigue a Herbert
__A continuación queremos que Félix persiga a Herbert el ratón, en vez de al puntero del ratón.__

1. Crea otro objeto usando el botón 'Escoger un nuevo objeto desde archivo' y selecciona animals/mouse1.
2. Cambia el nombre del objeto a Herbert.
3. Edita el disfraz y hazlo más pequeño que Félix. Prueba pinchando el botón 'Achicar' seis veces.
4. Asegúrate de que Herbert solo mire a la izquierda y derecha.
5. Dale este programa a Herbert:

```scratch
	
	al presionar BANDERA
	por siempre
		ir a apuntador del ratón
		apuntar hacia Félix
	(fin por siempre)
```
###Prueba Tu Proyecto__Pincha en la bandera verde.__
¿Se mueve Herbert bajo el puntero del ratón? ¿Persigue Félix a Herbert?
Guarda tu proyecto.
##PASO 3: Félix dice cuando ha pillado a Herbert
__Queremos que Félix sepa cuándo ha pillado a Herbert, y que nos lo diga.__
1. Cambia el programa de  Félix:

```scratch
	
	al presionar BANDERA
	por siempre
		apuntar hacia apuntador del ratón
		mover 10 pasos
		siguiente disfraz
		tocar tambor 62 durante 0.3 pulsos
		si ¿tocando Herbert?
			decir ¡Te pillé! por 1 segundos
		(fin si)
	(fin por siempre)
```

###Prueba Tu Proyecto__Pincha en la bandera verde.__
¿Dice algo Félix cuando ha pillado a Herbert?
Guarda tu proyecto.

##PASO 4: Herbert se convierte en un fantasma cuando lo pillan

__En vez de hacer que Félix diga algo, queremos que Herbert se convierta en un fantasma cuando lo pillan.__

1. Cambia el programa de Félix para que envíe este mensaje cuando pilla a Herbert.

```scratch
	
	al presionar BANDERA
	por siempre
		apuntar hacia apuntador del ratón
		mover 10 pasos
		siguiente disfraz
		tocar tambor 62 durante 0.3 pulsos
		si ¿tocando Herbert?
			enviar a todos pillado
			tocar tambor 58 durante 0.2 pulsos
			esperar 1 segundos
		(fin si)
	(fin por siempre)
```2. Importa un nuevo disfraz para Herbert desde fantasy/ghost2-a.3. Edita el disfraz haciéndolo más pequeño. Pinchando seis veces en el botón 'Achicar' debería bastar.4. Cambia los nombres de los disfraces de Herbert para que el de ratón se llame 'vivo' y el de fantasma se llame 'muerto'.5. Crea un programa nuevo para Herbert que lo convierta en fantasma:
```scratch
	
	al recibir pillado
	cambiar el disfraz a muerto
	esperar 0.5 segundos
	cambiar el disfraz a vivo
```
	
###Prueba Tu Proyecto__Pincha en la bandera verde.__
¿Se convierte Herbert en un fantasma cuando lo pillan?¿Hace Félix los ruidos correctos en cada momento?
¿Se queda quieto Félix lo suficiente para que Herbert pueda escapar?
Guarda tu proyecto.
##PASO 5: El marcador
__Vamos a añadir un marcador para saber si se nos da bien mantener a Herbert con vida.Empezamos el marcador a cero y le sumamos un punto por segundo. Si Félix pilla a Herbert, le restamos cien al marcador.__
1. Crea una variable para todos los objetos llamada Marcador.2. En el escenario, crea estos dos programas:
```scratch
	
	al presionar BANDERA
	fijar Marcador a 0
	por siempre
		cambiar Marcador por 1
		esperar 1 segundos
	(fin por siempre)
	
	al recibir pillado
	cambiar Marcador por -100
```
	
###Prueba Tu Proyecto__Pincha en la bandera verde.__
¿Aumenta el marcador un punto por segundo?¿Disminuye el marcador cien puntos cuando lo pillan a Herbert?¿Qué pasa cuando a Herbert lo pillan antes de que el marcador llega a cien? ¿vuelve otra vez el marcador a cero al empezar una nueva partida?
Guarda tu proyecto.
__Bien hecho, hemos terminado. ¡Ahora puedes disfrutar de tu propio juego!__No olvides que puedes compartir tu juego con amigos y familiares pinchando en __Compartir__ en el menú.