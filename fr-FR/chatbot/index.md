---
title: ChatBot
description: Apprend à programmer ton propre robot qui parle!
layout: project
notes: "ChatBot - notes.md"
---

# Introduction { .intro }

Vous allez apprendre à programmer votre propre robot parlant!

<div class="scratch-preview">
 <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/26762091/?autostart=false" frameborder="0"></iframe>
 <img src="images/chatbot-final.png">
</div>

#Étape 1 : Votre robot parlant { .activity }

## Liste de contrôle d'Activité { .check }

+ Avant que vous ne commenciez à faire votre chatbot, vous devez choisir leur personnalité.
	 + Quel sont leur prénoms                                                                                                  
	 + Où ils habitent ?
	 + Est-ce qu'ils sont heureux ? Sérieux ? Drôle ? Timide ? Amical ?

+ Commencez un nouveau projet de scratch et supprimez le lutin de chat pour que votre projet soit vide. Vous pouvez trouver l'éditeur scratch en ligne à <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Choisissez un de ces lutins et ajoutez-le à votre projet :

	![screenshot](images/chatbot-characters.png)

+ Choisissez un fond qui correspond à la personnalité de votre chatbots. Voici un exemple, bien que le vôtre ne doit pas ressembler ici :

	![screenshot](images/chatbot-sprite.png)

## Sauvegarder votre projet { .save }

# Étape 2: un chatbot parlant { .activity }

Maintenant que vous avez un chatbot avec une personnalité, programmons le pour qu'il vous parle.

## Liste de contrôle d'Activité { .check }

+ Le clic sur votre personnage chatbot et ajoute ce code :

	```blocks
		quand ce lutin est cliqué
		demander [Hé! Comment vous appelez-vous ?] et attendre
		dire [Quel charmant nom!] pendant (2) secondes
	```

+ Cliquez sur votre chatbot pour le tester. Après que l'on vous demande votre nom, taper le dans la boîte de dialogue en bas de l'étape.

	![screenshot](images/chatbot-text.png)

+  Votre chatbot répond simplement `Quel nom charmant !` a chaque fois. Vous pouvez personnaliser la réponse de votre chatbot, en vous servant de la réponse de l'utilisateur. Changez le code du chatbots, vomme ceci :

	```blocks
		quand ce lutin est cliqué
		demander [Hey! Comment vous appelez-vous?] et attendre
		dire <regroupe [salut] (Réponse)> pendant (2) secondes
	```

	Pour créer le dernier bloc, vous devrez d'abord ajouter un bloc vert `regroupe` {.blockoperators} et traînée celui-ci sur à le bloc `dire` {.blocklooks}.

	![screenshot](images/chatbot-join.png)

	Vous pouvez alors changer le texte `bonjour` et dire `salut`, et traînée le bloc bleu clair `réponse` {.blocksensing} ( dans la section 'capteur') sur le texte `Monde`.

	![screenshot](images/chatbot-answer.png)

