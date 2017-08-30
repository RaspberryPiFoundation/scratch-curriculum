---
title: La guerre des clones
description: "Apprends à programmer ton propre jeu de bataille spatiale."
layout: project
notes: "Clone Wars - notes.md"
---

# Introduction { .intro }

Dans ce projet, vous apprendrez à créer un jeu dans lequel vous devez sauver la Terre des monstres spatiaux.

<div class="scratch-preview">
 <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/46018140/?autostart=false" frameborder="0"></iframe>
 <img src="images/invaders-final.png">
</div>

# Étape 1 : Fabrication d'un vaisseau spatial { .activity }

Créons un vaisseau spatial qui défendra la Terre!

##liste de contrôle d'activité { .check }

+ Commencez un nouveau projet Scratch et supprimez le lutin de chat pour que votre projet soit vide. Vous pouvez trouver l'éditeur de scratch en ligne à <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Ajoutez le fond 'stars' et le lutin 'Spaceship' à votre projet. Faites rétrécir le vaisseau spatial et déplacez-le près du bas de l'écran.

	![screenshot](images/invaders-sprites.png)

+Ajoutez le code pour déplacer votre vaisseau spatial à gauche lorsque la touche de direction gauche est appuyée. Vous devrez utiliser ces blocs :

	```blocks
		quand le drapeau vert pressé
		répéter indéfiniment
   			si <touche [flèche gauche v] pressée?> alors
      			ajouter (-4) à x
   			fin
		fin
	```

+ Ajoutez le code pour déplacer votre vaisseau spatial à droite quand la touche de direction droite est appuyée.

+ Testez votre projet de voir si vous pouvez contrôler votre vaisseau spatial avec les touches de direction.

## Sauvegarder votre projet { .save }

# Etapes 2: Coup de tonnerre { .activity }

Donnons au vaisseau spatial la capacité de renvoyer des coups de tonnerre!

## Liste de contrôle d'activité { .check }

+ Ajoutez le lutin 'Lightning' en utilisant la bibliothèque de Scratch. Cliquez sur le lutin et tournez la foudre à l'envers.

	![screenshot](images/invaders-lightning.png)

+ Quand le jeu est commencé, la foudre devrait être cachée jusqu'à ce que le vaisseau spatial ne tire ses coups de canon laser.

	```blocks
		quand le drapeau vert pressé
		cacher
	```

+ Ajoutez le code suivant au vaisseau spatial pour créer un nouveau coup de foudre quand la barre d'espace est appuyée.


	```blocks
		quand le drapeau vert pressé
		répéter indéfiniment
			si <touche [espace v] pressée?> alors
      			créer un clone de [Lightning v]
			fin
		fin
	```

+ Quand un nouveau clone est créé, il devrait commencer au même endroit que le vaisseau spatial et avancer ensuite sur l'étape jusqu'à ce qu'il touche le bord. Ajoutez le code suivant au lutin de foudre :

	```blocks
		quand je commence comme un clone
		aller à [Spaceship v]
		montrer
		répéter jusqu’à <[bord v] touché?>
   			ajouter (10) à y
		fin
		supprimer ce clone
	```

À noter : Nous déplaçons le nouveau clone vers le vaisseau spatial lorsqu'il est toujours caché, avant de le montrer ainsi. Cela a l'air plus adéquat.

+ Testez votre foudre, en tapant la touche spatiale.

## Sauvegarder votre projet { .save }

## Défi : Réparation de la foudre {.challenge}
Qu'arrive-t-il si vous gardez la touche spatiale maintenue ? Pouvez vous utiliser le bloc 'attendre'{.blockcontrol} pour réparer cela ?

## Sauvegarder votre projet { .save }

# Étape 3 : Hippopotames spatiaux { .activity }

Ajoutons des hippopotames volants qui essaient de détruire votre vaisseau spatial.

## Liste de contrôle d'Activité { .check }

+ Créez un nouveau lutin 'Hippo1' dans la bibliothèque de Scratch.

	![screenshot](images/invaders-hippo.png)

