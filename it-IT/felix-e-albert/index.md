---
title: Felix e Albert
level: Level 1
language: it-IT
stylesheet: scratch
embeds: "*.png"
materials: ["*.sb2", "*.pdf"]
---

# Introduzione { .intro }

In questo esercizio creiamo un gioco dove il gatto __Felix__ deve inseguire e catturare il topolino __Albert__ . Il giocatore controlla Albert con il mouse e deve cercare di evitare di essere catturato da Felix. Piu' a lungo si riesce ad evitare Felix e piu' punti si accumulano ma fai attenzione a non essere catturato perche' il tuo punteggio scendera tantissimo! 

![screenshot](felixalbert_screenshot.png)

<div class="pagebreak"></div>

# Passo 1: Felix segue il puntatore del mouse { .activity }

## Lista delle Attivita' { .check }

+ Crea un nuovo progetto.
+ Fai doppio-click nello **stage** vicino all'immagine (sprite) di Felix. Seleziona il tab `Sfondi` e clicca su `Scegli uno sfondo dalla libreria`. Qui seleziona lo sfondo chiamato `hall`. Adesso cancella lo sfondo bianco facendo click sulla `X bianca su sfondo nero in alto a destra`
+ Adesso fai click sullo sprite di Felix. Poi fai click sulla `i` in alto a sinistra dello sprite. Cambia il nome in **Felix**.
+ Accertati che Felix abbia uno stile di rotazione sinistra-destra facendo click su: <img alt="" class="inline" src="flip_arrows.png">. 
+ Torna indietro facendo click sulla freccia in alto a sinistra
+ Crea questo script per Felix:
```blocks
    quando si clicca su @
	per sempre
	  punta verso [puntatore del mouse v]
	  fai (10) passi
	  passa al costume seguente
	  suona tamburo (3) per (0.3) battute
	end
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde.

+ Felix insegue il puntatore del mouse?
+ Quando Felix si muove sembra che stia camminando?
+ Felix si muove alla giusta velocita'?

## Salva il tuo progetto { .save }


# Passo 2: Felix insegue Albert { .activity }

Ora vogliamo che Felix insegua il topolino Albert e non il puntatore del mouse.

## Lista delle Attivita' { .check }

+ Crea un nuovo sprite facendo click su `Scegli uno sprite dalla libreria` { .blockgrey } e seleziona **Mouse 1**.
+ Cambia il nome dello sprite in **Albert** facendo click sulla `i` in alto a sinistra dello sprite.
+ Passa al tab __Costumi__ e fai click su Albert nell'editor. Un rettangolo apparira' attorno ad Albert. Tira un angolo per rendere Albert piu' piccolo di Felix.
+ Accertati che Albert abbia uno stile di rotazione sinistra-destra facendo click su: <img alt="" class="inline" src="flip_arrows.png">. 
+ Torna indietro facendo click sulla freccia in alto a sinistra
+ Crea questo script per Albert:
```blocks
    quando si clicca su @
	per sempre
		raggiungi [puntatore del mouse v]
		punta verso [Felix v]
	end
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde.

+ Felix insegue il puntatore del mouse?
+ Felix insegue il topolino Albert?

## Salva il tuo progetto { .save }

# Passo 3: Felix ci dice quando ha catturato Albert { .activity }

Vogliamo che Felix riconosca quando ha catturato Albert e ce lo dica.

## Lista delle Attivita' { .check }

+ Cambia lo script per Felix in questo modo:
```blocks
    quando si clicca su @
	per sempre
		punta verso [puntatore del mouse v]
		fai (10) passi
		passa al costume seguente
		suona tamburo (3) per (0.3) battute
		se <sta toccando [Albert v] > allora
			dire [Preso!!!] per (1) secondi
		end
	end
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde.

+ Felix ti dice quando ha catturato Albert?

## Salva il tuo progetto { .save }

<div class="pagebreak"></div>

# Passo 4: Albert diventa un fantasmino quando viene catturato da Felix { .activity }

Anziche' far dire a Felix quando prende Albert vogliamo che Albert diventi un fantasmino.

## Lista delle Attivita' { .check }

+ Cambia lo script per Felix in modo da inviare un messaggio quando prende Albert:
```blocks
    quando si clicca su @
	per sempre
		punta verso [puntatore del mouse v]
		fai (10) passi
		passa al costume seguente
		suona tamburo (3 v) per (0.3) battute
		se <sta toccando [Albert v]> allora
        	invia a tutti [preso v]
			suona tamburo (17 v) per (0.2) battute
            attendi (1) secondi
		end
	end
```
+ Aggiungi un nuovo costume per Albert facendo click sullo sprita e selezionando il tab `Costumi`. Da qui seleziona `Scegli un costume dalla libreria` { .blocklightgrey }. Seleziona il costume **ghost2-a**.  
+ Rendi il fantasmino piu' piccolo facendo click sullo sprite nell'editor e trascinando un angolo.
+ Cambia il nome dei costumi di Albert. Il topolino chiamalo `vivo` ed il fantasmino chiamalo `morto`.
+ Creau un nuovo script per Albert in modo che si trasformi in un fantasmino:
```blocks
	quando ricevo [preso v]
	passa al costume [morto v]
	attendi (1) secondi
	passa al costume [vivo v]
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde.

+ Albert si trasforma in un fantasmino quando viene catturato?
+ Senti Felix emettere il giusto suono al momento giusto?
+ Felix rimane fermo abbastanza a lungo per permettere ad Albert di fuggire?

## Salva il tuo progetto { .save }

<div class="pagebreak"></div>

# Passo 5:  Manteniamo il punteggio { .activity }

Aggiungiamo adesso un punteggio al gioco in modo da sapere quanto siamo bravi a tenere Albert in vita.

Il punteggio inizia da zero e viene incrementato di 1 per ogni secondo. Se Felix riesce a catturare Albert il punteggio viene diminuito di 100 punti.

## Lista delle Attivita' { .check }

+ Crea una variabile, per tutti gli sprite, che si chiama punteggio. Fai click su `Script`, poi seleziona `Variabili e Liste` e fai click su `Crea una variabile` { .blockorange }. Inserisci `punteggio` come nome della variabile ed assicurati che `Per tutti gli sprite` sia selezionato.
+ Nello stage, crea questi due script:
```blocks
    quando si clicca su @
	porta [punteggio v] a (0)
	per sempre
		cambia [punteggio v] di (1)
		attendi (1) secondi
	end

	quando ricevo [preso v]
	cambia [punteggio v] di (-100)
```

## Verifica il tuo progetto { .flag }

Fai click sulla bandierina verde.

+ Il punteggio viene incrementato di 1 ogni secondo?
+ Il punteggio viene ridotto di 100 punti quando Albert e' catturato?
+ Cosa succede se Albert e' catturato ed il punteggio e' inferiore a 100? 
+ Il punteggio torna a zero quando inizi una nuova partita?

## Salva il tuo progetto { .save }

Ben fatto, hai finito!!! Adesso puoi finalmente divertirti con il tuo gioco!!!

Ehi, non dimenticare che puoi condividere il tuo gioco con tutti i tuoi amici e familiari. Basta che fai selezioni il menu File e poi **Share to website**!!