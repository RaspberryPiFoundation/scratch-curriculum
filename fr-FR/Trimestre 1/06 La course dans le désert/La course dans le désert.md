Niveau 2

#La course dans le désert

__Introduction:__
Ce projet est un jeu qui se joue à 2 joueurs, où un perroquet et un lion font la course l’un contre l’autre dans le désert. Chaque joueur doit appuyer sur une touche du clavier aussi vite que possible pour faire avancer son personnage. Le premier qui atteint le bord de l’écran a gagné !

##Étape 1 : Crée le décor et ajoute les objets

1. Sélectionne la scène et ajoute l’arrière-plan “desert” que tu peux importer depuis le dossier “Nature”.
2. Supprime le chat. Ajoute un nouveau personnage : Choisis l’image du lion que tu trouveras dans le dossier “Animals” et change son nom en “Lion”.
3. Ajoute un autre personnage : Choisis l’image du perroquet que tu trouveras dans le dossier “Animals” et change son nom en “Perroquet”.



##Étape 2 : Fais bouger le lion et le perroquet


Nous voulons que le personnage se déplace lorsque tu appuies sur une touche.


1. D’abord, selectionne le lion et fais-le avancer de 4 pas quand tu appuies sur la touche “L”.

```scratch

	quand l est pressé
	avancer de 4 pas
```

2. Ensuite, sélectionne le perroquet et fais-le avancer de 4 pas quand tu appuies sur la touche “A”.

```scratch

	quand a est pressé
	avancer de 4 pas
```

###Teste ton projet
__Clique sur le drapeau vert.__ 
Est-ce que ton lion se déplace quand tu appuies sur “L” ? Est-ce que ton perroquet se déplace quand tu appuies sur “A” ?


Enregistre ton travail


##Étape 3 : Démarre la course

Nous avons besoin d’un moyen de démarrer la course et de savoir qui du lion ou du perroquet a gagné. __D’abord, créons un bouton de démarrage.__

1. Ajoute un nouvel objet depuis un fichier. Choisis l’objet “button” qui se trouve dans le dossier “Things” et change son nom en “Bouton”.
2. Modifie le costume du bouton : Ajoute-lui le texte “Démarrer” et clique sur OK. Place le bouton au milieu de la scène.
3. Maintenant, ajoute un script qui affiche le bouton Démarrer quand le projet est lancé :

```scratch

	quand DRAPEAU pressé
	montrer
```
4. Maintenant nous voulons que le bouton compte à rebours (c’est à dire à l’envers) à partir de 3, qu’il dise “Partez” puis qu’il disparaisse quand on clique dessus.
Ajoute un autre script comme celui-ci :
:

```scratch

	when StartRace clicked
	dire 3 pendant 1 secondes
	dire 2 pendant 1 secondes
	dire 1 pendant 1 secondes
	dire Partez ! pendant 1 secondes
	cacher
```
###Teste ton projet
__Clique sur le drapeau vert.__

Quand tu cliques sur le bouton “Démarrer”, est-ce qu’il commence le compte à rebours avant de disparaitre ?

Enregistre ton travail.

Nous souhaitons que les coureurs (le lion et le perroquet) ne puissent pas commencer à courir avant le début de la course. Nous devons donc savoir quand la course commence et quand elle est terminée. 
Pour cela nous avons besoin d’une variable :

5. Ajoute une variable pour tous les objets, appelée CourseDémarrée. Décoche la case qui se trouve à coté de son nom pour qu'elle ne soit pas affichée dans la scène.
6. Maintenant fais en sorte que la variable CourseDémarrée soit egale à 0 lorsque le projet est lancé pour la première fois. Change ton script `quand DRAPEAU est pressé` que tu as écris précédemment pour le bouton Démarrer comme ceci :

```scratch

	 quand DRAPEAU pressé
	montrer
	à CourseDémarrée attribuer 0
```
7. Ensuite, mets la variable CourseDémarrée à 1 quand le compte à rebours du bouton Démarrer est terminé.
8. Nous devons maintenant empêcher le lion et le perroquet de partir avant que la variable CourseDémarrée soit égale à 1.
Clique sur le perroquet et __ajoute un bloc de contrôle au script existant__ qui n’autorise le perroquet à avancer que si __CourseDémarrée = 1__.

```scratch

	quand a est pressé
	si CourseDémarrée = 1
		avance de 4 pas
	(fin si)
```
9. N’oublie pas de faire la même chose pour le lion.

###Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que le lion et le perroquet ne peuvent avancer que lorsque le compte à rebours est terminé ?

Nous voulons savoir qui a gagné la course et initialiser son score de nouveau. De cette façon, il est possible de faire la course de nouveau. 

##Étape 4 : Termine la course

1. Ajoute un bloc au script du perroquet qui met a variable CourseDémarrée à 0 quand le perroquet touche le bord de l’écran.

```scratch

	quand a est pressé
	si CourseDémarrée = 1
		avance de 4 pas
		si bord touché?
			à CourseDémarrée attribuer 0
		(fin si)
	(fin si)
```
2. Maintenant, nous voulons que le perroquet nous indique s’il a gagné la course. Enregistre un nouveau son pour le perroquet qui sera joué quand il gagnera. Clique sur __sons__ et enregistre le bruit du perroquet qui gagne la course !
3. Maintenant ajoute un bloc au script du perroquet pour qu’il joue ce son quand il a gagné :

```scratch

	quand a est pressé
	si CourseDémarrée = 1
		avance de 4 pas
		si bord touché?
			à CourseDémarrée attribuer 0
			jouer le son enregistrement1
			dire Le perroquet a gagné ! pendant 3 secondes
		(fin si)
	(fin si)
```
4. Maintenant, répète ces étapes pour le lion.

###Teste ton projet
__Clique sur le drapeau vert.__

Peux-tu cliquer sur le bouton Démarrer et faire avancer les coureurs en appuyant sur les touches “A” et “L” ? Est-ce que les coureurs jouent leur son de la victoire et disent qu’ils ont gagné lorsqu’ils atteingnent le bord en premier ?


Enregistre ton travail.

##Étape 5 : Réinitialise le jeu

Une fois que la course est terminée, nous devons dire à tous les objets de la scène que nous avons gagné et réinitialiser le jeu pour qu’on puisse rejouer.

__Le coureur qui gagne la course doit prévenir qu’il a gagné.__

1. Clique sur le perroquet. Ajoute un bloc au script du perroquet qui diffuse “CourseTerminée” après qu’il ait dit qu’il avait gagné.

```scratch

	quand a est pressé
	si CourseDémarrée = 1
		avance de 4 pas
		si bord touché?
			à CourseDémarrée attribuer 0
			jouer le son enregistrement1
			dire Le perroquet a gagné ! pendant 3 secondes
			envoyer à tous CourseTerminée
		(fin si)
	(fin si)
```
2. Maintenant nous devons ajouter un nouveau script qui écoute la diffusion du message “CourseTerminée” et replace le perroquet sur la ligne de départ. Que se passe-t-il si tu changes la valeur de x ?

```scratch

	quand je reçois CourseTerminée
	mettre x à -175
```
3. Maintenant ajoute le même script sur le lion. Teste différentes valeurs de x pour être sûr que le lion et le perroquet sont bien alignés sur la ligne de départ.
4. Nous voulons aussi mettre le lion et le perroquet à la même position sur la ligne départ lorsque le projet démarre. Pour cela, ajoute un autre script sur chaque coureur qui les déplace lorsqu’on clique sur le drapeau vert.

```scratch

	quand DRAPEAU pressé
	mettre x à -175
```
5. Maintenant clique sur le l’objet et ajoute un script pour qu’il s’affiche quand il reçoit le message CourseTerminée.
###Teste ton projet
__Clique sur le drapeau vert.__


Est-ce que tu peux faire une course avec un ami, l’un courant avec le lion en appuyant sur “L”, l’autre avec le perroquet en appuyant sur “A” ?

Enregistre ton travail.

##Défi : Ajouter un accélérateur

* __Essaie d’ajouter un accélérateur__ que tu ne peux utiliser qu’une fois par course qui fait avancer le perroquet ou le lion de __30 pas en 1 seule fois.__
* __Ajoute un nouveau costume__ avec du feu derrière chaque coureur et fais en sorte qu’il s’affiche quand l’accélérateur est utilisé.
* __Crée un nouveau son__ que le coureur jouera quand il utilisera l’accélérateur.

###Teste ton projet
Enregistre ton travail

__Félicitations ! Tu as terminé ! Maintenant tu peux profiter de ton jeu !__
N’oublie pas que tu peux partager ce jeu avec tous tes amis et toute ta famille en cliquant sur __Partager__ dans la barre de menu.
