---
title: Fuochi Artificiali
level: Level 1
language: it-IT
stylesheet: scratch
embeds: "*.png"
materials: ["*.sb2","Resources/*.wav", "Resources/*.png", "*.pdf"]
---

# Introduzione { .intro }

In questo progetto creiamo l'esplosione dei fuochi artificiali su una citta' Italiana.

![screenshot](fuochi_artificiali_screenshot.png)

<div class="pagebreak"></div>

# Passo 1: Crea un razzo che vola verso il puntatore del mouse { .activity }

Importiamo tutte le immagini necessarie per questo gioco

## Lista delle Attivita' { .check }

+ Crea un nuovo progetto Scratch. Rimuovi il gatto Felix con click-destro e seleziona **cancella**.
+ Nel tab `Sfondi` aggiungi un nuovo sfondo. Fai click su `Carica uno sfondo da un file`. Vai nella cartella `Resources` e seleziona **torino_sfondo.png**
+ Fai click su `Carica uno sprite da un file` e seleziona **rocket.png** dalla cartella `Resources`
+ Rendi il razzo invisibile all'inizio del gioco
```blocks
	quando si clicca su @
	nasconditi
```
+ Adesso vogliamo che quando facciamo click il razzo voli verso il puntatore del mouse. Aggiungi il blocco `quando si preme il tasto spazio`, sotto di questo visualizza il razzo e fallo scivolare (volare) verso il puntatore del mouse
```blocks
	quando si preme il tasto [spazio v]
	mostrati
	scivola in (1) secondi a x: (x del mouse) y: (y del mouse)
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde, posiziona il tuo mouse nello stage a premi la barra spaziatrice.

+ Vedi il razzo apparire e muoversi verso il puntatore del mouse?
+ Cosa succede se muovi il mouse e premi dinuovo la barra spaziatrice?

## Lista delle Attivita' { .check }

+ I fuochi artificiali tipicamente non volano lateralmente, quindi facciamo in modo che il razzo si muova verticalmente dal basso su fino al puntatore del mouse. Prima di visuallizare il razzo, inserisci il blocco `vai a` in modo che il razzo vada nella parte bassa dello schermo e sia allineato con il puntatore del mouse.
```blocks
	quando si clicca su @
	nasconditi

	quando si preme il tasto [spazio v]
	vai a x: (x del mouse) y: (-200)
	mostrati
	scivola in (1) secondi a x: (x del mouse) y: (y del mouse)
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde, posiziona il tuo mouse nello stage e premi la barra spaziatrice.

+ Vedi il razzo apparire e muoversi dal fondo dello schermo verso il puntatore del mouse?
+ Cosa succede se muovi il mouse e premi dinuovo la barra spaziatrice?

## Lista delle Attivita' { .check }

+ Infine fai in modo che il razzo venga lanciato quando fai click anziche' quando premi la barra spaziatrice. Per far questo possiamo racchiudere il nostro script in un blocco `per sempre se fai click` e sostituire il blocco `quando si preme il tasto spazio` con il blocco `quando di clicca su bandierina`. Come ultimo passo assicurati che il razzo sia invisibile prima del click con il mouse.
```blocks
	quando si clicca su @
	nasconditi
	per sempre
		se <tasto del mouse premuto> allora
			vai a x: (x del mouse) y: (-200)
			mostrati	
			scivola in (1) secondi a x: (x del mouse) y: (y del mouse)		
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde e fai click con il mouse nello stage. Adesso fai click in un altro punto

## Cose da provare { .try }

+ Prova a rendere alcuni razzi piu' veloci o lenti degli altri.
+ Prova a cambiare la posizione iniziale del razzo in modo che percorra un arco nel raggiungere il puntatore del mouse.

## Salva il tuo progetto { .save }

<div class="pagebreak"></div>

# Passo 2: Fai esplodere il razzo { .activity }

## Lista delle Attivita' { .check }

+ Il primo passo per far esplodere il razzo e fargli emettere un boato (**Resources/bang.wav**) prima che inizi a volare. Quindi una volta che ha raggiunto il puntatore del mouse lo facciamo scomparire. Per importare un suono vai al tab `Suoni` e fai click su `Carica un suono da un file`.
```blocks
	quando si clicca su @
	nasconditi
	per sempre
		se <tasto del mouse premuto> allora
			vai a x: (x del mouse) y: (-200)
			produci suono [bang v]
			mostrati	
			scivola in (1) secondi a x: (x del mouse) y: (y del mouse)
			nasconditi		
```

+ Adesso fai in modo che il razzo invii un segnale nel momento in cui esplode. Dopo faremo in modo di ascoltare questo messaggio.
```blocks
	quando si clicca su @
	nasconditi
	per sempre
		se <tasto del mouse premuto> allora
			vai a x: (x del mouse) y: (-200)
			produci suono [bang v]
			mostrati	
			scivola in (1) secondi a x: (x del mouse) y: (y del mouse)
			nasconditi
			invia a tutti [esploso v]		
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde. 

