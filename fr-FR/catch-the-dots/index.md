---
title: Catch the Dots
description: Apprend à programmer un jeu ou il faut attraper des boules!
layout: project
notes: "Catch the Dots - notes.md"
---

# Introduction { .intro }

Dans ce projet, vous apprendrez à faire un jeu, dans lequel le joueur doit rassembler des points colorés avec la partie correspondante du contrôleur.

<div class="scratch-preview">
 <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/44942820/?autostart=false" frameborder="0"></iframe>
 <img src="images/dots-final.png">
</div>

# Étape 1 : Création d'un contrôleur { .activity }

Commençons en créant un contrôleur, qui sera utilisé pour rassembler des points.

## Liste de contrôle d'Activité { .check }

+ Commencez un nouveau projet scratch et supprimez le lutin de chat pour que votre projet soit vide. Vous pouvez trouver l'éditeur de scratch en ligne à <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Pour ce projet, vous devriez avoir un dossier 'Ressources du projet', contenant l'image du contrôleur que vous pouvez utiliser. Assurez-vous que vous pouvez trouver ce dossier et demander à votre leader de club si vous ne le trouvez pas.

	![screenshot](dots-resources.png)

+ De ce dossier des Ressources du Projet, importez 'controller.png ' comme un nouvel lutin. Si vous n'avez pas cette image vous pouvez le dessiner vous-même! Vous devriez aussi faire le fond noire. Voici comment votre étape devrait être :

	![screenshot](dots-controller.png)

+ Vous pouvez déplacer votre contrôleur vraiment facilement, en le tournant à gauche ou à droit quand les flèches sont appuyées :

	```blocks
		quand le drapeau pressé
		répéter indéfiniment
			si <touche [Flèche gauche v] pressé?> alors
				tourner gauche de (2) degrés
			end
			si <touche [Flèche droite v] pressé?> alors
				tourner droite de (2) degrés
			end
		end
	```
+ Testez votre contrôleur - il devrait tourner à gauche et à droite.

+ Bien que ce code fonctionne, il serait plus interressant de commencer avec une grosse vitesse et de la diminuer au fure et a mesure que le jeux avance. Pour faire ceci, supprimez le code que vous avez créé pour votre contrôleur et créer une nouvelle variable appelée ` vitesse contrôleur ` {.blockdata}.

+ Ajoutez ce code à votre contrôleur :

	```blocks
		quand le drapeau pressé
		mettre [vitesse de contrôleur v] à [0]
		répéter indéfiniment
			tourner droite de (Vitesse de contrôleur) degrés
		end
	```

+ À l'heure actuelle, ce code ne déplacera pas le contrôleur, comme la vitesse a été mise à 0! Créez un scripts séparé dans votre contrôleur qui augmente la vitesse quand la flèche est appuyée.

	```blocks
		quand le drapeau
		répéter indéfiniment
			si <touche [Flèche droite v] pressé?> alors
				ajouter [Vitesse de contrôleur v] par (0.2)
			sinon

			end
		end
	```

+ Avez-vous remarqué qu'il y a un écart dans le code ci-dessus ? Vous devrez ajouter un certain code pour ralentir le contrôleur si la touche de direction n'est pas appuyée. Cependant, vous voulez seulement ralentir le contrôleur jusqu'à ce que la vitesse arrive à 0, autrement il commencera à tourner en arrière.

	Voici le code que vous devriez ajouter :

	```blocks
	si <(Vitesse de contrôleur) > [0.1]> alors
		ajouter [Vitesse de contrôleur v] par (-0.2)
	end
	```

	Voici comment votre code de contrôleur devrait être :

	![screenshot](dots-right.png)

+ Testez votre projet de nouveau. Si vous maintenez la touche de direction droite votre contrôleur devrait s'accélérer. Lâcher la touche et votre contrôleur devrait progressivement ralentir.

## Sauvegarder votre projet { .save }

## Défi : Tourner à gauche{.challenge}
Dupliquez le code pour tourner à droite. Pouvez-vous modifier ce code dupliqué pour que votre contrôleur tourne à gauche quand la touche de direction gauche est maintenue ?

Vous devrez changer certains des nombres dans le code! ( la variable a une valeur négative.)

## Sauvegarder votre projet { .save }

# Étape 2 : Rassemblement de points { .activity }

Ajoutons des points au jeu que le joueur rassemblera avec leur contrôleur.

## Liste de contrôle d'activité { .check }

+ Créez un nouvel lutin appelé 'rouge'. Cet lutin devrait être un petit point rouge.

	![screenshot](dots-red.png)

+ Ajoutez ce scripts à votre lutin 'rouge', pour créer un nouveau point multiplie toutes les quelques secondes :

	```blocks
		quand le drapeau pressé
		attendre (2) secondes
		répéter indéfiniment
			créer un clone de [Moi même v]
			attendre (nombre aléatoire (5) et (10)) secondes
		end
	```

+ Quand un clone est créé, vous voulez qu'il apparaisse dans un des 4 coins de l'étapes.

	![screenshot](dots-start.png)

	Faire ceci , créent d'abord une nouvelle variable de liste appelée ` position début `{.blockdata} et cliquez sur ` (+) ` pour ajouter les valeurs '-180' et '180'

	![screenshot](dots-list.png)

+ Vous pouvez utiliser ces 2 articles de liste pour choisir un coin aléatoire de l'étape. Ajoutez ce code au lutin 'pointé', pour que chaque nouveau clone se déplace vers un coin aléatoire et ensuite se déplace lentement vers le contrôleur.

	```blocks
		quand je commence comme un clone
		aller à x: (élément (nombre aléatoire v) de [Positions du début v]) y: (élément (nombre aléatoire v) de [Positions du début v])
		s'orienter vers [contrôleur v]
		montrer
		répéter jusqu'à <touché [contrôleur v]?>
			avancer de (1)
		end
	```

	Le code ci-dessus choisit '-180' ou '180' pour le x et le y des positions, signifiant que chaque clone commence dans un coin de l'étape.

