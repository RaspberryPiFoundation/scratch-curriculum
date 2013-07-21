Nivel 3

#Caja de pinturas

__Introducción:__
Este proyecto crea una aplicación de dibujo que te permitirá crear tus propias obras de arte. Puedes dibujar líneas de distintos colores, borrar la pantalla, estampar diseños ¡y mucho más!

##PASO 1: Arrastra para dibujar

Empecemos con un lápiz que dibuja cuando lo mueves sobre el escenario.

1. Comienza un nuevo proyecto de Scratch. Borra el objeto gato pinchando en él con el botón derecho y pinchando en 'borrar'.
2. Pincha en el escenario y luego en la pestaña de Fondos. Importa el fondo __indoors/chalkboard__.
3. Crea un nuevo objeto llamado __lápiz__, usando la imagen __resources/green-pencil.__
4. Cambia a la pestaña __Disfraces__ y pincha en __Editar__. Una vez en el __Editor de Pinturas__, mueve el centro de la imagen a la punta del lápiz. Para ello, pincha el botón __Seleccionar dentro de disfraz__ y mueve las líneas que aparecen hasta que queden justo pasado el final de la punta del lápiz.
5. Haz que el lápiz siga al puntero del ratón usando bloques __por siempre__ e __ir a apuntador del ratón__.

```scratch
al presionar BANDERA
por siempre
	ir a apuntador del ratón
(fin por siempre)
```

__Ahora queremos que este objeto lápiz se comporte como un lápiz de verdad.__ En la paleta llamada Lápiz verás varios bloques para dibujar. Para empezar nos interesan __bajar lápiz__ y __subir lápiz__.

6. Queremos controlar el lápiz con el botón del ratón: con el botón presionado. el lápiz está en contacto con el escenario, y al soltar el botón se levanta el lápiz. Lo conseguimos usando bloques __si / si no__ y __¿ratón presionado?__.

```scratch
al presionar BANDERA
por siempre
	ir a apuntador del ratón
	si ¿ratón presionado?
		bajar lápiz
	si no
		subir lápiz
	(fin si)
(fin por siempre)
```
##Prueba tu proyecto
__Pincha en la bandera verde.__
¿Sigue el lápiz al ratón por el escenario? ¿Qué pasa cuando mantienes apretado el botón del ratón y lo mueves? No te preocupes por ahora del color del lápiz.


7. Muy pronto se te llenará la pantalla de garabatos. Puedes usar un bloque __borrar__ para borrar el escenario.

```scratch
al presionar BANDERA
borrar
por siempre
	ir a apuntador del ratón
	si ¿ratón presionado?
		bajar lápiz
	si no
		subir lápiz
	(fin si)
(fin por siempre)
```

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Desaparece tu dibujo cuando pinchas en la bandera verde?

Guarda tu proyecto.

##PASO 2: Vuelve a empezar

En vez de tener que detener y reiniciar el proyecto, añadamos un botón para borrar el dibujo. El botón usará el bloque __borrar__.

1. Crea un nuevo objeto con la imagen __resources/cancel-button__. 
2. Cambia el nombre del objeto a __borrar__.
3. Coloca el objeto cerca de la esquina inferior izquierda del escenario.
4. Dale este programa:

```scratch
al presionar borrar
borrar
```

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Funciona el botón para borrar el dibujo?

Guarda tu proyecto.

##PASO 3: Cambia de color

Por ahora solo podemos dibujar líneas azules. ¡Dibujemos en colores! Vamos a añadir unos objetos en la parte inferior del recuadro. Los objetos parecerán botones de colores. Si pinchamos uno de ellos, cambiará el color de las líneas que dibujemos. Para saber qué color estamos usando, el botón también cambiará el color del lápiz.

1. Añade un nuevo objeto llamado __rojo__, usando la imagen __resources/red-selector__. 
2. Colócalo bajo el recuadro, cerca del botón __borrar__.
3. Cuando se pinche el objeto rojo, haz que mande el mensaje __rojo__.

```scratch
al presionar rojo
enviar a todos rojo
```
__Y eso es todo para este botón. El lápiz se encarga de lo demás.__

En el lápiz, importa un nuevo disfraz, __resources/red-pencil__. Mueve el centro de la imagen a la punta del lápiz como hiciste con la imagen original.

4. Añade otro programa al lápiz. Cuando el lápiz recibe el mensaje __rojo__, debe cambiar a su disfraz rojo y cambiar el color de la línea a rojo (usando un bloque __fijar color de lápiz a__).

__Pista:__ si pinchas en el recuadro de color del bloque __fijar color de lápiz a__, puedes pinchar con el cuentagotas en el objeto rojo para tomar su color.
```scratch
al recibir rojo 
cambiar el disfraz a red-pencil
fijar color de lápiz a (rojo)
```

##Prueba tu proyecto
__Pincha en la bandera verde.__

Empieza dibujando una línea. Después pincha el objeto rojo y dibuja algo más. ¿Ha cambiado de disfraz el lápiz? ¿Las líneas son ahora rojas? ¿Aparecen desde la punta del lápiz?

