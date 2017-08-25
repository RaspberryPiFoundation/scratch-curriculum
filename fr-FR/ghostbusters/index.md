---
title: SOS Fantômes
description: Apprends à créer un jeu pour attraper des fantômes !
layout: project
notes: "Ghostbusters - notes.md"
---

# Introduction { .intro }

Vous allez créer un jeu pour attraper des fantômes !

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/60787262/?autostart=false" frameborder="0"></iframe>
  <img src="images/ghost-final.png">
</div>

# Étape 1: Animer un fantôme { .activity }

## Liste de contrôle d'Activité { .check }

+ Démarrez un nouveau projet de Scratch et supprimez le lutin de chat pour que votre projet soit vide. Vous pouvez trouver l'éditeur scratch en ligne à <a href="http://jumpto.cc/scratch-new" target="_blank">jumpto.cc/scratch-new</a>.

+ Ajoutez un nouveau lutin de fantôme et un arrière-plan approprié.

	![screenshot](images/ghost-ghost.png)

+ Ajoutez ce code au fantôme pour qu'il apparaisse et disparaisse constamment :

	```blocks
		when flag clicked
		forever
			hide
			wait (1) secs
			show
			wait (1) secs
		end
	```

+ Testez le code de votre fantôme en appuyant sur le drapeau vert.

## Sauvegarder votre projet { .save }

# Étape 2: Fantômes aléatoires { .activity }

Votre fantôme est trop facile à attraper parce qu'il ne bouge pas !

## Liste de contrôle d'Activité { .check }

+ Au lieu de rester au même endroit, Scratch peut choisir les coordonnées x et y de façon aléatoire. Ajouter un bloc `go to` {.blockmotion} [en français : `aller à`] au code du fantôme pour que ça ressemble à ceci :

	![screenshot](images/ghost-random.png)

+ Testez votre fantôme de nouveau et vous devriez remarquer qu'il apparaît dans un endroit différent à chaque fois.

## Sauvegarder votre projet { .save }

## Défi: Plus aléatoire {.challenge}
Pouvez-vous faire [en français : `attendre`] `wait` {.blockcontrol} votre fantôme pendant une durée de temps aléatoire avant de réapparaître ?  Pouvez-vous utiliser le bloc [en français : `mettre à de la taille initiale`] `set size` {.blocklooks} pour donner une taille aléatoire à votre fantôme à chaque fois qu'il apparaît ?

## Sauvegarder votre projet { .save }

# Étape 3: Attraper des fantômes { .activity }

Donnons la possibilité au joueur d'attraper les fantômes !

## Liste de contrôle d'Activité { .check }

+ Pour permettre au joueur d'attraper un fantôme, ajoutez ce code :

	```blocks
		when this sprite clicked
		hide
	```

+ Testez votre projet. Pouvez-vous attraper les fantômes lorsqu'ils apparaissent ? Si vous avez du mal à les attraper, vous pouvez jouer avec un plein écran en cliquant sur le bouton suivant :

	![screenshot](images/ghost-fullscreen.png)

## Défi: Ajouter du son { .challenge }
Pouvez-vous ajouter un bruit à chaque fois qu'un fantôme est attrapé ?

## Sauvegarder votre projet { .save }

# Étape 4: Ajouter le score { .activity .new-page }

Rendons les choses plus intéressantes en gardant le compte du score.

## Liste de contrôle d'Activité { .check }

+ Pour garder le compte de score du joueur, il faut le stocker quelque part. Une __variable__ est un endroit pour garder des données qui peuvent changer, commme un score.

	Pour créer une variable, cliquez sur l'onglet 'Scripts', sélectionnez `Données` {.blockdata}, puis cliquez sur 'Créer une variable'.

	![screenshot](images/ghost-score.png)

	Tapez 'score' comme nom de variable, vérifiez si ce nom est disponible pour tous les lutins et cliquez sur 'OK' pour créer la variable. Vous allez ensuite voir plusieurs blocs de code qui peuvent être utilisés avec votre variable `score` {.blockdata}.

	![screenshot](images/ghost-variable.png)

	Vous allez aussi voir le score en haut à gauche de la scène.

	![screenshot](images/ghost-stage-score.png)

+ Lorsque vous commencez un nouveau jeu (en cliquant sur le drapeau), vous devez remettre le score à 0 :

	```blocks
	when flag clicked
	set [score v] to [0]
	```

+ Vous devrez ajouter 1 au score à chaque fois qu'un fantôme sera attrapé :

	![screenshot](images/ghost-change-score.png)

+ Exécutez votre programme de nouveau et attrapez quelques fantômes. Votre score change-t-il ?

## Sauvegarder votre projet { .save }

# Étape 5: Ajouter un compte à rebours { .activity }

Vous pouvez rendre votre jeu encore plus intéressant en limitant chaque partie à 10 secondes pour attraper le plus de fantômes possible.

## Liste de contrôle d'Activité { .check }

+ Vous pouvez utiliser une autre variable pour stocker le temps qui vous reste. Cliquez sur la scène et créez une nouvelle variable nommée 'time' :

	![screenshot](images/ghost-time.png)

+ Le compte à rebours devrait fonctionner ainsi :

	+ Le compte à rebours devrait commencer à 10 secondes ;
	+ Le compte à rebours devrait décompter chaque seconde ;
	+ Le jeu devrait s'arrêter lorsque le compte à rebours arrive à 0.

	Voici le code qui vous permettra de réaliser cela. Vous pouvez ajouter celui-ci à votre __scène__ :

	```blocks
		when flag clicked
		set [time v] to [10]
		repeat until <(time) = [0]>
			wait (1) secs
			change [time v] by (-1)
		end
		stop [all v]
	```

	Voici comment vous pouvez ajouter le code `repeat until`{.blockcontrol}`time`{.blockdata}`= 0`{.blockoperators} :

	![screenshot](images/ghost-timer-help.png)

+ Déplacez votre variable 'time' vers le côté droit de votre scène. Vous pouvez aussi faire un clic droit sur l'affichage de la variable et choisir 'grande lecture' afin de changer la présentation du temps.

	![screenshot](images/ghost-readout.png)

+ Demandez à un ami de tester votre jeu. Combiens de points peut-il marquer ? Si votre jeu est trop facile, vous pouvez :

	+ Donner moins de temps au joueur ;
	+ Faire en sorte que les fantômes apparaissent moins souvent ;
	+ Réduire la taille des fantômes.

	Testez votre jeu à quelques reprises jusqu'à ce que vous soyez satisfaits du niveau de difficulté.

## Sauvegarder votre projet { .save }

## Défi: Plus d'objets {.challenge}
Pouvez-vous ajouter d'autres objets à votre jeu ?

![screenshot](images/ghost-final.png)

Vous devrez penser aux objets que vous allez ajouter. Pensez à ces questions :

+ Quelle sera sa taille ?
+ Apparaîtra-t-il plus ou moins souvent que les fantômes ?
+ À quoi correspond-il au niveau de l'image et du son lorsqu'on l'attrape ?
+ Combien de points devrait-on gagner (ou perdre) lorsqu'on l'attrape ?

Si vous avez besoin d'aide pour ajouter un autre objet, vous pouvez suivre de nouveau les étapes ci-dessus !

## Sauvegarder votre projet { .save }
