---
title: Tragapeces
level: Level 1
language: es-ES
stylesheet: scratch
embeds: "*.png"
note: "notas para coordinadores.md"
...

#Tragapeces

__Introducción:__
¡Vamos a crear un juego tragapeces! Ayuda al Pez Gordo a comerse todo lo que nada a su alrededor.

##PASO 1: Crea un objeto que cambia de disfraz
__¡Hagamos que el Pez Gordo nade por el mar!__

1. Comienza un nuevo proyecto de Scratch.
2. Selecciona el escenario y luego la pestaña de 'Fondos'. Importa el fondo 'nature/underwater' y borra el fondo 'fondo1'.
3. Cambia el nombre del objeto de 'Objeto1' a 'Pez Gordo'.
4. Importa el disfraz para el Pez Gordo 'resources/hungry-fish' y borra los anteriores ('disfraz1' y 'disfraz2').
5. Pincha el botón __solo mirar izquierda-derecha__ en la zona de información del objeto para que solo se mueve de izquierda a derecha.
6. Crea este programa para que el Pez Gordo persiga al puntero del ratón:

```scratch

	al presionar BANDERA
	por siempre		
		apuntar hacia apuntador del ratón
		mover 3 pasos
	(fin por siempre)
```

###Prueba tu proyecto
__Pincha en la bandera verde.__ 
Mueve el ratón por el mar. ¿Sigue el pez al puntero?
¿Qué ocurre si dejas de mover el ratón y el pez lo alcanza? ¿Qué aspecto tiene? ¿Por qué crees que hace eso?


7. Para evitar que el Pez Gordo se vuelva loco, haz que solo se mueva cuando no esté muy cerca del puntero. (Encontrarás el bloque 'distancia a' en la paleta de 'Sensores').


```scratch

	al presionar BANDERA
	por siempre	si distancia a apuntador del ratón > 10
		apuntar hacia apuntador del ratón
		mover 3 pasos
	(fin por siempre)
```


###Prueba tu proyecto

Guarda tu proyecto

##Cosas para probar

Si quieres puedes jugar con los números del programa. ¿Cómo cambia la forma de moverse del Pez Gordo? Cambia la 'distancia a apuntador del ratón' a algo más grande (p.ej. 100) o más pequeño (p.ej. 1) Cambia cuánto se mueve el pez a un valor grande (p.ej. 20) o pequeño (p.ej. 1 o hasta 0).

##PASO 2: Añade la presa

1. Crea un nuevo objecto usando el archivo 'animals/lobster1'. 
2. Usa el botón 'achicar objeto' (encima del escenario) para hacerlo más pequeño.
3. Crea un programa que haga que la presa nade por el mar. Queremos que se mueva al azar, así que haremos que se mueva hacia adelante un poco, luego se gire al azar a derecha o izquierda, repetidamente.

```scratch

	al presionar BANDERA
	por siempre		
		mover 2 pasos
		girar número al azar entre -20 y 20 grados
		rebotar si está tocando un borde
	(fin por siempre)
```

###Prueba tu proyecto
__Pincha en la bandera verde__ y observa si la presa nada por el escenario. ¿Se mueve como esperabas? ¿Es un movimiento realista?

__Por ahora el Pez Gordo y la presa no interactúan. En el siguiente paso añadiremos eso.__

Guarda tu proyecto

###Cosas para probar

* Prueba cambiar los valores en los bloques 'número al azar' y 'mover'. ¿Cómo cambia el movimiento de la presa?
* ¿Para qué sirve el bloque __rebotar si está tocando un borde__? Quítalo y verás.

##PASO 3: El Pez Gordo se come a la presa

__¡Queremos que el Pez Gordo se coma a la presa!__ Una vez que el Pez Gordo tenga a la presa en su boca, hay que hacer que:
* El Pez Gordo cierre la boca y toque el sonido 'chomp'.
* La presa desaparezca, y reaparezca un poco más tarde.