+ Quando il razzo raggiunge il puntatore del mouse emette un boato e scompare?

## Lista delle Attivita' { .check }

+ Crea un nuovo sprite caricando il file **Resources/firework1.png**
+ Quando lo sprite appena aggiunto, riceve il messaggio `esplosione` deve scomparire, posizionarsi sul razzo usando il blocco `vai a`, apparire per 1 secondo e poi sparire dinuovo.
```blocks
	quando ricevo [esploso v]
	nasconditi
	raggiungi [Rocket v]
	mostrati
	attendi (1) secondi
	nasconditi
```

## Verifica il tuo progetto { .flag }

Lancia un altro razzo.

+ Riesci a vedere il razzo che esplode ed il fuoco artificiale comparire?
+ Cosa succede se tieni premuto il tasto sinistro del mouse e contemporaneamente lo muovi? (Non ti preoccupare, risolveremo il problema dopo)

## Salva il tuo progetto { .save }

# Passo 3: Rendi ogni esplosione unica { .activity }

## Lista delle Attivita' { .check }

+ Adesso possiamo rendere ogni esplosione unica usando il blocco `cambia effetto colore` { .blockpurple } con un colore a caso compreso tra **1** e **200** prima di visualizzare il fuoco d'artificio.
```blocks
	quando ricevo [esploso v]
	nasconditi
	porta effetto [colore v] a (numero a caso tra (1) e (200))
	raggiungi [Rocket v]
	mostrati
	attendi (1) secondi
	nasconditi
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde. 

+ Le esplosioni sono tutte di un colore diverso?

## Lista delle Attivita' { .check }

+ Adesso aggiungiamo altri tipi di fuochi artificiali aggiungendo nuovi costumi per lo sprite. Usa __Resources/firework2.png__ e __Resources/firework3.png__ e cambia il costume per ogni razzo prima di visualizzarlo.

##Verifica il tuo progetto { .flag}

Fai click sulla bandierina verde.

+ Riesci a lanciare tipi diversi di fuochi artificiale?

## Lista delle Attivita' { .check}

+ Infine rendiamo l'esplosione piu' grande dopo che il razzo esplode! Anziche' aspettare per 1 secondo, porta la dimensione dello sprite al **5%** e dopo che e' visualizzato aumenta la dimensione dello sprite di **2** per **50** volte usando un blocco `ripeti` { .blockorange }.
```blocks
	quando ricevo [esploso v]
	nasconditi
	porta effetto [colore v] a (numero a caso tra (1) e (200))
	raggiungi [Rocket v]
	mostrati
	porta dimensione al (5) %
	ripeti (50) volte
		cambia dimensione di (2)
	fine
	nasconditi
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde.

+ L'effetto esplosivo inizia dal centro del razzo e si espande gradualmente?

## Cose da provare { .try }

+ Perche' non provare a rendere ciascun esplosione ancora piu' unica variando la dimensione e la velocita' dell'esplosione stessa?

## Salva il tuo progetto { .save }

# Passo 4: Risolvere il problema dell'esplosione incompleta { .activity }

Ti ricordi che nei passi precedenti abbiamo riscontrato che tenendo premuto il pulsante del mouse l'esplosione del razzo era incompleta? Cio' succede perche' quando il razzo invia il messagio `esploso`, lo script ricomincia immediatamente e riposiziona il razzo al fondo dello schermo. Cio' avviene prima che l'esplosione si muove alla posizione del razzo. 

## Lista delle Attivita' { .check }

+ Per risolvere questo problema, possiamo rimpiazzare il blocco `invia a tutti` con un blocco `invia a tutti e attendi`. In questo modo il ciclo non si ripetera' finche' l'esplosione non sara' completamente terminata.
```blocks
	quando si clicca su @
	nasconditi
	per sempre
		se <tasto del mouse premuto> allora
			vai a x: (x del mouse) y: (-200)
			produci suono [bang v]
			mostrati	
			scivola in (1) secondi a x: (x del mouse) y: (y del mouse)
			nasconditi
			invia a tutti [esploso v] e attendi	
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde, tieni premuto il tasto sinistro del mouse and muovi il mouse in punti diversi dello stage. 

+ L'effetto esplosivo appare al posto giusto ed al momento giusto?

## Salva il tuo progetto { .save }

Ben fatto!!! Hai finito con questo esercizio. Adesso divertiti con il tuo nuovo gioco!!!

Ehi, non dimenticare che puoi condividere il tuo gioco con tutti i tuoi amici e familiari. Basta che fai selezioni il menu File e poi **Share to website**!!