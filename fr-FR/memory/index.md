Défi ---
title: Mémoire
description: Créer un jeu de mémoire, où vous devez mémoriser et répéter une séquence aléatoire de couleurs !
layout: project
notes: "Memory - notes.md"
---

# Introduction { .intro }

Dans ce projet, vous allez créer un jeu de mémoire où vous devez mémoriser et répéter une séquence aléatoire de couleurs !

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/34874510/?autostart=false" frameborder="0"></iframe>
  <img src="images/colour-final.png">
</div>

# Étape 1: Des couleurs aléatoires { .activity }

D'abord, créeons un personnage qui peut se transformer dans une séquence aléatoire de couleurs à mémoriser par le joueur.

## Liste de contrôle { .check }

+ Démarrer avec un nouveau projet Scratch, et supprimer le lutin chat pour commencer d'un projet vide. L'éditeur en ligne se trouve à <a href="http://jumpto.cc/scratch-new" target="_blank">jumpto.cc/scratch-new</a>.

+ Choisir un lutin et un arrière-plan. Votre personnage n'a pas besoin d'être un humain, mais doit pouvoir changer de couleur.

	![capture d'écran](images/colour-sprite.png)

+ Dans votre jeu, vous allez utiliser un chiffre différent pour réprésenter chaque couleur :

	+ 1 = rouge;
	+ 2 = bleu;
	+ 3 = vert;
	+ 4 = jaune.

	Donnez à votre personnage 4 des costumes avec 4 couleurs différentes, un pour chacune des 4 couleurs ci-dessus. Vérifier le bon ordre de vos costumes.

	![capture d'écran](images/colour-costume.png)

+ Pour créer une séquence aléatoire, vous avez besoin de créer une __liste__. Une liste est simplement une variable qui stocke des données _dans un certain ordre_. Créer une nouvelle liste nommée `séquence` {.blockdata}. Seul votre personnage a besoin de voir la liste, donc nous pouvons choisir 'Pour ce lutin uniquement'.

	![capture d'écran](images/colour-list.png)

	Votre liste vide devrait apparaître en haut à gauche de votre scène, ainsi que beaucoup de nouveaux blocs à utiliser avec des listes.

	![capture d'écran](images/colour-list-blocks.png)

+ Ajouter ce code à votre personnage afin d'ajouter un chiffre aléatoire à votre liste (et montrer le bon costume) 5 fois :

	```blocks
		when flag clicked
		delete (all v) of [sequence v]
		repeat (5)
			add (pick random (1) to (4)) to [sequence v]
			switch costume to (item (last v) of [sequence v]
			wait (1) secs
		end
	```

	Vous pouvez remarquer que vous avez aussi vidé la liste avant de commencer.

## Défi : Ajouter du son {.challenge}
Tester votre projet plusieurs fois. Vous pouvez remarquer que parfois le même chiffre est choisi deux fois (ou plus) de suite, rendant la séquence plus difficile à mémoriser. Pouvez-vous faire jouer le son d'un tambour chaque fois que le personnage change de costume ?

Saurez-vous faire changer le son du tambour selon le chiffre aléatoire choisi ? Ceci sera _très_ similaire par rapport à votre code pour changer le costume du personnage.

## Sauvegarder votre projet { .save }

# Étape 2: Répéter la séquence { .activity }

Ajoutons 4 boutons, pour que le joueur répète la séquence mémorisée.

## Liste de contrôle { .check }

+ Ajouter 4 lutins à votre projet, qui vont devenir des boutons. Modifier vos 4 lutins pour avoir un de chaque couleur utilisée.

	![capture d'écran](images/colour-drums.png)

+ Quand on clique sur le tambour rouge, il faut envoyer le message à votre personnage, pour faire savoir que le bouton rouge a été cliqué. Ajouter ce code à votre tambour rouge :

	```blocks
		when this sprite clicked
		broadcast [red v]
	```

+ Quand votre personnage reçoit ce message, il doit vérifier si le chiffre 1 est au début de la liste (ce qui veut dire que rouge est la prochaine couleur dans la séquence). Si ça correspond, c'est que la réponse est bonne. Sinon, c'est "Game over !"

	```blocks
		when I receive [red v]
		if <(item (1 v) of [sequence v])=[1]> then
			delete (1 v) of [sequence v]
		else
			say [Game over!] for (1) secs
			stop [all v]
		end
	```

+ Vous pouvez aussi faire clignoter des lumières une fois la liste vide, pour signifier que vous avez bien deviné la séquence entière correctement. Ajouter ce code à la fin du script `when flag clicked` {.blockevents} de votre personnage :

	```blocks
		wait until < (length of [sequence v]) = [0]>
		broadcast [won v] and wait
	```

+ Cliquez sur votre scène, et ajouter ce code pour jouer __n'importe quel__ son et faire changer la couleur du fond une fois que le joueur a gagné la partie.

	```blocks
		when I receive [won v]
		play sound [drum machine v]
		repeat (50)
			change [color v] effect by (25)
			wait (0.1) secs
		end
		clear graphic effects
	```

## Défi : Créer 4 boutons {.challenge}
Répéter les étapes ci-dessus pour vos boutons de couleur bleu, vert et jaune. Quel code restera pareil et quel code faudrait-il modifier pour chaque bouton ?

Vous pouvez aussi ajouter des sons quand on appuye sur les boutons.

Pensez à tester le code que vous venez d'ajouter ! Vous arrivez à mémoriser une séquence de 5 couleurs ? Est-ce que la séquence change chaque fois ?

## Sauvegarder votre projet { .save }

# Étape 3: De multiples niveaux { .activity .new-page }

Jusqu'alors, le joueur n'a qu'à se souvenir de 5 couleurs. Nous allons améliorer notre jeu en rendant la séquence plus longue.

## Liste de contrôle { .check }

+ Créer une nouvelle variable nommée `score` {.blockdata}.

	![capture d'écran](images/colour-score.png)

+ Ce `score` {.blockdata} sera utilisé pour décider la longueur de la séquence que le joeur doit mémoriser. Alors, pour commencer le score (et la taille de la séquence) sera 3. Ajouter ce bloc de code tout au début du code `when flag clicked` {.blockevents} de votre personnage :

	```blocks
		set [score v] to [3]
	```

+ Au lieu de toujours créer une séquence de 5 couleurs, vous voulez maintenant que le `score` {.blockdata} détermine la longueur de séquence. Changer la boucle `repeat` {.blockcontrol} de votre personnage (pour créer la séquence) en :

	```blocks
		repeat (score)
		end
	```

+ Si la séquence a été correctement identifiée, vous devez ajouter 1 au score, pour augmenter la longueur de la séquence.

	```blocks
		change [score v] by (1)
	```

+ Enfin, vous avez besoin d'ajouter une boucle `forever` {.blockcontrol} autour du code qui génère la séquence, pour créer une nouvelle séquence pour chaque niveau. Le code de votre lutin devrait apparaître comme suit :

	```blocks
		when flag clicked
		set [score v] to [3]
		forever
			delete (all v) of [sequence v]
			repeat (score)
				add (pick random (1) to (4)) to [sequence v]
				switch costume to (item (last v) of [sequence v]
				wait (1) secs
			end
			wait until < (length of [sequence v]) = [0]>
			broadcast [won v] and wait
			change [score v] by (1)
		end
	```

+ Demander à vos amis de tester votre jeu. Pensez à cacher la liste `sequence` {.blockdata} avant de lancer le jeu !

## Sauvegarder votre projet { .save }

# Étape 4: Meilleur score { .activity }

Ajoutons la possibilite d'enregistrer le meilleur score, pour pouvoir jouer contre vos amis.

## Liste de contrôle { .check }

+ Ajuter 2 nouvelles variables à votre projet, nommées `meilleur score` {.blockdata} et `nom` {.blockdata}.

+ Si jamais le jeu s'arrete (en appuyant sur le mauvais bouton), vous aurez besoin de vérifier si le score du joeur est meilleur que le meilleur score actuel. Si c'est le cas, vous devez enregistrer le score comme le nouveau meilleur score, et enregistrer le nom du joeur. Voici à quoi devrait correspondre votre bouton rouge :

	```blocks
		when I receive [red v]
		if <(item (1 v) of [sequence v])=[1]> then
			delete (1 v) of [sequence v]
		else
			say [Game over!] for (1) secs
			if < (score) > (high score) > then
				set [high score v] to (score)
				ask [High score! What is your name?] and wait
				set [name v] to (answer)
			end
			stop [all v]
		end
	```

+ Vous aurez besoin d'ajouter ce nouveau code aux 3 autres boutons aussi ! Avez-vous remarqué que le code 'Game over' est identique pour chacun des 4 boutons ?

	![capture d'écran](images/colour-same.png)

+ Si jamais vous changez une partie du code, par exemple pour ajouter un son ou changer le message 'Game over!', vous devrez le changer 4 fois ! Ça devient embettant, et vous perdez beaucoup de temps.

	A la place, vous pouvez définir vos propres blocs, pour les réutiliser dans votre projet ! Pour le faire, cliquer `more blocks` {.blockmoreblocks}, puis sur 'Créer un bloc'. Nommer ce nouveau bloc 'Game over'.

	![capture d'écran](images/colour-more.png)

+ Ajouter le code du bloc `else` {.blockcontrol} du bouton rouge au nouveau bloc que vous voyez :

	![capture d'écran](images/colour-make-block.png)

+ Désormais vous avez crée une nouvelle _fonction_ qui s'appelle `Game over` {.blockmoreblocks}, que vous pouvez utiliser où vous voulez. Tirez votre nouveau bloc `Game over` {.blockmoreblocks} vers les 4 scripts pour les boutons.

	![capture d'écran](images/colour-use-block.png)

+ Ensuite, ajouter un son quand on clique sur le mauvais bouton. Vous n'avez besoin que d'ajouter ce code _une fois_ dans le bloc `Game over` {.blockmoreblocks} que vous venez de créer, et pas 4 fois à 4 endroits différents !

	![capture d'écran](images/colour-cough.png)

## Défi : Créer d'autres blocs {.challenge}
Est-ce que vous voyez d'autres parties de code qui sont les même pour les 4 boutons ?

![capture d'écran](images/colour-more-blocks.png)

Pouvez-vous créer un autre bloc 'personalisé', à utiliser pour chaque bouton ?

## Sauvegarder votre projet { .save }

## Défi : Un autre costume {.challenge}
Avez-vous remarqué que votre jeu démarre avec votre personnage montrant une des 4 couleurs, et qu'il s'affiche toujours la dernière couleur de la séquence pendant que le joeur répète la séquence ?

Pouvez-vous ajouter un costume blanc à votre lutin, qui sera affiché au début du jeu, ainsi que quand le jouer tente de copier la séquence ?

![capture d'écran](images/colour-white.png)

## Sauvegarder votre projet { .save }

## Défi : Niveau de difficulté {.challenge}
Pouvez-vous laisser votre joeur choisir entre des niveaux 'mode Facile' (utilisant que les tambours rouge et bleu) et 'mode Normal' (qui utilise les 4 tambours) ?

Vour pourriez imaginer même un mode 'Difficile", qui utilise un 5è tambour !

## Sauvegarder votre projet { .save }