1. Primero hagamos que la presa desaparezca si está tocando al Pez Gordo, y reaparezca 3 segundos después. Para ello usamos un bloque '¿tocando?':

```scratch

	al presionar BANDERA
	por siempre		
		mover 2 pasos
		girar número al azar entre -20 y 20 grados
		rebotar si está tocando un borde
		si ¿tocando Pez Gordo?
			esconder
			esperar 3 segundos
			mostrar
		(fin si)
	(fin por siempre)
```

###Prueba tu proyecto
__Vuelve a probar tu juego. ¿Notas algún problema?__ Fíjate que la presa desaparece al tocar cualquier parte del Pez Gordo. Además, el pez puede quedarse quieto 3 segundos esperando a que la presa reaparezca, ¡eso no vale!

2. ¿Cómo podemos hacer que la presa solo desaparezca cuando toca la boca del pez? Una forma de hacerlo es usando un bloque '¿tocando el color?' para ver si está tocando el color de los dientes del pez. Para ello, reemplaza el bloque '¿tocando?' con un '¿tocando el color?', pincha en el color del bloque, y luego pincha en los dientes del pez.
3. También haremos que la presa se mueva a una parte del escenario al azar antes de reaparecer, usando un bloque 'ir a' y dándole valores x e y al azar.

```scratch

	al presionar BANDERA
	por siempre		
		mover 2 pasos
		girar número al azar entre -20 y 20 grados
		rebotar si está tocando un borde
		si ¿tocando el color []?
			esconder
			esperar 3 segundos
			ir a x:número al azar entre -220 y 220 y: número al azar entre -170 y 170
			mostrar
		(fin si)
	(fin por siempre)
```
###Prueba tu proyecto

Prueba tu juego de nuevo: confirma que la presa solo desaparece cuando toca la boca del pez, y reaparece en un lugar al azar del escenario.

4. El pez tiene que saber cuando se ha tragado algo para poder tocar el sonido y cambiar de disfraz. Para ello la presa tiene que enviar un mensaje indicando que se la han tragado antes de desaparecer.

```scratch

	al presionar BANDERA
	por siempre		
		mover 2 pasos
		girar número al azar entre -20 y 20 grados
		rebotar si está tocando un borde
		si ¿tocando el color []?
			enviar a todos comida
			esconder
			esperar 3 segundos
			ir a x:número al azar entre -220 y 220 y: número al azar entre -170 y 170
			mostrar
		(fin si)
	(fin por siempre)
```
__Ahora queremos que el pez responda a este mensaje tocando el sonido 'chomp' y cerrando la boca.__

5. Añade el disfraz 'resources/mouth-closed' y el sonido 'resources/chomp. al objeto Pez Gordo.
6. Después añade un nuevo programa al Pez Gordo para responder al mensaje de la presa. El programa toca el sonido, cambia el disfraz, espera un poco y vuelve al disfraz original.

```scratch

	al recibir comida
	tocar sonido chomp
	repetir 2
		cambiar el disfraz a mouth-closed
		esperar 0.5 segundos
		cambiar el disfraz a hungry-fish
	(fin repetir)
```

__Ahora que el Pez Gordo está listo, ¡llenemos el mar de comida! Pincha en el objecto presa con el botón derecho y duplícalo varias veces.__

###Prueba tu proyecto
Pincha en la bandera verde.
¿Se come el Pez Gordo la presa? ¿Se come las distintas presas?

Guarda tu proyecto

###Detalles a considerar
¿Por qué tenemos que añadir un 'mostrar' al principio del programa de la presa? Piensa qué ocurriría sin él si el pez se come la presa y detienes el juego antes de que reaparezca. ¿Qué ocurriría la próxima vez que reiniciases el juego?

__Bien hecho, has acabado el juego básico. Pero puedes hacer más cosas con él. ¿Listos para un desafío?


##Desafío 1: Haz que la presa se mueva de forma distinta

