<!--
*************************************************************************************************
Comentaris:

Traducció Selma Casanovas
	
	- FLAG ->  Bandera, bandereta?, banderola? (Senyera, per més correcte que sigui, ho penso en quatribarrat, no hi puc fer més) 
	- script. Crec que ja en les trads anteriors ho vaig deixar a script: cap proposta?
	- Traduccions pendents de les 'Scratch Cards?' 
	  - Cronòmetre
*************************************************************************************************
-->

Nivell 3

#Caixa de Pintures

__Introducció:__En aquest projecte construireu una eina per dibuixar. Hi podreu pintar, canviar de color, netejar la pantalla, estampar, i moltes més coses!!￼##PAS 1: Arrossegar i dibuixarComençarem amb un llapis que dibuixa quan l'arrossegueu per l'Escenari.1. Comenceu un projecte nou de Scratch. Elimineu el gat (premeu el botó dret damunt del gat i llavors __esborra__)2. Seleccioneu l'__Escenari__ i llavors la pestanya __Fons__. Importeu el fons __indoors/chalkboard__.3. Creeu una nova animació que es digui __llapis__, usant el recurs __resources\green-pencil.__4. Canvieu a la pestanya __vestits__, cliqueu __Edita__ per aquest vestit, i feu que el centre de la imatge sigui a la punta del llapis. Per fer-ho, cliqueu __Fixa el centre del vestit__ i arrossegueu les línies fins que passin per la punta.5. Feu que el llapis segueixi el ratolí per tot l'escenari utilitzant els blocs __per sempre__ i __vés a__.

```
		al prémer BANDERA
		per sempre
			vés a punter del ratolí
		(fi per sempre)	
```

__Ara el que volem és fer servir aquesta animació com un llapis de veritat.__ Si mireu dins la secció __llapis__, hi veureu diversos blocs per controlar una eina de dibuix. Els que ens interessen ara són __baixa el llapis__ i __puja el llapis__6. Controlarem el llapis amb el ratolí: quan el botó del ratolí estigui premut, el llapis "tocarà el paper" i quan no ho estigui, el llapis estarà aixecat. Una manera de fer-ho és amb un bloc __si… si no__ i el bloc __ratolí premut?__:``` 
        al prémer BANDERA
		per sempre
			vés a punter del ratolí
			si ratolí premut?
	           baixa el llapis
	        si no
			   puja el llapis
			(fi si)
		(fi per sempre)
```

##Proveu el projecte__Cliqueu la bandera verda.__Comproveu que el llapis va allà on va el ratolí. Què passa si manteniu el botó del ratolí premut mentre moveu el ratolí? (No cal que us preocupeu encara pel color del llapis).

