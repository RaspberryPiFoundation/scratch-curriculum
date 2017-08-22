---
title: Attrape les points
description: "Apprends à programmer un jeu où il faut attraper des points!"
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

Commençons par créer un contrôleur qui sera utilisé pour rassembler des points.

## Liste de contrôle d'activité { .check }

+ Commencez un nouveau projet Scratch et supprimez le lutin de chat afin que votre projet soit vide. Vous pouvez trouver l'éditeur de Scratch en ligne à <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Pour ce projet, vous devriez avoir un dossier 'Ressources du projet', contenant l'image du contrôleur que vous pouvez utiliser. Assurez-vous de pouvoir trouver ce dossier et demandez à votre leader de club si vous ne le trouvez pas.

	![screenshot](dots-resources.png)

+ À partir du dossier des Ressources du projet, importez 'controller.png ' comme nouveau lutin. Si vous n'avez pas cette image, vous pouvez le dessiner vous-même! Vous devriez aussi mettre l'arrière-plan noir. Voici le résultat que vous devriez obtenir :

	![screenshot](dots-controller.png)

+ Vous pouvez déplacer votre contrôleur facilement, en le tournant à gauche ou à droite lorsque vous appuyez sur les flèches:

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

+ Même si ce code est fonctionnel, il serait plus intérressant de débuter le jeu à une grande vitesse et de la diminuer au fur et à mesure que le jeu avance. Pour ce faire, supprimez le code que vous avez créé pour votre contrôleur et créez une nouvelle variable appelée ` vitesse contrôleur ` {.blockdata}.

+ Ajoutez ce code à votre contrôleur :

	```blocks
		quand le drapeau pressé
		mettre [vitesse de contrôleur v] à [0]
		répéter indéfiniment
			tourner droite de (Vitesse de contrôleur) degrés
		end
	```

+ Pour le moment, ce code ne déplacera pas le contrôleur puisque la vitesse a été mise à 0! Créez un script séparé dans votre contrôleur, qui augmentera la vitesse lorsque la flèche sera appuyée.

	```blocks
		quand le drapeau
		répéter indéfiniment
			si <touche [Flèche droite v] pressé?> alors
				ajouter [Vitesse de contrôleur v] par (0.2)
			sinon

			end
		end
	```

+ Avez-vous remarqué qu'il y a un écart dans le code ci-dessus ? Si la touche de direction n'est pas appuyée, vous devrez ajouter un code particulier pour ralentir le contrôleur. Cependant, vous devez seulement ralentir le contrôleur jusqu'à ce que la vitesse arrive à 0, autrement il commencera à tourner par en arrière.

	Voici le code que vous devriez ajouter :

	```blocks
	si <(Vitesse de contrôleur) > [0.1]> alors
		ajouter [Vitesse de contrôleur v] par (-0.2)
	end
	```

	Voici comment votre code de contrôleur devrait être :

	![screenshot](dots-right.png)

+ Testez votre projet à nouveau. Si vous maintenez la touche de direction droite, votre contrôleur devrait accélérer. Si vous lâchez la touche, votre contrôleur devrait ralentir progressivement.

## Sauvegarder votre projet { .save }

## Défi : Tourner à gauche{.challenge}
Dupliquez le code pour tourner à droite. Pouvez-vous modifier ce code dupliqué pour que votre contrôleur tourne à gauche lorsque la touche de direction gauche est maintenue ?

Vous devrez changer certains nombres dans le code! ( la variable a une valeur négative.)

## Sauvegarder votre projet { .save }

# Étape 2 : Rassemblement de points { .activity }

Ajoutons des points au jeu, que le joueur rassemblera avec son contrôleur.

## Liste de contrôle d'activité { .check }

+ Créez un nouveau lutin nommé 'rouge'. Ce lutin devrait être un petit point rouge.

	![screenshot](dots-red.png)

+ Ajoutez ce script à votre lutin 'rouge', afin de créer un nouveau point dupliqué toutes les quelques secondes :

	```blocks
		quand le drapeau pressé
		attendre (2) secondes
		répéter indéfiniment
			créer un clone de [Moi même v]
			attendre (nombre aléatoire (5) et (10)) secondes
		end
	```

+ Lorsqu'un clone est créé, vous devez le faire apparaître dans l'un des quatre coins de l'étape. 

	![screenshot](dots-start.png)

	Pour ce faire, créez d'abord une nouvelle liste appelée ` position début `{.blockdata} et cliquez sur ` (+) ` pour ajouter les valeurs '-180' et '180'.

	![screenshot](dots-list.png)

+ Vous pouvez utiliser ces 2 articles de liste afin de choisir un coin aléatoire dans l'étape. Ajoutez ce code au lutin 'pointé', pour que chaque nouveau clone se déplace vers un coin aléatoire et se déplace ensuite lentement vers le contrôleur.

	```blocks
		quand je commence comme un clone
		aller à x: (élément (nombre aléatoire v) de [Positions du début v]) y: (élément (nombre aléatoire v) de [Positions du début v])
		s'orienter vers [contrôleur v]
		montrer
		répéter jusqu'à <touché [contrôleur v]?>
			avancer de (1)
		end
	```

	Le code ci-dessus choisit '-180' ou '180' pour les positions x et le y. Ceci signifie que chaque clone commence dans un coin de l'étape.