+ Ajuster sa rotation pour qu'elle soit de gauche à droite seulement et puis ajouter le code suivant pour cacher le lutin lorsque le jeu commencera :

	```blocks
		quand le drapeau vert pressé
		cacher
	```

+ Créez une nouvelle variable appelée 'Vitesse' {.blockdata}, c'est pour le lutin d'hippopotame seulement.

	![screenshot](images/invaders-var.png)

	Vous saurez immédiatement si vous l'avez fait correctement car la variable aura le nom du lutin à côté de son nom, comme ceci:

	![screenshot](images/invaders-var-test.png)

+ Le code suivant créera un nouvel hippopotame a quelques secondes d'intervalle. La scène est un bon endroit pour ce code :

	```blocks
		quand le drapeau vert pressé
		répéter indéfiniment
   			attendre (nombre aléatoire entre (2) et (4)) secondes
   			créer un clone de [Hippo1 v]
		fin
	```

+Lorsque chaque clone d'hippopotame démarrera, déplacez-le autour de la scène (à une vitesse aléatoire) jusqu'à ce qu'il soit frappé par la foudre. Ajoutez ce code au clone d'hippopotame :

	```blocks
		quand je commence comme un clone
		[speed v] prend la valeur (nombre aléatoire entre (2) et (4))
		aller à x:(nombre aléatoire entre (-220) et (220)) y:(150)
		montrer
		répéter jusqu’à <[lightning v] touché?>
   			avancer de (speed)
   			tourner droite de (nombre aléatoire entre (-10) et (10)) degrés
   			rebondir si le bord est atteint
		fin
		supprimer ce clone
	```

+ Testez votre code d'hippopotame. Vous devriez voir qu'un nouveau clone d'hippopotame apparaît à quelques secondes d'intervalle, chacun de déplaçant à sa propre vitesse.

	![screenshot](images/invaders-hippo-test.png)

+ Testez votre canon laser. Si vous frappez un hippopotame, disparaît-t-il ?

+ Lorsqu'un hippopotame touche votre vaisseau spatial, nous devons faire éclater le vaisseau spatial! Pour faire cela, vous devez vous assurer que votre vaisseau spatial a 2 costumes appelés 'normal' et 'hit'.

	![screenshot](images/invaders-spaceship-costumes.png)

	Le costume du vaisseau spatial 'hit' peut être fait en important l'image 'soleil' de la bibliothèque de Scratch et en utilisant l'outil 'colorier une forme' afin de changer sa couleur.

	![screenshot](images/invaders-sun.png)

+ Ajoutez ce code à votre vaisseau spatial pour qu'il change de costume a chaque fois qu'il entre en collision avec un hippopotame volant :

	```blocks
		quand le drapeau vert pressé
		répéter indéfiniment
   			basculer sur costume [normal v]
   			attendre jusqu’à <[Hippo1 v] touché?>
   			basculer sur costume [hit v]
   			envoyer à tous [hit v]
   			attendre (1) secondes
		fin
	```

+ Avez-vous remarqué que vous avez l'émission du message 'hit' dans le code ci-dessus ? Vous pouvez utiliser ce message pour faire disparaître tous les hippopotames lorsque le vaisseau spatial est touché.

	Ajoutez ce code à votre hippopotame :

	```blocks
		quand je reçois [hit v]
		supprimer ce clone
	```

+ Testez ce code en commençant un nouveau jeu et en entrant en collision avec un hippopotame.

	![screenshot](images/invaders-hippo-collide.png)

## Sauvegarder votre projet { .save }

## Défi : Vies et Score {.challenge}
Pouvez-vous ajouter 'vies' {.blockdata}, `score` {.blockdata} ou même un `meilleur score` {.blockdata} à votre jeu ? Le projet 'Catch the Dots' permettra de vous aider.

## Sauvegarder votre projet  { .save }

# Étape 4 : Une chauve-souris !{ .activity }

Créons une chauve-souris qui jette des oranges à votre vaisseau spatial.

## Liste de contrôle d'activité { .check }