DESEU EL PROJECTE 7. Ben aviat us trobareu que la pantalla se us omple de gargots. Per netejar la pantalla, podem fer servir el bloc __neteja__.
```
		al prémer BANDERA
		neteja
		per sempre
			vés a punter del ratolí
			si ratolí premut?
	           baixa el llapis
	        si no
			   puja el llapis
			(fi si)
		(fi per sempre)	
```
##Proveu el projecte__Cliqueu la bandera verda.__Comproveu que el que havíeu dibuixat desapareix en clicar la bandera verda.DESEU EL PROJECTE##￼￼￼PAS 2: Netejar la pantallaPer no haver de parar i reiniciar tot el programa cada cop que volem netejar, afegirem un __botó de neteja__ de pantalla. Utilitzarà el mateix bloc __neteja__ que hem vist abans.1. Creeu una nova animació a partir del vestit __resources/cancel button__. 
2. Poseu-li un nom. Per exemple __neteja__.3. Posicioneu l'animació a la part baixa de la pantalla, prop del racó esquerre.4. Programeu l'animació amb aquest simple script:
```
	Al prémer NETEJA
		neteja
```##Proveu el projecte__Cliqueu la bandera verda.__Comproveu que el botó neteja sí que neteja la vostra pantalla.DESEU EL PROJECTE##PAS 3: Canviar de colorFins aquí només hem pogut dibuixar línies de color blau. Anem ara a dibuixar amb uns quants colors diferents! Afegirem algunes animacions al peu de la pantalla. Les animacions semblaran botons de colors. Si en cliquem un, canviarà el color de la línia que dibuixem. Per tal de saber quin color tenim activat, el botó canviarà també el color de l'animació llapis.1. Afegiu una animació nova, que anomenarem __vermell__, a partir del vestit __resources/red-selector costume__. 
2. Poseu-la en algun lloc a la part baixa de la pantalla, prop del __botó neteja__.3. En prémer l'animació vermell, hauria d'enviar a tots el missatge __vermell__.
```
al prémer VERMELL
enviar a tots VERMELL
```__Ja està: això és tot el que fa aquesta animació. El gruix de la feina el farà el llapis.__￼￼￼￼Al llapis, importeu un nou vestit, __resources/red-pencil__. Feu que el centre del vestit se situi a la punta del llapis, tal com ho heu fet pel vestit verd original.4. Afegiu un script nou al llapis. Quan el llapis rebi el missatge __vermell__, hauria de canviar al vestit de llapis vermell i el color amb què pinta hauria de canviar a vermell (utilitzeu el blocs __fixa el color del llapis a__).__Pista:__ si cliqueu al quadret de color del bloc __fixa el color del llapis a__, podeu escollir el color exacte de la vostra animació __vermell__ amb el recollidor de mostres.
```
al rebre VERMELL
canvia el vestit a llapis-vermell
fixa el color del llapis a (vermell)
```##Proveu el projecte__Cliqueu la bandera verda.__Comenceu dibuixant una línia. Cliqueu llavors el selector vermell i dibuixeu una mica més. Que canvia de vestit, el llapis? I que pinta vermell? I ja pinta des de la punta del llapis? O des d'alguna altra part del llapis?DESEU EL PROJECTE5. Repetiu això mateix per als selectors de color blau, groc i verd.##Proveu el projecte__Cliqueu la bandera verda.__Comproveu que tots els botons selectors funcionen. Tots ells canvien el vestit al color esperat? Tots ells fan que el llapis dibuixi en el color esperat? Tots ells pinten des de la punta del llapis?DESEU EL PROJECTE##PAS 4: Dibuixar només dins els límitsPotser ja us heu adonat que es pot pintar per tot l'__Escenari__, fins i tot a les vores. Ara voldríem mantenir els traços només a la part central de l'__Escenari__. Això s'aconsegueix fent que el llapis no pugui sortir de l'àrea de dibuix. La part de color gris clar.￼￼￼￼￼￼￼Si ho recordeu, Scratch defineix els punts a partir dels eixos x i y de coordenades. La nostra àrea de dibuix se situa entre els valors 230 i -230 de l'eix x, i els valors 170 i -120 de l'eix y. Aquests valors es poden usar en un bloc __si__, que s'asseguri que el ratolí és dins l'àrea permesa abans de fer-hi anar el llapis.Per fer-ho, posarem un nou bloc __si__ al voltant del bloc __vés a… si__ que ja teníem, i dins aquest nou __si__ comprovarem la condició següent:
ratolí y > -120 i ratolí y < 170i ratolí x > -230 i ratolí x < 230__Nota__: per construir això us caldran 3 blocs __i__: un per a les dues condicions sobre ratolí x, un altre per les de ratolí y, i finalment un altre per unir-les totes:
```
neteja
per sempre 
si ratolí y > -120 i ratolíi y < 170i ratolí x > -230 i ratolí x < 230
 vés a punter del ratolí
```Com que no es pot pintar fora de l'àrea de dibuix, podem amagar el llapis al sortir-ne. Per fer-ho, en lloc d'un bloc __si__ n'hi posarem un de __si…si no__. En cas que es compleixi la condició, hi posarem una intrucció __mostra__, i en cas que no, __amaga__.