Guarda tu proyecto.

5. Repite esos pasos para crear lápices de color azul, amarillo y verde.

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Funcionan todos los botones para seleccionar colores? ¿Cambia el color del lápiz y de las líneas que dibuja? ¿Aparecen todas las líneas desde la punta del lápiz?

Guarda tu proyecto.

##PASO 4: Dibuja solo dentro del recuadro

Habrás notado que puedes dibujar por todo el escenario, incluso fuera del recuadro de fondo. Queremos mejorar las cosas, haciendo que solo se pueda dibujar en la zona central del escenario. Para ello haremos que el lápiz no pueda salir de la zona gris más clara del escenario.


Recuerda que en Scratch cada punto del escenario se describe por sus coordenadas __x__ e __y__. El recuadro gris contiene puntos con valores de x entre -230 y 230, y valores de y entre -120 y 170. Usando estos valores en un bloque __si__, podemos asegurarnos de que el ratón se encuentre en esa zona antes de mover el lápiz.

Para ello rodea el bloque __ir a__ con un bloque __si__, en el que verificas que:

'y' del ratón es mayor que -120 y 'y' del ratón es menor que 170
y 'x' del ratón es mayor que -230 y 'x' del ratón es menor que 230

__Nota:__ para crear esta expresión tendrás que usar varios bloques __y__ de la paleta de Operadores: uno para la parte de la coordenada x, otro para la parte de la coordenada y, y otro para combinar las dos partes.

```scratch
borrar
por siempre 
	si y del ratón > -120 y y del ratón < 170 y x del ratón > -230 y x del ratón < 230
ir a apuntador del ratón
```

Como ya no podemos dibujar fuera del recuadro, deberíamos hacer que el lápiz desaparezca cuando nos salimos de él. Para ello, reemplaza el bloque __si__ con un __si / si no__. Mantén la misma condición para el __si__, muestra el lápiz si la condición se cumple, y escóndelo si no.

```scratch
al presionar BANDERA
subir lápiz
borrar
por siempre
	si y del ratón > -120 y y del ratón < 170 y x del ratón > -230 y x del ratón < 230
		ir a apuntador del ratón
		mostrar
		si ¿ratón presionado?
			bajar lápiz
		si no
			subir lápiz
		(fin si)
	si no
		esconder
	(fin si)
(fin por siempre)
```

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Todavía puedes dibujar dentro del recuadro? ¿Puedes dibujar fuera de él? ¿Qué le pasa al lápiz cuando entra y sale del recuadro?

Guarda tu proyecto.

##PASO 5: Goma de borrar

__Poder dibujar líneas está muy bien, pero a veces cometes un error y quieres borrarlo.__ Podemos conseguirlo con un lápiz especial que dibuja de color gris (el mismo gris que el fondo del recuadro).

Añade un nuevo objeto botón con el que seleccionar la goma de borrar. Usa el disfraz __resources/eraser__, cambiando su tamaño para que quepa en la parte inferior del escenario. Funciona de la misma manera que los botones de selección de colores, mandando un mensaje __borrar__.

El objeto lápiz debe responder al mensaje __borrar__ cambiando el color del lápiz al gris (recuerda cómo puedes usar el cuentagotas para seleccionar el color del fondo). También necesitará un disfraz que represente la goma: usa el mismo disfraz __resources/eraser__. __No olvides cambiar el centro del disfraz.__

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Funciona la goma para borrar líneas? ¿Funciona hasta los bordes del recuadro? ¿Es posible intercambiar entre goma de borrar y lápices?

Guarda tu proyecto.

##PASO 6: Estampados

Lo siguiente es añadir un sello con el que estampar pequeñas imágenes en el dibujo. 

1. Añade un nuevo objeto, usando cualquier imagen que te guste. Reduce su tamaño y ponlo en la parte inferior del escenario junto a los otros botones. Al pinchar en este objeto, hazlo __enviar a todos estampar__.
2. Añade un nuevo disfraz al objeto lápiz, con la misma imagen que has elegido para la estampa.
3. Selecciona el objeto lápiz y crea una nueva variable llamada __modo lápiz__ solo para este objeto. Usaremos esta variable para registrar si estamos dibujando o estampando.
4. Añade un nuevo programa que responda al mensaje __estampar__, que cambie el disfraz al de la estampa y fije el valor de __modo lápiz__ a __falso__.
5. Cambia los otros programas que responden a los otros mensajes (rojo, verde, azul, borrar) para que fijen el valor de __modo lápiz__ a __verdadero__.
6. Finalmente, comprobamos esta variable cuando el botón del ratón esté presionado para saber si debemos dibujar o estampar. Si __modo lápiz = verdadero__ dejamos el bloque __bajar lápiz__, y si no, usamos un bloque __sellar__.

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Funciona correctamente el sello para estampar?

¿Qué ocurre cuando vuelves a uno de los lápices de colores?

Guarda tu proyecto.