+ Premièrement, créer un nouveau lutin de chauve-souris qui 'se déplacera' {.blockmotion} à travers le sommet de la scène 'indéfiniment'{.blockcontrol}. Rappelez-vous de tester votre code.

	![screenshot](images/invaders-bat.png)

+ Si vous regardez les costumes de la chauve-souris, vous verrez qu'il en a déjà 2 :

	![screenshot](images/invaders-bat-costume.png)

	Utilisez le bloc 'costume suivant' {.blocklooks} pour faire bouger les ailes de la chauve-souris lorsqu'elle se déplace.

+ Créez un nouveau lutin 'Orange' de la bibliothèque de Scratch

	![screenshot](images/invaders-orange.png)


+ Ajoutez le code à votre chauve-souris, pour qu'il créé une nouvelle orange à quelques secondes d'intervalle.

	```blocks
		quand le drapeau vert pressé
		répéter indéfiniment
   			attendre (nombre aléatoire entre (5) et (10)) secondes
   			créer un clone de [Orange v]
		fin
	```

+ Cliquez sur votre lutin orange et ajoutez ce code pour faire tomber chaque clone 'orange' en bas de la scène, de la chauve-souris vers le vaisseau spatial :

	```blocks
		quand le drapeau vert pressé
		cacher

		quand je commence comme un clone
		aller à [Bat1 v]
		montrer
		répéter jusqu’à <[bord v] touché?>
   			ajouter (-4) à y
		fin
		supprimer ce clone

		quand je reçois [hit v]
		supprimer ce clone
	```

+ Dans votre lutin de vaisseau spatial, vous devrez modifier votre code pour que vous soyez frappés si vous touchez un hippopotame ou une orange :

	```blocks
		attendre jusqu’à <<[Hippo1 v] touché?> ou <[Orange v] touché?>>
	```

+ Testez votre jeu. Qu'arrive-t-il si vous êtes frappés par une orange?

## Sauvegarder votre projet { .save }

# Étape 5 : Fin du jeu { .activity }

Ajoutons un message 'Game Over' à la fin du jeu.

## Liste d'activité de contrôle { .check }

+ Créez une nouvelle variable appelée 'vies' {.blockdata} si ce n'est pas déjà fait. Votre vaisseau spatial devrait commencer avec 3 vies et devrait perdre une vie lorsqu'il entre en collision avec un ennemi. Votre jeu devrait aussi s'arrêter lorsque vous perdez toutes vos vies. Si vous avez besoin d'aide, vous pouvez utiliser le projet 'Catch the dots' pour vous aider.

+ Dessinez un nouveau lutin appelé 'Fin du jeu', en utilisant l'outil de texte.

	![screenshot](images/invaders-game-over.png)

+ Sur votre étape, émettez le message ` game over ` {.blockevents} juste avant la fin de jeu.

	```blocks
		envoyer à tous [game over v] et attendre
	```

+ Ajoutez ce code à votre lutin 'Game Over' pour que le message puisse apparaître à la fin du jeu :

	```blocks
		quand le drapeau vert pressé
		cacher

		quand je reçois [game over v]
		montrer
	```

	A  cause du bloc `envoyer à tous [le jeu sur] et attendre `{.blockevents} que vous avez utilisé sur votre scène, il attendra que le lutin 'Game Over' soit montré avant de finir la partie.

+ Testez votre jeu. Combien de points pouvez-vous marquer ? Pensez aux façons d'améliorer votre jeu si c'est trop facile ou trop difficile ?

## Sauvegarder votre projet { .save }

## Défi : Améliorez votre jeu {.challenge}
Quelles améliorations pouvez-vous faire à votre jeu ? Voici quelques idées :

+ Ajoutez des paquets de santé que vous pouvez ramasser pour gagner des vies supplémentaires;

![screenshot](images/invaders-aid.png)

+ Ajoutez des roches flottantes que votre vaisseau spatial doit éviter;

![screenshot](images/invaders-rocks.png)

+ Faites apparaître plus d'ennemis lorsque votre score arrive à 100.

```blocks
	attendre jusqu’à <(score) = [100]>
```

## Sauvegarder votre projet { .save }