```
	al prémer BANDERA
		puja el llapis
		neteja
		per sempre
			si ratolí y > -120 i ratolíi y < 170           		i ratolí x > -230 i ratolí x < 230
            	mostra
				vés a punter del ratolí
				si ratolí premut?
	           		baixa el llapis
	        	si no
			   		puja el llapis
				(fi si premut)
			si no
			 	amaga
			(fi si area dibuix)
		(fi per sempre)			
```##Proveu el projecte__Cliqueu la bandera verda.__Encara podeu dibuixar dins l'àrea de dibuix? I fora? Què li passa, al llapis, quan sortiu de l'àrea de dibuix i hi torneu a entrar?￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼DESEU EL PROJECTE##PAS 5: Esborrador__￼￼￼￼Pintar línies està bé però a vegades fem algun eror que volem esborrar.__ Ho farem amb un nou llapis que pinta en gris (el color del fons!).Afegiu una nova animació-botó a l'__Escenari__ per seleccionar l'esborrador, a partir del vestit __resources/eraser__. Feu-lo més petit si cal perquè hi càpiga a la base de la pantalla. Funcionarà com els altres selectors, però enviarà un missatge __ESBORRADOR__.Responent a aquest missatge, l'animació __llapis__ canviarà el color de dibuix a gris i el vestit al mateix del botó esborrador (__resources/eraser__). __Penseu-hi a reposicionar el centre de l'animació també en aquest cas.__##Proveu el projecte__Cliqueu la bandera verda.__Comproveu que l'esborrador elimina les línies dibuixades. Podeu tornar al llapis, un cop heu seleccionat l'esborrador?
DESEU EL PROJECTE##￼PAS 6: EstampacionsLa propera cosa que podem afegir és una eina d'estampació, per estampar petites imatges al nostre dibuix.Passos a seguir:1. Afegiu una animació nova, a partir del vestit o imatge que preferiu. Feu-la de la mida dels altres botons que ja hi ha a la base de la pantalla (esborrador, neteja, selectors de color). En clicar aquesta animació, s'enviarà a tots el missatge __ESTAMPA__.2. A l'animació __llapis__, afegiu el mateix vestit que heu escollit per a l'estampació.3. A l'animació __llapis__ hi afegirem una variable, que es dirà __modeLlapis__ (només per aquesta animació). La farem servir per recordar si estem pintant o bé estampant.4. També al __llapis__, hi afegirem un script que reaccioni al missatge __ESTAMPA__. Ha de canviar al vestit de l'estampa i posar el __modeLlapis__ a __fals__.5. Canvieu la resposta a la resta de missatges de canvi d'eina (blau,vermell,groc,verd,esborrador) perquè tots posin el __modeLlapis__ a __cert__.6. Finalment, allà on hi tenim la instrucció __baixa el llapis__, ara ho farem només si __modeLlapis__ està a __cert__, si és __fals__, utilitzarem la instrucció __estampa__. ##Proveu el projecte__Cliqueu la bandera verda.__Comproveu que l'eina d'estampació funciona. Què passa si torneu a les eines de llapis? Encara funcionen?
DESEU EL PROJECTE
__Molt ben fet!!! heu completat el projecte bàsic.Us atreviu amb uns quants reptes?__￼￼￼
##Repte 1: Llapis MulticolorAra afegirem un llapis especial que pinta en multicolors. Això no ho podem fer amb els llapis o rotuladors del món real, i per això té la gràcia de mostrar-nos com un ordinador ens permet de fer coses diferents. El secret de com funciona és al bloc de canvi de color de llapis.Per començar, afegireu el botó per escollir aquesta eina, i el vestit corresponent a l'animació llapis:1. Creeu una nova animació per seleccionar aquest llapis especial i poseu-la amb la resta de selectors a la part baixa de la pantalla. Feu servir el vestit __resources/rainbow-selector__ i feu que envii a tots __MULTICOLOR__ en ser clicat.2. Afegiu també aquest vestit (__resources/rainbow-pencil__) a l'animació __llapis__.Fareu un script que canvïi el color de tinta uns quants cops per segon per crear l'efecte Arc de Sant Martí (Nosaltres hem trobat que canviant-lo 5 unitats cada 0.05 segons funciona prou bé, però podeu provar-ho amb altres valors). La tarja Scratch __Cronòmetre__ mostra com fer que una cosa passi a cada cert interval de temps. Useu un bloc __augmenta 5 el color del llapis__ en lloc de __augmenta -1 el temps__ dins el bucle.També us caldrà controlar el bucle perquè només canvii el color quan hi ha seleccionat el llapis multicolor, altrament tots els llapis tindrien el mateix efecte!!! Això es pot controlar amb una nova variable __canviMulticolor__ que sigui __cert__ per aquest llapis i fal per a la resta d'eines. Cada cop que el llapis respon a un missatge de selecció d'eina s'hauria de posar el valor corresponent a aquesta variable.Fes servir el que has après per controlar l'efecte multicolor. Els scripts que reaccionen als missatges de selecció de llapis hauran d'actuar sobre dues variables: modeLlapis i canviMulticolor.##Proveu el projecte__Cliqueu la bandera verda.__Funciona com esperaves, el llapis multicolor? Què passa quan tornes a escollir una eina de llapis normal?DESEU EL PROJECTE
##￼￼￼￼￼￼￼￼￼Repte 2: Combinacions de teclesEn lloc d'utilitzar les animacions a la base de l'escenari per seleccionar cada eina, podeu fer servirRather than using the tool-selection sprites at the bottom of the stage, you can use the keyboard to select the different tools.You can use the when [] key pressed blocks to respond to the keyboard. For each key you want to use, you’ll need another when [] key pressed block, which sends the same message as the respective tool-selection sprite does when its clicked. Add these scripts to the stage.I used these shortcuts:* Clear all - a* Eraser - e* Red pencil -r 
* Blue pencil - b
* Yellow pencil - y
* Green pencil - g
* Rainbow pencil - w￼￼￼* Stamp - s
##Proveu el projecte__Cliqueu la bandera verda.__￼￼Do all the tools get selected with the correct keyboard shortcuts? Does each of the tools work correctly when you select it with keyboard? Are the correct tools still selected with the tool-selection sprites on the stage?SAVE YOUR PROJECT