__Bien hecho, has completado el proyecto básico. ¡Intenta estos desafíos!__

##Desafío 1: Lápiz arco iris 

Añadamos un lápiz especial que pinta con los colores del arco iris. Es algo que no se puede hacer con lápices de verdad, así que vamos a demostrar cómo el ordenador amplía tus posibilidades. El secreto es el bloque __cambiar color del lápiz por__.


Primero añade el objeto que representa el color arco iris y añade otro disfraz al objeto lápiz:

1. Crea un nuevo objeto junto a los otros en la parte inferior del escenario, usando el disfraz __resources/rainbow-selector__ y haz que mande el mensaje __arco iris__ cuando se pincha en él.
2. Añade el disfraz __resources/rainbow-pencil__ al objeto lápiz.

Tienes que construir un programa que cambia el color del lápiz varias veces por segundo para crear el efecto arco iris (parece que cambiando el color por 5 cada 0.05 segundos funciona bien, pero prueba tus propios valores). La tarjeta de Scratch __cronómetro__ te recuerda cómo hacer que algo ocurra repetidamente. Usa un bloque __cambiar color del lápiz por__ en vez de un __cambiar cronómetro por -1__ dentro del ciclo.

También tienes que diseñar el programa para que solo cambie el color del lápiz cuando tienes el lápiz arco iris seleccionado, ¡si no todos los lápices tendrían el mismo efecto! Puedes conseguirlo de manera parecida a cómo el lápiz cambia entre sus modos de lápiz y de estampa. Tienes que crear una variable llamada __modo arco iris__ con el valor __verdadero__ cuando quieras el efecto arco iris, y __falso__ cuando no. Cada vez que el lápiz responda a un mensaje de uno de los botones, deberá fijar el valor de __modo arco iris__ que corresponda.

Controla el efecto arco iris usando lo aprendido cuando creaste el sello de estampar. Es decir, los programas que responden a los mensajes de los botones fijan los valores de dos variables cada vez: __modo lápiz__ y __modo arco iris__.

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Funciona el modo arco iris como querías?

¿Qué ocurre cuando vuelves a uno de los lápices de colores?

Guarda tu proyecto.

##Desafío 2: Teclas de atajo

En vez de usar los objetos de la parte inferior del escenario, puedes usar teclas del teclado para seleccionar los diferentes tipos de lápiz.

Yo usé estos atajos:
* borrar todo - t
* Goma de borrar - b
* Lápiz rojo -r 
* Lápiz azul - z
* Lápiz amarillo - a
* Lápiz verde - v
* Lápiz arco iris - i
* Sello para estampar - e

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Funciona cada tecla para seleccionar el tipo de lápiz correcto? ¿Funciona correctamente cada lápiz una vez seleccionado? ¿Siguen funcionando los botones en pantalla?

Guarda tu proyecto.

##Desafío 3: Grande y pequeño
Otra función que permiten los programas de dibujo es cambiar el tamaño del trazado del lápiz. Vamos a añadir esa función.

Existe una complicación: a veces hay que cambiar el tamaño del trazado del lápiz, y otras veces hay que cambiar el tamaño del disfraz del objeto lápiz. Depende de si estamos en modo lápiz o modo estampa.

Crea dos objetos más, llamados __agrandar__ y __reducir__. Usa las imágenes __resources/bigger-selector__ y __resources/smaller-selector__ y haz que manden mensajes __agrandar__ y __reducir__.

El objeto lápiz puede responder a los nuevos mensajes cambiando el tamaño del lápiz por 1 o el tamaño del disfraz por 10, dependiendo del valor de __modo lápiz__ (usa un bloque __si / si no__ similar al que usaste cuando el objeto elige entre bajar el lápiz o estampar). 
No olvides las teclas de atajo correspondientes. Yo elegí la flecha arriba y flecha abajo. 

Guarda tu proyecto.

Quizás hayas notado que al cambiar el tamaño del sello también cambia el tamaño del lápiz cuando vuelves al modo lápiz.
Para evitarlo, fija el tamaño al 100% cada vez que cambies al modo lápiz, para que la imagen del lápiz siempre tenga el tamaño correcto.

Para hacerlo aún mejor, haz que el sello recuerde su tamaño antes de seleccionar el lápiz y vuelva a ese tamaño cuando vuelvas a seleccionar el sello. La manera más fácil de lograrlo es creando una nueva variable __tamaño sello__, que actualizas con el tamaño del sello cada vez que cambias su tamaño. Cuando se selecciona el sello, cambia su tamaño según el valor de la variable.

##Prueba tu proyecto
__Pincha en la bandera verde.__

¿Funcionan los botones para cambiar el tamaño del lápiz?

¿Qué ocurre cuando seleccionas el sello, cambias su tamaño y luego seleccionas uno de los lápices?

Guarda tu proyecto.


__Bien hecho, hemos terminado. ¡Ahora a disfrutar de tu juego!__


No olvides que puedes compartir tu juego con amigos y familiares pinchando en __Compartir__ en el menú.