+ Testez votre projet. Vous devriez voir que beaucoup de points rouges apparaissent dans chaque coin de l'écran et se déplacent lentement vers le contrôleur.

	![screenshot](dots-red-test.png)

+ Créez 2 nouvelles variables appelées 'vies' {.blockdata} et `score` {.blockdata}.

+ Ajoutez le code à votre étape pour établir les 'vies' {.blockdata} à 3 et le 'score' {.blockdata} à 0 au début du jeu.

+ Vous devez ajouter du code à la fin du code ` quand je commence comme un clone ` {.blockcontrol} de votre point rouge, afin que 1 soit soit ajouté au 'score' du joueur {.blockdata} si la couleur correspond, ou que 1 soit retiré des `vies` {.blockdata} du joueur si les couleurs ne correspondent pas.

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

+ Ajoutez ce code à la fin du script de votre étape pour que le jeu se termine lorsque le joueur perd toutes ses vies :

	```blocks
		attendre jusqu'à <(vies) < [1]>
		stop [tout v]
	```

+ Testez votre jeu pour vous assurer que ces codes fonctionnent.

## Sauvegarder votre projet { .save }

## Défi : Plus de points {.challenge}
Dupliquez votre lutin pointé 'rouge' deux fois et nommez les deux nouveaux lutins 'jaune' et 'bleu'.

![screenshot](dots-more-dots.png)

Éditez ces lutins (incluant leur code), afin que chaque point coloré corresponde à la couleur sur le contrôleur. Souvenez-vous de tester votre projet, en vous assurant que vous gagniez des points et que vous perdiez des vies aux bons moments et que votre jeu n'est pas trop facile ou trop difficile!

![screenshot](dots-all-test.png)

## Sauvegarder votre projet { .save }

# Étape 3 : Augmentation de la difficulté{ .activity .new-page}

Créons un jeu qui devient de plus en plus difficile quand joueur survit plus longtemps, en réduisant l'écart entre l'apparition des points.

## Liste de contrôle d'activité { .check }

+ Créez une nouvelle variable appelée 'écart' {.blockdata}.

+ Sur votre étape, créez un nouveau script qui rend l'écart à un chiffre élevé et qui réduit ensuite lentement le temps d'écart.

	```blocks
		quand le drapeau pressé
		ajouter [Retard v] à (8)
		répéter jusqu'à < (Retard) = (2)>
			attendre (10) secondes
			mettre [Retard v] à (-0.5)
		end
	```

	Remarquez que c'est semblable au fonctionnement d'une minuterie !

+ Finalement, vous pouvez utiliser cette variable 'écart' {.blockdata} dans les scripts de vos points rouges, jaunes et bleues. Enlevez le code qui attend un nombre de secondes aléatoires pour créer des clones et remplacez-le par votre nouvelle variable 'écart' {.blockdata}:

	```blocks
		attendre (retard) secondes
	```

+ Testez votre nouvelle variable 'écart' {.blockdata} et regardez si le retard entre les points réduit lentement. Est-ce que cela fonctionne pour les 3 points colorés ? Pouvez-vous voir la valeur de l' 'écart'{.blockdata} réduire ?

## Sauvegarder votre projet { .save }

## Défi : Points plus rapides {.challenge}
Pouvez-vous améliorer votre jeu en ajoutant une variable 'vitesse' {.blockdata} pour que les points se déplacent lentement au début, et ensuite de plus en plus rapidement? Ceci marchera d'une manière similaire que la variable 'écrat' {.blockdata} utilisée ci-dessus et vous pouvez utiliser ce code pour vous aidez.

## Sauvegarder votre projet { .save }

# Étape 4 : Meilleur score { .activity }

Sauvegardons le meilleur score afin que les joueurs puissent voir comment ils/elles se débrouillent.

## Liste de contrôle d'activité { .check }

+ Créez une nouvelle variable appelée ` meilleur score ` {.blockdata}.

+ Cliquez sur votre étape et créez un nouveau bloc personnalisé appelé ` contrôle meilleur score ` {.blockmoreblocks}.

	![screenshot](dots-custom-1.png)

+ Juste avant la fin du jeu, ajoutez votre nouveau bloc personnalisé.

	![screenshot](dots-custom-2.png)

+ Ajoutez le code à votre bloc personnalisé pour stocker le 'score' actuel{.blockdata} dans 'meilleur score' {.blockdata} `si` {.blockcontrol} c'est le score le plus élevé jusqu'à maintenant :

	```blocks
		definir [vérifier en haut le score]
		si <(score) > (meilleur score)> alors
			ajouter [meilleur score v] à (score)
		end
	```

+ Testez le code que vous avez ajouté. Jouez votre jeu pour vérifier si "meilleur score" {.blockdata} est mis à jour adéquatement.

## Sauvegarder votre projet { .save }

## Défi : Améliorez votre jeu!{.challenge}
Pouvez-vous penser à comment améliorer votre jeu ? Par exemple, vous pourriez créer des points spéciaux qui peuvent :

+ Doubler votre score;
+ Ralentir les points;
+ Cacher tous les autres points sur l'écran!

## Sauvegarder votre projet { .save }