##Challenge 3: Big and SmallAnother feature that most drawing packages have is the ability to change thesize of the pencil. Let’s add that.There’s one complication, though, which is that sometimes the resizing needs to change the pen size and sometimes it needs to change the pencil sprite’s costume size. It depends on whether you’re using a pencil or a stamp.Create two new tool-selection sprites, called bigger and smaller. They should have the resources/bigger-selector and resources/smaller-selector costumes and should send the bigger and smaller messages.The pencil sprite can respond to the messages by changing either the pen size by 1 or the costume size by 10, depending on the value of pencil mode (use an if-else block, similar to how the sprite chooses between putting the pen down or stamping)Don’t forget the keyboard shortcuts for the bigger and smaller tools. I used the up and down arrows.SAVE YOUR PROJECTWhat you should have noticed is that changing the size of the stamp also changes the size of the pencil on-screen when you change to that tool.To stop that, you need to set the size to 100% every time you change to a pencil tool. so that the tools look the right size.To make it even better, have the stamp remember what size it was before you selected the pencil and go back to that size when you select the stamp tool again. The easiest way to do that is to create a new variable called stampSize, that is updated with the current size every time the stamp is resized. When the stamp tool is selected, it can set its size from the contents of this variable.￼￼￼￼￼￼￼￼￼##￼Test Your Project__Click on the green flag.__
Do the size controls work for the pencils?What happens if you switch to the stamp, change the size and then switch back to a pencil?SAVE YOUR PROJECT
￼￼￼￼￼￼￼__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!