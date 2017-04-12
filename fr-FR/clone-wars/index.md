---
title: Clone Wars
description: Apprend à programmer ton propre jeu de bataille spatial.
layout: project
notes: "Clone Wars - notes.md"
---

## La communauté a contribué pour le projet { .challenge .pdf-hidden }
Ce projet a été créé avec Eric. Si vous voudriez contribuer à un projet, vous devez vous mettre en contact avec nous sur Github(https://github.com/CodeClub).

# Introduction { .intro }

Dans ce projet vous apprendrez à créer un jeu dans lequel vous devez sauver la Terre de monstres spatiaux.

<div class="scratch-preview">
 <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/46018140/?autostart=false" frameborder="0"></iframe>
 <img src="images/invaders-final.png">
</div>

# Étape 1 : Fabrication d'un Vaisseau spatial { .activity }

Faisons un vaisseau spatial qui défendra la Terre!

##liste de contrôle d'activité { .check }

+ Commencez un nouveau projet scratch et supprime le lutin de chat pour que votre projet soit vide. Vous pouvez trouver l'éditeur de scratch en ligne à <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Ajoutez le fond 'stars' et le lutin 'Spaceship' à votre projet. Faites rétrécir le vaisseau spatial et déplacez-le près du bas de l'écran.

	![screenshot](images/invaders-sprites.png)

+Ajoutez le code pour déplacer votre vaisseau spatial à gauche quand la touche de direction gauche est appuyée. Vous devrez utiliser ces blocs :

	```blocks
		quand le drapeau prressé
		répéter indéfiniment
			Si <touche [Flèche gauche v] pressé?> alors
				ajouter (-4) à x
			end
		end
	```

+ Ajoutez le code pour déplacer votre vaisseau spatial à droite quand la touche de direction droite est appuyée.

+ Testez votre projet de voir si vous pouvez contrôler votre vaisseau spatial avec les touches de direction.

## Sauvegarder votre projet { .save }

# Etapes 2: Coup de tonnerre { .activity }

Donnons au vaisseau spatial la capacité de renvoyer des Coups de tonnerre!

## Liste de contrôle d'activité { .check }

+ Ajoutez le lutin 'Lightning' de la bibliothèque de scratch. Cliquez sur le lutin et tournez la foudre à l'envers.

	![screenshot](images/invaders-lightning.png)

+ Quand le jeu est commencé, la foudre devrait être cachée jusqu'à ce que le vaisseau spatial ne tire ses coups de canon laser.

	```blocks
		quand le drapeau pressé
		cacher
	```

+ Ajoutez le code suivant au vaisseau spatial pour créer un nouveau coup de foudre quand la touche espace est appuyée.


	```blocks
		quand le drapeau pressé
		répéter indéfiniment
			Si <touche [Espace v] pressé?> alors
				créer un clone de [Foudre v]
			end
		end
	```

+ Quand un nouveau clone est créé, il devrait commencer en même endroit que le vaisseau spatial et avancer ensuite sur l'étape jusqu'à ce qu'il touche le bord. Ajoutez le code suivant au lutin de Foudre :

	```blocks
		quand je commence comme un clone
		aller à [Vaisseau spatial v]
		montrer
		répéter jusqu'à <touché [Bord v] ?>
			ajouter (10) à y
		end
		supprimer ce clone
	```

Notez : Nous déplaçons le nouveau clone vers le vaisseau spatial tandis qu'il est toujours caché, le montrant avant cela. Ceci a juste l'air plus agréable.

+ Testez votre foudre, en tapant la touche spatiale.

## Sauvegarder votre projet { .save }

## Défi : Réparation de la foudre {.challenge}
Ce qui arrive si vous gardez la touche spatiale maintenue ? Pouvez vous utiliser le bloc 'attendre'{.blockcontrol} pour réparer ceci ?

## Sauvegarder votre projet { .save }

# Étape 3 : Hippopotames spatiaux { .activity }

Ajoutons des hippopotames volants qui essayent de détruire votre vaisseau spatial.

## Liste de contrôle d'Activité { .check }

+ Créez un nouveau lutin 'Hippo1' dans la bibliothèque de Scratch.

	![screenshot](images/invaders-hippo.png)

+ Faites que sa rotation soit seulement de gauche à droite et ajouter le code suivant pour cacher le lutin quand le jeu commence :

	```blocks
		quand le drapeau pressé
		cacher
	```

+ Créez une nouvelle variable appelée 'Vitesse' {.blockdata}, c'est pour le lutin d'hippopotame seulement.

	![screenshot](images/invaders-var.png)

	Vous saurez si vous l'avez fait correctement car la variable aura le nom du lutin à côté de son nom à elle, comme ceci:

	![screenshot](images/invaders-var-test.png)

+ Le code suivant créera un nouvel hippopotame toutes les X secondes. La scène est un bon endroit pour ce code :

	```blocks
		quand le drapeau pressé
		répéter indéfiniment
			attendre (nombre aléatoires (2) à (4)) secondes
			créer un clone de [Hippo1 v]
		end
	```

+Quand chaque clone d'hippopotame démarre, faites-le ce déplacer sur la scène (à une vitesse aléatoire) jusqu'à ce qu'il soit frappé par la foudre. Ajoutez ce code :

	```blocks
		quand je commence comme un clone
		mettre [vitesse v] à (nombre aléatoire (2) à (4))
		aller à x: (nombre aléatoire (-220) à (220)) y: (150)
		montrer
		répéter jusqu'à <touché [Foudre v] ?>
			s'orienter vers (vitesse)
			tourner à droite (nombre aléatoire  (-10) à (10)) degrés
			rebondir si le bord est atteint
		end
		supprimer ce clone
	```

+ Testez votre code d'hippopotame. Vous devriez voir qu'un nouveau clone d'hippopotame apparaît toutes les quelques secondes, chaque déplacement à sa propre vitesse.

	![screenshot](images/invaders-hippo-test.png)

+ Testez votre canon laser. Si vous frappez un hippopotame, disparaît-il ?

+ Quand un hippopotame touche votre vaisseau spatial, nous devons faire éclater le vaisseau spatial! Pour ceci , assurez vous d'abord que votre vaisseau spatial a 2 costumes appelés 'normal' et 'hit'.

	![screenshot](images/invaders-spaceship-costumes.png)

	Le costume du vaisseau spatial 'hit' peut être fait en important 'sun' l'image de la bibliothèque de Scratch et en utilisant l'outil 'colorier une forme' pour changer sa couleur.

	![screenshot](images/invaders-sun.png)

+ Ajoutez ce code à votre vaisseau spatial pour qu'il change de costume quand il entre en collision avec un hippopotame volant :

	```blocks
		quand le drapeau pressé
		répéter indéfiniment
			basculer sur costume [normal v]
			attendre jusqu'à <touché [Hippo1 v]>?
			basculer sur costume [coup v]
			envoyer à tous [coup v]
			attendre (1) secondes
		end
	```

+ Avez-vous remarqué que vous avez l'émission du message 'hit' dans le code ci-dessus ? Vous pouvez utiliser ce message pour faire disparaître tous les hippopotames quand le vaisseau spatial est touché.

	Ajoutez ce code à votre hippopotame :

	```blocks
		quand je reçois [hit v]
		supprimer ce clone
	```

+ Testez ce code en commençant un nouveau jeu et entrant en collision avec un hippopotame.

	![screenshot](images/invaders-hippo-collide.png)

## Sauvegarder votre projet { .save }

## Défi : Vies et Score {.challenge}
Pouvez vous ajouter 'vies' {.blockdata}, `score` {.blockdata} Ou même a `meilleur score` {.blockdata} À votre jeu ? Le projet 'Catch the Dots' permettra de vous aider.

## Sauvegarder votre projet  { .save }

# Étape 4 : Une chauve-souris !{ .activity }

Faisons une chauve-souris qui jette des oranges à votre vaisseau spatial.

## Liste de contrôle d'activité { .check }

+ Premièrement, faites un nouveau lutin de chauve-souris qui 'se déplacera' {.blockmotion} À travers le sommet de la scène 'indéfiniment'{.blockcontrol}. Rappelez-vous tester votre code.

	![screenshot](images/invaders-bat.png)

+ Si vous regardez les costumes de la chauve-souris, vous verrez qu'il a déjà 2 :

	![screenshot](images/invaders-bat-costume.png)

	Utilisez le bloc costume suivant {.blocklooks} pour faire volet la chauve-souris.

+ Créez un nouvel lutin 'Orange' de la bibliothèque de Scratch

	![screenshot](images/invaders-orange.png)


+ Ajoutez le code à votre chauve-souris, pour qu'il crée une nouvelle orange toutes les quelques secondes.

	```blocks
		quand le drapeau pressé
		répéter indéfiniment
			attendre (nombre aléatoires (5) et (10)) secondes
			créer un clone de [Orange v]
		end
	```

+ Cliquez sur votre lutin 'orange' et ajouter ce code pour faire tomber chaque clone de 'orange' en bas de la scène de la chauve-souris vers le vaisseau spatial :

	```blocks
		quand le drapeau pressé
		cacher

		quand je commence comme un clone
		aller à [chauvesouris1 v]
		montrer
		répéter jusqu'à <touché [Bord v]?
			ajouter (-4) à y
		end
		supprimer ce clone

		quand je reçois [coup v]
		supprimer ce clone
	```

+ Dans votre lutin de vaisseau spatial, vous devrez modifier votre code pour que vous soyez frappés si vous touchez un hippopotame ou une orange :

	```blocks
		attendre jusqu'à < <touché [Hippo1 v]?> ou <touché [Orange v]?>>
	```

+ Testez votre jeu. Qu'est ce qui arrive si vous êtes frappés par une orange tombante ?

## Sauvegarder votre projet { .save }

# Étape 5 : Fin du jeu { .activity }

Ajoutons un message 'Game Over' a la fin du jeu.

## Liste d'activité de contrôle { .check }

+ Si vous n'avez pas déjà, créez une nouvelle variable appelée 'vies' {.blockdata}. Votre vaisseau spatial devrait commencer par 3 vies et perdre une vie quand il entre en collision avec un ennemi. Votre jeu devrait aussi s'arrêter quand vous êtes à court de vies. Si vous avez besoin d'aide, vous pouvez utiliser le projet 'Catch the dots' pour vous aider.

+ Dessinez un nouvel lutin appelé 'Fin du jeu', en utilisant l'outil de texte.

	![screenshot](images/invaders-game-over.png)

+ Sur votre étape, émettez le message ` game over ` {.blockevents} juste avant la fin de jeu.

	```blocks
		envoyer à tous [game over v] et attendre
	```

+ Ajoutez ce code à votre lutin 'Game Over', pour que le message montre à la fin du jeu :

	```blocks
		quand le drapeau pressé
		cacher

		quand je reçois [game over v]
		montrer
	```

	Parce que vous avez utilisé ` envoyer à tous [le jeu sur] et attendre `{.blockevents} sur votre scène, il attendra que le lutin 'Game Over' soit montré avant la fin du jeu.

+ Testez votre jeu. Combien de points vous pouvez marquer ? Pensez aux façons d'améliorer votre jeu si c'est trop facile ou trop dur ?

## Sauvegarder votre projet { .save }

## Défi : Améliorez votre jeu {.challenge}
Quelles améliorations pouvez-vous faire à votre jeu ? Voici quelques idées :

+ Ajouter des paquets de santé que vous pouvez ramasser pour gagner des vies supplémentaires;

![screenshot](images/invaders-aid.png)

+ Ajoutez des roches flottantes que votre vaisseau spatial doit éviter;

![screenshot](images/invaders-rocks.png)

+ Faites apparaître plus d'ennemis quand votre score arrive à 100.

```blocks
	attendre jusqu'à <(score) = [100]>
```

## Sauvegarder votre projet { .save }