+ Testez ce nouveau programme. Marche-t-il comme vous le voulez ? Pouvez-vous réparer les problèmes que vous pouvez voir ? (PS: vous pouvez essayer d'ajouter un espace quelque part !)

+ Peut être que vous voulez stocker le nom de l'utilisateur dans une variable, pour que vous puissiez l'utiliser de nouveau plus tard. Créez une nouvelle variable appelée `nom` {.blockdata}. Si vous avez oublié comment faire ceci, le projet 'Ballons' vous aidera.

+ Les informations que vous avez entrés sont déjà stockées dans une variable spéciale appelée `réponse` {.blocksensing}. Allez dans le groupe de blocs 'capteur' et cliquez sur le bloc de réponse pour qu'une case cochante apparaissent. La valeur actuelle dans `réponse` {.blocksensing} devrait alors s'afficher en haut à gauche de l'étape.

+ Une fois que vous avez créé votre nouvelle variable, assurez-vous que le code de votre chatbot ressemble a ceci :

	```blocks
		quand ce lutin est cliqué
		demander [Hey! Comment t'appelles-tu?
		mettre [nom v] à (réponse)
		dire <regroupe [Sava] (nom)> pendant (2) secondes
	```

+ Si vous testez votre programme de nouveau, vous remarquerez que la réponse est stockée dans le `nom` {.blockdata} On montre la variable en haut à gauche de l'étape. La variable `nom` {.blockdata} devrait maintenant contenir la même valeur que la variable `réponse` {.blocksensing}.

	![screenshot](images/chatbot-variable.png)

	Si vous ne préféreriez pas voir les variables sur votre étape, vous pouvez decoché à côté des noms de variables dans les onglets pour les cacher.

## Sauvegarder votre projet{ .save }

## Défi : Plus de questions { .challenge }

Programmez votre chatbot pour poser une autre question. Pouvez-vous stocker la réponse dans une variable ?

![screenshot](images/chatbot-question.png)

## Sauvegarder votre projet { .save }

# Étape 3 : Prendre des décisions { .activity }

Vous pouvez programmer votre chatbot pour décider que faire, en fonction des réponses de l'utilisateur.

## Liste de contrôle d'activité { .check }

+ Faisons poser une question à votre chatbot et l'utilisateur qui répond `oui` ou `non`. Voici un exemple, mais vous pouvez changer la question si vous voulez:

	```blocks
		quaand ce lutin est cliqué
		demander [Hey! Comment t'appelles-tu?] et attendre
		mettre [nom v] à (réponse)
		dire <regroupe [Hi ] (nom)> pendant (2) secondes
		demander <regroupe [Tu vas bien?] (nom)> et attendre
		si ((réponse)=[oui]) alors
			dire [ C'est super ] pendant (2) secondes
		end
	```

+ Pour tester ce programme correctement, vous devrez le tester deux fois - une fois en tapant "non" et une fois en tapant 'oui'. Vous devriez seulement obtenir une réponse de votre chatbot `if` {.blockcontrol} vous répondez `oui`.

+ Les ennuis avec votre chatbot sont qu'il ne donne pas de réponse si l'utilisateur répond `non`. Vous pouvez réparer ceci, en changeant le block `if` {.blockcontrol} par un block `if/else` {.blockcontrol}.
	```blocks
		quand ce lutin est cliqué
		demander [Hey! Comment vous appelez-vous ?] et attendre
		mettre [nom v] à (réponse)
		dire <regroupe [Hi ] (nom)> pendant (2) secondes
		demander <regroupe [Vous allez bien? ] (nom)> et attendre
		si ((réponse)=[oui]) alors
			dire [C'est super !] pendant (2) secondes
		sinon
			dire [Oh non!] pendant (2) secondes
		end
	```

+ Si vous testez votre code, vous verrez maintenant que vous obtenez une réponse quand vous répondez 'oui' ou 'non'. Votre chatbot devrait répondre 'c'est super !' ` quand vous répondez 'oui', mais répondrez avec 'Oh non!' quand vous tapez quoi que ce soit d'autre que 'oui' (`sinon` {.blockcontrol} signifie ' sinon ').
	![screenshot](images/chatbot-else.png)

+ Vous pouvez mettre n'importe quel code à l'intérieur d'un block `si` {.blockcontrol} ou `sinon` {.blockcontrol}, pas seulement faire parler votre chatbot. Par exemple, vous pouvez changer le costume du chatbot pour correspondre à la réponse.

	Si vous regardez les costumes de votre chatbot, vous pouvez voir qu'il y en a plusieur. (Sinon, vous pouvez toujours en ajouter vous-même!)

	![screenshot](images/chatbot-costumes.png)

	Vous pouvez utiliser ces costumes dans le cadre de la réponse de votre chatbot, en utilisant ce code :

	```blocks
		quand ce lutin est cliqué
		basculer sur costume [nano-a v]
		demander [Hey! Comment vous appelez-vous ?] et attendre
		mettre [nom v] à (réponse)
		dire <regroupe [Sava ] (nom)> pendant (2) secondes
		demander <regroupe [Vous allez bien?] (nom)> et attendre
		si ((réponse)=[youi]) alors
			basculer sur costume [nano-c v]
			dire [C'est super pour entendre!] pendant (2) secondes
		sinon
			basculer sur costume [nano-d v]
			dire [Oh non!] pendant (2) secondes
		end
	```

	![screenshot](images/chatbot-face.png)

## Sauvegader votre projet { .save }

## Défi : Plus de décisions { .challenge }

Programmez votre chatbot pour poser une autre question - quelque chose avec un 'oui' ou 'aucune' réponse. Pouvez-vous faire répondre votre chatbot à la question?

![screenshot](images/chatbot-joke.png)

## Sauvegader votre projet { .save }

# Étape 4 : Changement d'emplacement { .activity }

Vous pouvez aussi programmer votre chatbot pour changer son emplacement.

## Liste de contrôle d'Activité { .check }

+ Ajoutez un autre fond à votre étape, par exemple le fond 'lune'.

	![screenshot](images/chatbot-moon.png)

+ Vous pouvez maintenant programmer votre chatbot pour changer l'emplacement, en ajoutant ce code à votre chatbot :

	```blocks
		 demander [je vais à la lune. Voulez-vous venir avec moi ?] et attendre
		si ((réponse) = [oui]) alors
			basculer sur l'arrière-plan [lune v]
		end
	```


	![screenshot](images/chatbot-outside.png)

+ Testez votre programme et répondez 'oui' si vous voulez aller sur la lune. Vous devriez voir que l'emplacement du chatbot a changé.

	![screenshot](images/chatbot-backdrop.png)

+ Votre chatbot change-t-il l'emplacement si vous ne tapez pas ? Qu'en est-il de si vous tapez ` je ne suis pas sûr ` ?

## Sauvegarder votre projet { .save }

##Défi : Faites votre propre chatbot {.challenge}
Utilisation ce que vous avez appris pour finir de créer votre chatbot interactif. Voici quelques idées :

![screenshot](images/chatbot-ideas.png)

Une fois que vous avez fini votre chatbot, dites à vos amis d'avoir une conversation avec lui! Ils aiment votre caractère ? Ont-ils découvert des problèmes ?

## Sauvegader votre projet { .save }
