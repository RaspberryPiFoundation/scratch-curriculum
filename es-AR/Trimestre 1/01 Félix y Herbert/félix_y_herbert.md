Nivel 1

#Félix y Herbert

__Introducción:__
Vamos a crear un juego en el que el gato Félix y el ratón Herbert juegan a atraparse. Vos controlarás a Herbert con el mouse para evitar que lo atrape Félix. Cuanto más tiempo puedas evitarlo, más puntos te dará el juego, pero tené cuidado porque ¡perderás puntos si te atrapa! 

##PASO 1: Félix sigue el puntero del mouse

Marcá cada casilla para indicar tu progreso.

1. Creá un proyecto nuevo.
2. Hacé doble-clic en el escenario y cambiá a la pestaña de Fondos, y luego importá el fondo indoors/hall. Borrá el fondo blanco original.
3. Cambiá el nombre del objeto a Félix.
4. Asegurate de que Félix solo mire a la izquierda y derecha haciendo clic en este botón:
5. Creá este programa:

```scratch

	al presionar BANDERA

	por siempre

		apuntar hacia apuntador del ratón

		mover 10 pasos

		siguiente disfraz

		tocar tambor 62 durante 0.3 pulsos

	(acabar por siempre)
```
		
###Probá Tu Proyecto
__Hacé clic en la bandera verde.__
¿Sigue Félix al puntero del mouse? ¿Camina al moverse? ¿Se mueve a la velocidad adecuada?

Guardá tu proyecto

##PASO 2: Félix persigue a Herbert

__A continuación queremos que Félix persiga al ratón Herbert, en vez de al puntero del mouse.__

1. Creá otro objeto usando el botón 'Escoger un nuevo objeto desde archivo' y seleccioná animals/mouse1.
2. Cambiá el nombre del objeto a Herbert.
3. Editá el disfraz y hacelo más pequeño que Félix. Probá haciendo clic en el botón 'Achicar' seis veces.
4. Asegurate de que Herbert sólo mire a la izquierda y derecha.
5. Dale este programa a Herbert:


```scratch
	
	al presionar BANDERA
	por siempre
		ir a apuntador del ratón
		apuntar hacia Félix
	(acabar por siempre)
```

###Probá Tu Proyecto
__Hacé clic en la bandera verde.__

¿Se mueve Herbert bajo el puntero del mouse? ¿Persigue Félix a Herbert?

Guardá tu proyecto.

##PASO 3: Félix dice cuando ha atrapado a Herbert

__Queremos que Félix sepa cuándo ha atrapado a Herbert, y que nos lo diga.__


1. Cambiá el programa de Félix:

```scratch
	
	al presionar BANDERA
	por siempre
		apuntar hacia apuntador del ratón
		mover 10 pasos
		siguiente disfraz
		tocar tambor 62 durante 0.3 pulsos
		si ¿tocando Herbert?
			decir ¡Te atrapé! por 1 segundos
		(acabar si)
	(acabar por siempre)
```

###Probá Tu Proyecto
__Hacé clic en la bandera verde.__

¿Dice algo Félix cuando ha atrapado a Herbert?

Guardá tu proyecto.

##PASO 4: Herbert se convierte en un fantasma cuando lo atrapan

__En vez de hacer que Félix diga algo, queremos que Herbert se convierta en un fantasma cuando lo atrapan.__

1. Cambiá el programa de Félix para que envíe este mensaje cuando atrapa a Herbert.

```scratch
	
	al presionar BANDERA
	por siempre
		apuntar hacia apuntador del ratón
		mover 10 pasos
		siguiente disfraz
		tocar tambor 62 durante 0.3 pulsos
		si ¿tocando Herbert?
			enviar a todos atrapado
			tocar tambor 58 durante 0.2 pulsos
			esperar 1 segundos
		(acabar si)
	(acabar por siempre)
```
2. Importá un nuevo disfraz para Herbert desde fantasy/ghost2-a.
3. Editá el disfraz haciéndolo más pequeño. Haciendo clic seis veces en el botón 'Achicar' debería bastar.
4. Cambiá los nombres de los disfraces de Herbert para que el de ratón se llame 'vivo' y el de fantasma se llame 'muerto'.
5. Creá un programa nuevo para Herbert que lo convierta en fantasma:

```scratch
	
	al recibir atrapado
	cambiar el disfraz a muerto
	esperar 0.5 segundos
	cambiar el disfraz a vivo
```
	
###Probá Tu Proyecto
__Hacé clic en la bandera verde.__

¿Se convierte Herbert en un fantasma cuando lo atrapan?
¿Hace Félix los ruidos correctos en cada momento?
¿Se queda quieto Félix lo suficiente para que Herbert pueda escapar?

Guardá tu proyecto.

##PASO 5: El marcador

__Vamos a añadir un marcador para saber si se nos da bien mantener a Herbert con vida.
Empezamos el marcador a cero y le sumamos un punto por segundo. Si Félix atrapa a Herbert, le restamos cien al marcador.__

1. Creá una variable para todos los objetos llamada Marcador.
2. En el escenario, creá estos dos programas:

```scratch
	
	al presionar BANDERA
	fijar Marcador a 0
	por siempre
		cambiar Marcador por 1
		esperar 1 segundos
	(acabar por siempre)
	
	al recibir atrapado
	cambiar Marcador por -100
```
	
###Probá Tu Proyecto
__Hacé clic en la bandera verde.__

¿Aumenta el marcador un punto por segundo?
¿Disminuye el marcador cien puntos cuando lo atrapan a Herbert?
¿Qué pasa cuando a Herbert lo atrapan antes de que el marcador llega a cien? ¿Vuelve otra vez el marcador a cero al empezar una nueva partida?

Guardá tu proyecto.

__Bien hecho, hemos terminado. ¡Ahora podés disfrutar de tu propio juego!__
No olvides que puedes compartir tu juego con amigos y familiares pinchando en __Compartir__ en el menú.