Niveau 1

#Felix & Herbert

__Introduction:__
On va jouer au chat et à la souris avec __Félix le chat__ et __Herbert__ la souris. C’est toi qui guides Herbert la souris avec ton pointeur de... souris et tu dois essayer de ne pas te faire attraper par Félix. Plus tu lui échappes longtemps, plus tu marqueras de points. Mais s’il t’attrape, tu perdras alors des points !

##Étape 1 : Félix suit le pointeur de souris

1. Commence un nouveau projet (“Fichier" dans le menu du haut, puis “Nouveau”).
2. Clique sur la scène près du chat et sélectionne l’onglet “Arrière-plan”. Importe l’arrière-plan “hall” dans la catégorie ”Indoors” et supprime l'arrière-plan vide d’origine. 
3. Change le nom du chat et appelle-le “Félix”.
4. Fais en sorte que Félix puisse seulement se retourner horizontalement, de gauche à droite, en cliquant sur ce bouton : Flèche horizontale à 2 pointes.
5. Crée le script suivant :

```scratch

	quand DRAPEAU pressé

	répéter indéfiniment

		pointer vers pointeur de souris

		avancer de 10 pas

		costume suivant

		jouer tambour 62 pour 0.3 temps

	(fin répéter indéfiniment)
```
		
###Teste ton projet
__Clique sur le drapeau vert.__
Est-ce que Félix suit bien le pointeur de ta souris ? 
Est-ce qu’il a l’air de marcher quand il avance ? 
Est-ce qu’il avance à la bonne vitesse ?

Enregistre ton projet

##STEP 2: Félix poursuit Herbert

__Maintenant nous voulons que Félix poursuive Herbert plutôt que le pointeur de souris.__

1. Crée un nouveau personnage en cliquant sur le bouton “Choisir un nouvel objet dans un dossier” et choisis “Mouse1” dans la catégorie “Animals”.
2. Change le nom du personnage pour qu’il s’appelle “Herbert”.
3. Modifie son costume et rends-le plus petit que Félix. Essaie en cliquant 6 fois fois sur le bouton “Réduire”, celui avec 4 flèches pointant vers le centre.
4. Assure-toi que Herbert ne puisse se tourner que de manière horizontale, de gauche à droite. 
5. Créé le script suivant pour Herbert :


```scratch
	
	quand DRAPEAU pressé
	répéter indéfiniment
		Aller à pointeur de souris
		Pointer vers Félix
	(fin répéter indéfiniment)
```

###Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que Herbert bouge avec le pointeur de souris ? Est-ce que Félix poursuit Herbert ?

Enregistre ton projet.

##Étape 3 : Félix parle quand il a attrapé Herbert

__On veut que Félix sache quand il a attrapé Herbert, et qu'il nous le dise.__


1. Change le script de Félix de la manière suivante :

```scratch
	
	quand drapeau pressé
	répéter indéfiniment
		pointer vers pointeur de souris
		avancer de 10 pas
		costume suivant
		jouer tambour 62 pour 0.3 temps
		si Herbert touché 
			dire Je t’ai attrapé ! pendant 1 seconde
		(fin si)
	(fin répéter indéfiniment)
```

###Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que Félix dit quelque chose quand il touche Herbert ?

Enregistre ton projet

##Étape 4 : Herbert se transforme en fantôme quand il se fait attraper

__Modifie le script de Félix pour envoyer un message quand il attrape Herbert:__

1. Modifie le script de Félix pour envoyer un message quand il attrape Herbert:

```scratch
	
	quand drapeau pressé
	répéter indéfiniment
		se diriger vers pointeur de souris
		avancer de 10 pas
		costume suivant
		jouer tambour 62 pour 0.3 temps
		si Herbert touché 
			envoyer à tous Attrapé
			jouer tambour 58 pour 0.2 temps
			attendre 1 seconde
		(fin si)
	(fin répéter indéfiniment)
```
2. Importe le costume “ghost2-a” pour Herbert : va dans l’onglet “Costumes” puis dans la catégorie “Fantasy”.
3. Rends le costume plus petit: clique 6 fois fois sur le bouton “Réduire”.
4. Renomme les costumes d’Herbert de façon à appeler le costume de la souris “vivant” et le costume du fantôme “mort”.
5. Crée le script suivant pour Herbert, pour le transformer en fantôme :

```scratch
	
	quand je reçois Attrapé
	basculer sur le costume mort
	attendre 0.5 secondes
	basculer sur le costume vivant
```
	
###Teste ton projet
__Clique sur le drapeau vert.__

Est ce que Herbert devient un fantôme quand il se fait attraper ? 
Est ce que Félix joue le bon son au bon moment ? 
Est ce que Félix reste immobile assez longtemps pour que Herbert puisse s’échapper ? 

Enregistre ton projet.

##Étape 5 : Compte les Points

__Le score commencera à zéro et il sera augmenté d’un point par seconde. Si Félix attrape Herbert, le score devra diminuer de 100 points.__

1. Crée une variable pour tous les objets, appelée “Score” : choisis l’option “Variables” dans l’onglet “Scripts”, puis clique sur “Nouvelle variable”. 
2. Sélectionne la scène et crée les deux scripts suivants :

```scratch
	
	quand drapeau pressé
	à score attribuer 0
	répéter indéfiniment
		changer score par 1
		attendre 1 seconde
	(fin répéter indéfiniment)
	
	quand je reçois Attrapé
	changer score par -100
```
	
###Teste ton projet
__Clique sur le drapeau vert__

Est-ce que le score augmente d’un point par seconde ? 
Est-ce que le score diminue de 100 points quand Herbert se fait attraper ? 
Que se passe-t-il quand Herbert se fait attraper avant que le score n’atteigne 100 ? 
Est-ce que le score redémarre à zéro quand tu commences une nouvelle partie ?

Enregistre ton projet

__Bravo, tu as fini ! Tu peux maintenant t’amuser !__
N’oublie pas que tu peux partager ton jeu avec tes amis et ta famille en cliquant sur le bouton __Partage__ en haut à droite. 