Por ahora todas las presas se mueven de la misma forma. __¿Sabrías hacer que una de ellas se mueva de forma distinta?__
__Pista:__ No gastes mucho tiempo en esta parte sin mirar primero el resto de las actividades.

__Elige una presa con la que experimentar.__ Cambia su color con el bloque 'fijar efecto color' para poder distinguirla de las demás.

Haz que esta presa se mueva más despacio que las demás. __Pista:__ Busca el bloque 'mover 2 pasos'.


###Prueba tu proyecto
¿Se mueve más despacio esa presa? ¿Es mejor el juego así?
Pudiendo hacer eso, __intenta que uno de los peces se mueva más rápido que los demás.__


Sigue moviéndose la presa de manera razonable? ¿Mejora el juego así?
__Pista:__ Si la presa se mueve en círculos, verifica los valores de los bloques 'número al azar'.

¿Qué tal si haces que cada presa se mueva de manera distinta, combinando estos cambios?

¿Qué cambios mejoran el juego? ¿Lo hacen más interesante, divertido, difícil o fácil? ¿Cuál es mejor?

Guarda tu proyecto

##Desafío 2: Haz que la presa evite al Pez Gordo

¡Esta presa es muy tonta! Nada al azar hasta que se la comen. La presa real huye de sus depredadores. __Hagamos que la presa nade alejándose del Pez Gordo.__

En Scratch no existe ningún bloque que te indique en qué dirección se encuentra un objeto, pero puedes hacer que un objeto apunte hacia otro, y luego que se de la vuelta. Los bloques que necesitas están en la paleta de 'Movimiento'.

Con esa información, __haz que una de las presas siempre se aleje del Pez Gordo__. Igual hasta puedes hacer que zigzaguee mientras se aleja.

###Prueba tu proyecto
¿Es más difícil capturar a esta presa? ¿Mejora el juego así?

Guarda tu proyecto

##Desafío 3: Añade un marcador
No basta con tragar peces. ¿Cómo sabes si se te da mejor que a tus amigos? __Hace falta alguna manera de mantener un marcador__. Mira la tarjeta de Scratch __Guarda los puntos__ para saber cómo.

¿Dónde debes añadir los bloques que cambian el marcador?

Asegúrate de que el marcador empieza de cero al principio de la partida. ¿Dónde irá ese bloque?

###Prueba tu proyecto
¿Empieza siempre de cero la partida? Sube el marcador cada vez que te comes una presa?

Guarda tu proyecto

##Desafío 4: Añade una cuenta atrás

__Date un límite de tiempo para cada partida.__ ¿Cuántos peces puedes comerte en treinta segundos?

Mira la tarjeta de Scratch __Cronómetro__ para saber cómo añadir una cuenta atrás. Comienza cada partida con treinta segundos.

###Prueba tu proyecto
¿Empieza el cronómetro a 30 segundos?

¿Baja el cronómetro a la velocidad correcta?

¿Puedes tragar presa solo mientras el cronómetro está en marcha?

¿Se detiene el juego cuando se acaba el tiempo?

Guarda tu proyecto

##Desafío 5: Añade puntos extra
Añade un bonus al marcador si consigues tragar a tres peces a la vez. ¿Cómo puedes saber cuántos peces te has comido a la vez?
__Pista:__ Una forma de hacerlo es mantener una variable que cuenta cuánta presa hay nadando en cada momento.

Guarda tu proyecto

##Desafío 6: El juego al revés: ¡mantén la presa con vida!
A veces las mejores ideas surgen al darle la vuelta a una idea inicial.

__Cambia el juego tal que, en vez de controlar al pez que se come a los demás, controlas una presa rodeada de Peces Gordos. ¿Cuánto tiempo duras sin ser tragado?

Guarda tu proyecto

__Bien hecho, hemos terminado. ¡Ahora a disfrutar de tu juego!__
No olvides que puedes compartir tu juego con amigos y familiares pinchando en __Compartir__ en el menú.