+ Testez votre projet. Vous devriez voir que beaucoup de points rouges apparaissent dans chaque coin de l'écran et se déplace lentement vers le contrôleur.

	![screenshot](dots-red-test.png)

+ Créez 2 nouvelles variables appelées 'vies' {.blockdata} et `score` {.blockdata}.

+ Ajoutez le code à votre étape pour mettre 'vies' {.blockdata} à 3 et 'score' {.blockdata} à 0 au début du jeu.

+ Vous devez ajouter le code à la fin de votre point rouge ` quand je commence comme un clone ` {.blockcontrol}, pour que 1 soit ajouté au 'score' du joueur {.blockdata} si la couleur correspond, ou prendre une `vies` {.blockdata} si les couleurs ne correspondent pas.

	```blocks
		avancer de  (5)
		Si <couleur [#FF0000] touchée?> alors
			mettre [score v] à (1)
			jouer le son [pop v]
		sinon
			mettre [vies v] à (-1)
			jouer le son [laser1 v]
		end
		supprimer ce clone
	```

+ Ajoutez ce code à la fin du scripts de votre étape, pour que le jeu finisse quand le joueur perd toutes leurs vies :

	```blocks
		attendre jusqu'à <(vies) < [1]>
		stop [tout v]
	```

+ Testez votre jeu pour vous assurer que ces codes fonctionne.

## Sauvegarder votre projet { .save }

## Défi : Plus de points {.challenge}
Dupliquez votre lutin pointé 'rouge' deux fois et nommez les deux nouveaux lutins 'jaunes' et 'bleus'.

![screenshot](dots-more-dots.png)

Éditez ces lutins (incluant leur code), pour que chaque point coloré correspondre à la couleur sur le contrôleur. Rappelez-vous tester votre projet, en vous assurant que vous gagnez des points et perdez des vies aux bons moments et que votre jeu n'est pas trop facile ou trop dur!

![screenshot](dots-all-test.png)

## Sauvegarder votre projet { .save }

# Étape 3 : Augmentation de la difficulté{ .activity .new-page}

Faisons un jeu plus difficiles quand le joueur survit plus longtemps, en réduisant lentement l'écart entre l'apparition de points.

## Liste de contrôle d'Activité { .check }

+ Créez une nouvelle variable appelée 'écart' {.blockdata}.

+ Sur votre étape, créez un nouveau scripts qui met l'écart à un chiffre haut et réduit ensuite lentement le temps d'écart.

	```blocks
		quand le drapeau pressé
		ajouter [Retard v] à (8)
		répéter jusqu'à < (Retard) = (2)>
			attendre (10) secondes
			mettre [Retard v] à (-0.5)
		end
	```

	Remarquez que ceci est semblable au fonctionnement d'un minuteur !

+ Finalement, vous pouvez utiliser cette variable 'écart' {.blockdata} dans les scripts de vos points rouges, jaunes et bleus. Enlevez le code qui attend un nombre aléatoire de secondes entre la création de clones et le remplacer le par votre nouvelle variable 'écart' {.blockdata}:

	```blocks
		attendre (retard) secondes
	```

+ Testez votre nouvelle variable 'écart' {.blockdata} et regardez si le retard entre des points réduit lentement. Marche-t-il tous les 3 points colorés ? Pouvez-vous voir la valeur 'écart'{.blockdata} ce réduire ?

## Sauvegarder votre projet { .save }

## Défi : Déplacement de points plus rapide {.challenge}
Pouvez vous améliorer votre jeu en ajoutant une variable 'vitesse' {.blockdata}, pour que au début les points ce déplacement lentement puis de plus en plus rapide? Ceci marchera d'une façon très semblable à la variable utilisée ci-dessus 'écrat' {.blockdata} vous pouvez utilisez ce code pour vous aidez.

## Sauvegarder votre projet { .save }

# Étape 4 : Meilleur score { .activity }

Mettre un meileur score, pour que les joueurs puissent voir comment ils/elles se débrouillent.

## Liste de contrôle d'activité { .check }

+ Créez une nouvelle variable appelée ` meilleur score ` {.blockdata}.

+ Cliquez sur votre étape et crée un nouveau bloc personnalisé appelé ` contrôle meilleur score ` {.blockmoreblocks}.

	![screenshot](dots-custom-1.png)

+ Juste avant la fin du jeu, ajoutez votre nouveau bloc personnalisé.

	![screenshot](dots-custom-2.png)

+ Ajoutez le code à votre bloc personnalisé pour stocker 'score' actuel{.blockdata} dans 'meilleur score' {.blockdata} `si` {.blockcontrol} c'est le score le plus haut jusqu'ici :

	```blocks
		definir [vérifier en haut le score]
		si <(score) > (meilleur score)> alors
			ajouter [meilleur score v] à (score)
		end
	```

+ Testez le code que vous avez ajouté. Jouez votre jeu pour vérifier si "meilleur score" {.blockdata} est mis à jour correctement.

## Sauvegarder votre projet { .save }

## Défi : Améliorez votre jeu!{.challenge}
Pouvez-vous penser aux façons d'améliorer votre jeu ? Par exemple, vous pourriez créer des points spéciaux qui peuvent :

+ Doubler votre score;
+ Ralentir les points;
+ Cacher tous les points autres sur l'écran!

## Sauvegarder votre projet { .save }
