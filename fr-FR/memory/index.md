---
title: Mémoire
description: Crées un jeu de mémoire où tu devras mémoriser et répéter une séquence aléatoire de couleurs!
layout: project
notes: "Memory - notes.md"
---

# Introduction { .intro }

Dans ce projet, vous allez créer un jeu de mémoire où vous devez mémoriser et répéter une séquence aléatoire de couleurs!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/172305882/?autostart=false" frameborder="0"></iframe>
  <img src="images/colour-final.png">
</div>

# Étape 1: Des couleurs aléatoires { .activity }

Créons un personnage qui peut se transformer dans une séquence aléatoire de couleurs à mémoriser par le joueur.

## Liste de contrôle d'activité { .check }

+ Démarrez avec un nouveau projet Scratch et supprimez le lutin de chat pour commencer un projet vide. L'éditeur scratch se trouve en ligne à <a href="http://jumpto.cc/scratch-new" target="_blank">jumpto.cc/scratch-new</a>.

+ Choisissez un lutin et un arrière-plan. Votre personnage n'a pas besoin d'être un humain, mais doit pouvoir changer de couleur.

	![capture d'écran](images/colour-sprite.png)

+ Dans votre jeu, vous allez utiliser un chiffre différent pour représenter chaque couleur :

	+ 1 = rouge;
	+ 2 = bleu;
	+ 3 = vert;
	+ 4 = jaune.

	Donnez à votre personnage 4 costumes de couleurs différentes, un pour chacune des 4 couleurs ci-dessus. Vérifiez le bon ordre de vos costumes.

	![capture d'écran](images/colour-costume.png)

+ Pour créer une séquence aléatoire, vous avez besoin de créer une __liste__. Une liste est simplement une variable qui stocke des données _dans un certain ordre_. Créez une nouvelle liste nommée `séquence` {.blockdata}. Seul votre personnage a besoin de voir la liste, donc nous pouvons choisir 'Pour ce lutin uniquement'.

	![capture d'écran](images/colour-list.png)

	Votre liste vide devrait apparaître en haut à gauche de votre scène, ainsi que plusieurs nouveaux blocs à utiliser avec des listes.

	![capture d'écran](images/colour-list-blocks.png)

+ Ajoutez ce code à votre personnage afin d'ajouter un chiffre aléatoire à votre liste (et montrer le bon costume) 5 fois :

	```blocks
    quand le drapeau vert pressé
    supprimer l'élément (tout v) de la liste [séquence v]
    répéter (5) fois
       ajouter (nombre aléatoire entre (1) et (4)) à [séquence v]
       basculer sur costume (élément (last v) de [séquence v])
       attendre (1) secondes
    fin
	```

	Vous pouvez remarquer que vous avez aussi vidé la liste avant de commencer.

## Défi : Ajouter du son {.challenge}
Testez votre projet plusieurs fois. Vous pouvez parfois remarquer que le même chiffre est choisi deux fois (ou plus) de suite, rendant la séquence plus difficile à mémoriser. Pouvez-vous faire jouer le son d'un tambour chaque fois que le personnage change de costume?

Pouvez-vous changer le son du tambour selon le chiffre aléatoire choisi? Ceci sera _très_ similaire par rapport à votre code pour changer le costume du personnage.

## Sauvegarder votre projet { .save }

# Étape 2: Répéter la séquence { .activity }

Ajoutons 4 boutons pour que le joueur puisse répéter la séquence mémorisée.

## Liste de contrôle d'activité { .check }

+ Ajoutez 4 lutins qui vont devenir des boutons. Modifiez vos 4 lutins pour qu'il y en ait un de chaque couleur.

	![capture d'écran](images/colour-drums.png)

+ Quand on clique sur le tambour rouge, il faut envoyer le message à votre personnage pour faire savoir que le bouton rouge a été cliqué. Ajoutez ce code à votre tambour rouge :

	```blocks
    quand ce lutin est cliqué
    envoyer à tous [rouge v]
	```

+ Quand votre personnage reçoit ce message, il doit vérifier si le chiffre 1 est au début de la liste (ce qui veut dire que rouge est la prochaine couleur dans la séquence). Si tout correspond, c'est que la réponse est bonne. Sinon, c'est "Partie terminée!"

	```blocks
    quand je reçois [rouge v]
    si <(élément (1 v) de [séquence v]) = [1]> alors
       supprimer l'élément (1 v) de la liste [séquence v]
    sinon
       dire [Partie terminée!] pendant (1) secondes
       stop [tout v]
    fin
	```

+ Vous pouvez aussi faire clignoter des lumières lorsque la liste sera vide, ce qui signifie que vous avez bien deviné la séquence entière. Ajoutez ce code à la fin du texte `quand ⚑ cliqué` {.blockevents} de votre personnage :

	```blocks
    attendre jusqu’à <(longueur de [séquence v]) = [0]>
    envoyer à tous [gagné v] et attendre
	```

+ Cliquez sur votre scène et ajoutez ce code pour jouer __n'importe quel__ son et faire changer la couleur du fond lorsque le joueur a gagné la partie.

	```blocks
    quand je reçois [gagné v]
    jouer le son [drum machine v]
    répéter (50) fois
       ajouter à l'effet [couleur v] (25)
       attendre (0.1) secondes
    fin
    annuler les effets graphiques
	```

## Défi : Créer 4 boutons {.challenge}
Répétez les étapes ci-dessus pour vos boutons bleus, verts et jaunes. Quel code restera pareil et quel code faudrait-il modifier pour chaque bouton?

Vous pouvez aussi ajouter des sons lorsque vous appuyez sur les boutons.

N'oubliez pas de tester le code que vous venez d'ajouter! Pouvez-vous mémoriser une séquence de 5 couleurs? Est-ce que la séquence change à chaque fois?

## Sauvegarder votre projet { .save }

# Étape 3: De multiples niveaux { .activity .new-page }

Jusqu'à maintenant, le joueur n'a qu'à se souvenir de 5 couleurs. Nous allons donc améliorer notre jeu en rendant la séquence plus longue.

## Liste de contrôle d'activité { .check }

+ Créez une nouvelle variable nommée `pointage` {.blockdata}.

	![capture d'écran](images/colour-score.png)

+ Ce `pointage` {.blockdata} sera utilisé pour déterminer la longueur de la séquence que le joueur doit mémoriser. Pour commencer, le pointage (et la taille de la séquence) sera de 3. Ajoutez ce bloc de code au début du code `quand ⚑ cliqué` {.blockevents} de votre personnage :

	```blocks
		[pointage v] prend la valeur [3]
	```

+ Au lieu de toujours créer une séquence de 5 couleurs, vous voulez avoir un `pointage` qui {.blockdata} détermine la longueur de la séquence. Changez la boucle `répéter` {.blockcontrol} de votre personnage (pour créer la séquence) en :

	```blocks
    répéter (pointage) fois
    fin
	```

+ Si la séquence a été identifiée correctement, vous devez ajouter 1 au pointage afin d'augmenter la longueur de la séquence.

	```blocks
		ajouter à [pointage v] (1)
	```

+ Enfin, vous aurez besoin d'ajouter une boucle `répéter indéfiniment` {.blockcontrol} autour du code qui génère la séquence afin de créer une nouvelle séquence pour chaque niveau. Le code de votre lutin devrait apparaître comme suit :

	```blocks
    quand le drapeau vert pressé
    [pointage v] prend la valeur [3]
    répéter indéfiniment
       supprimer l'élément (tout v) de la liste [séquence v]
       répéter (pointage) fois
          ajouter (nombre aléatoire entre (1) et (4)) à [séquence v]
          basculer sur costume (élément (dernier v) de [séquence v])
          attendre (1) secondes
       fin
       attendre jusqu’à <(longueur de [séquence v]) = [0]>
       envoyer à tous [gagné v] et attendre
       ajouter à [pointage v] (1)
    fin
	```

+ Demandez à vos amis de tester votre jeu. Pensez à cacher la liste `séquence` {.blockdata} avant de lancer le jeu!

## Sauvegarder votre projet { .save }

# Étape 4: Meilleur pointage { .activity }

Ajoutons la possibilité d'enregistrer le meilleur pointage afin de pouvoir jouer contre vos amis.

## Liste de contrôle d'activité { .check }

+ Ajoutez 2 nouvelles variables à votre projet nommées `meilleur pointage` {.blockdata} et `meilleur joueur` {.blockdata}.

+ Si jamais le jeu s'arrête (en appuyant sur le mauvais bouton), vous aurez besoin de vérifier si le pointage du joueur est plus grand que le meilleur pointage actuel. Si c'est le cas, vous devez enregistrer le pointage comme le nouveau meilleur pointage et enregistrer le nom du joueur. Voici à quoi devrait correspondre votre bouton rouge :

	```blocks
    quand je reçois [rouge v]
    si <(élément (1 v) de [séquence v]) = [1]> alors
       supprimer l'élément (1 v) de la liste [séquence v]
    sinon
       dire [Partie terminée!] pendant (1) secondes
       si <(pointage) > (meilleur pointage)> alors
          [meilleur pointage v] prend la valeur (pointage)
          demander [Meilleur pointage! Quel est ton nom?] et attendre
          [meilleur joueur v] prend la valeur (réponse)
       fin
       stop [tout v]
    fin
	```

+ Vous aurez besoin d'ajouter ce nouveau code aux 3 autres boutons aussi! Avez-vous remarqué que le code 'Partie terminée' est identique pour chacun des 4 boutons?

	![capture d'écran](images/colour-same.png)

+ Si jamais vous changez une partie du code, comme pour ajouter un son ou changer le message 'Partie terminée!', vous allez devoir le changer 4 fois! Ça devient embêtant et vous perdez beaucoup de temps.

	À la place, vous pouvez définir vos propres blocs afin de les réutiliser dans votre projet! Pour faire cela, cliquez `Ajouter blocs` {.blockmoreblocks} et puis sur 'Créer un bloc'. Nommez ce nouveau bloc 'Partie terminée'.

	![capture d'écran](images/colour-more.png)

+ Ajoutez le code du bloc `sinon` {.blockcontrol} du bouton rouge au nouveau bloc que vous voyez :

	![capture d'écran](images/colour-make-block.png)

+ Vous avez maintenant créé une nouvelle _fonction_ appelée `Partie terminée` {.blockmoreblocks} que vous pouvez utiliser où vous voulez. Glissez votre nouveau bloc `Partie terminée` {.blockmoreblocks} vers les 4 scripts pour les boutons.

	![capture d'écran](images/colour-use-block.png)

+ Ensuite, ajoutez un son lorsque vous cliquez sur le mauvais bouton. Vous avez juste à ajouter ce code _une fois_ dans le bloc `Partie terminée` {.blockmoreblocks} que vous venez de créer, et non à 4 occasions différentes!

	![capture d'écran](images/colour-cough.png)

## Défi : Créer d'autres blocs {.challenge}
Est-ce que vous voyez d'autres séquences de code qui se répètent pour les 4 boutons?

## Sauvegarder votre projet { .save }

## Défi : Un autre costume

![capture d'écran](images/colour-more-blocks.png)

Pouvez-vous créer un autre bloc 'personnalisé', à utiliser pour chaque bouton?

## Sauvegarder votre projet { .save }

## Défi : Un autre costume {.challenge}

Avez-vous remarqué que votre jeu démarre avec votre personnage montrant une des 4 couleurs et qu'il affiche toujours la dernière couleur de la séquence pendant que le joueur répète la séquence?

Pouvez-vous ajouter un costume blanc qui sera affiché sur votre lutin au début de la partie, ainsi que lorsque le joueur tente de copier la séquence?

![capture d'écran](images/colour-white.png)

## Sauvegarder votre projet { .save }

## Défi : Niveau de difficulté {.challenge}
Pouvez-vous laisser votre joueur choisir entre des niveaux 'mode Facile' (utilisant juste les tambours rouges et bleus) et 'mode Normal' (qui utilise les 4 tambours)?

Vous pourriez même imaginer un mode 'Difficile" qui utilise un 5ième tambour!

## Sauvegarder votre projet { .save }
