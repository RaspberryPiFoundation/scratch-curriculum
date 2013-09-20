Niveau 1

#Feux d'artifices

__Introduction:__
Dans ce projet, on va faire un feu d’artifice dans le ciel d’une ville.

##Étape 1 : Crée une fusée qui vole dans la direction de la souris

__Importons les différentes images pour le jeu__

1. Commence un nouveau projet Scratch. Supprime le chat en cliquant dessus avec le bouton droit de la souris et choisis la commande “Supprimer”.
2. Remplace la scène et choisis l’arrière plan ‘city-with-water’ qui se trouve dans le dossier “Outdoors”.
3. Clique sur le bouton __Choisir un nouvel objet dans un dossier__ et ajoute l’objet “Fusée” au projet (utilise le costume “Rocket.png” qui se trouve dans le dossier “Resources”).
to the project (use the Resources/Rocket.png costume).
4. Fais disparaître la fusée quand le drapeau vert est pressé.

Maintenant, nous voulons que la fusée s’envole vers le pointeur de la souris quand la barre espace est appuyée. 

5. Sélectionne la fusée et ajoute le bloc de contrôle “quand espace est pressé” au dessous duquel tu vas faire appraître la fusée et la faire voler jusqu’à la souris.

```scratch

	quand DRAPEAU pressé

	cacher

	
	quand espace est pressé
	montrer
	glisser en 1 secondes à x: souris x y: souris y
```
		
###Teste ton projet
__Clique sur le drapeau vert, place la souris sur la scène et appuie sur la touche espace.__

Est-ce que la fusée apparaît et se déplace vers la souris ? 
Que se passe-t-il si tu déplaces la souris et que tu appuies de nouveau sur la touche espace ?

6. Normalement, les feux d’artifices ne volent pas à l’horizontale ! 
Assurons-nous que les fusées glissent depuis le coté inférieur de la scène pour atteindre la souris. Avant de faire apparaître la fusée, utilise le bloc "aller à x y" de sorte que la fusée se lance toujours du dessous de la scène mais à la verticale de la souris

```scratch

	quand DRAPEAU pressé

	cacher

	
	quand espace est pressé
	aller à x: souris x y: -200
	montrer
	glisser en 1 secondes à x: souris x y: souris y
```

###Teste ton projet
__Clique sur le drapeau vert, place la souris sur la scène et appuie sur la touche espace.__ 
Est-ce que la fusée vole en direction de la souris à partir du bas de la scène ? Que se passe-t-il si tu changes l’emplacement de la souris et que tu appuies de nouveau sur la barre espace ? 


7. Finalement, modifions cette tâche pour utiliser le clic de la souris au lieu de la barre espace.
Pour cela, nous pouvons envelopper notre script par le bloc __répéter indéfiniment si souris pressé__. Puis, change le bloc __Quand touche espace préssé__ par __Quand drapeau préssé__
Assure-toi que la fusée soit cachée quand le programme commence.

```scratch

	quand DRAPEAU pressé
	cacher 
	répéter indéfiniment si souris pressée
		aller à x: souris x y: -200
		montrer
		glisser en 1 secondes à x: souris x y: souris y
	(fin répéter indéfiniment)
```
###Teste ton projet
__Clique sur le drapeau vert, puis clique n’importe où sur la scène. Répète cette action plusieurs fois dans différents endroits.__ 

###Essaie d’aller plus loin :
1. Essaie de modifier la trajectoire de la fusée en un arc de cercle avant d’atteindre la souris.
2. Essaie de rendre quelques fusées plus lentes ou plus rapides que d’autres.

Enregistre ton travail.

##Étape 2 : Fais exploser la fusée

1. 1.	La première étape pour faire exploser la fusée consiste à jouer le son “bang” avant son lancement (le son se trouve dans le dossier “Resources”). Ensuite, la fusée sera masquée une fois qu’elle touchera la souris. Pour importer un son, clique sur l’onglet “sons” puis sur le bouton “Importer”


```scratch

	quand DRAPEAU pressé
	cacher
	répéter indéfiniment si souris préssée
		aller à x: souris x y: -200
		jouer le son bang
		montrer
		glisser en 1 secondes à x: souris x y: souris y
		cacher
	(fin répéter indéfiniment)
```
2. Ensuite, programme la fusée pour qu’elle diffuse un nouveau message quand elle explose :

```scratch

	quand DRAPEAU pressé
	cacher
	répéter indéfiniment si souris préssée
		aller à x: souris x y: -200
		jouer le son bang
		montrer
		glisser en 1 secondes à x: souris x y: souris y
		cacher
		envoyer à tous explosion
	(fin répéter indéfiniment)
```
###Teste ton projet
__Clique sur le drapeau vert.__ 
Assure-toi que la fusée joue un son et disparaît quand elle atteint la souris.

3. Importe l’objet “firework1.png” qui se trouve dans le dossier “Ressources”.
4. Avant que le message “explosion” soit reçu, l’objet doit être caché, puis quand le message est reçu, il se met à la position de la fusée en utilisant le bloc “aller à x: y:”. Il apparaît pour une seconde puis disparaît à nouveau. Sélectionne ce nouvel objet et ajoute-lui ce script :


```scratch

	quand je reçois explosion

	cacher

	aller à x: position x de Fusée y: position y de Fusée

	montrer

	attendre 1 secondes

	cacher
```
###Teste ton projet
__Lance une fusée.__ 
Est-ce qu’elle est bien remplacée avec l’image de l’explosion quand elle explose ? 
Que se passe-t-il si tu maintiens le bouton de la souris enfoncé et que tu la bouges en même temps ? (Ne t’en fais pas, nous allons arranger ça)

Enregistre ton travail.

##Étape 3 : Rends chaque explosion unique

1. Maintenant, nous pouvons rendre chaque explosion unique en effectuant des modifications sur le bloc couleur. Ce bloc va prendre une couleur aléatoire entre 1 et 200 avant d’apparaître

```scratch

	quand je reçois explosion

	cacher

	mettre l’effet couleur à nombre aléatoire entre 1 et 200

	aller à x: position x de Fusée y: position y de Fusée

	montrer

	attendre 1 secondes

	cacher
```

###Teste ton projet
__Clique sur le drapeau vert.__ 

Est-ce que chaque explosion est d’une couleur différente ?

2. Ajoutons d’autres possibilités d’explosions. 
Nous allons importer les costumes “firework2.png” et “firework3.png” du dossier “Ressources”. Bascule entre les différents costumes de chaque fusées avant de les faire apparaître.

###Teste ton projet
__Clique sur le drapeau vert__ 

Est ce que chaque fusée a une image d’explosion différente? 

3. Au final, on va agrandir l’explosion doucement à la place de la faire apparaître d’un coup. Au lieu d’attendre une seconde, nous allons fixer la taille de l’objet “Explosion” à 5% avant de le faire apparaître. Après son apparition, on va augmenter la taille de 2% 50 fois en utilisant le bloc répéter.


```scratch

	quand je reçois explosion

	cacher

	mettre l’effet couleur à nombre aléatoire entre 1 et 200

	aller à x: position x de Fusée y: position y de Fusée

	mettre la taille à 5%

	montrer
	
	répéter 50 fois
		modifier la taille par 2
	(fin répéter)

	cacher
```
###Teste ton projet
__Clique sur le drapeau vert.__ 

Est-ce que l’explosion commence à partir du centre de la fusée puis s'agrandit doucement?

###Essaie d’aller plus loin :
Pourquoi ne pas rendre chaque explosion plus unique en changeant la taille et la vitesse de l’explosion ?

Enregistre ton travail

##Étape 4 : Corrige bug de la diffusion du message
Rappelle-toi qu’on a un bug quand on maintient le bouton de la souris enfoncé ?Ceci arrive parce que quand la fusée diffuse le message d’explosion elle va immédiatement recommencer boucle “si” et diffuser un autre message d’explosion avant même que la dernière fusée finisse l’explosion.


1. Pour corriger cela, Nous pouvons remplacer le bloc “envoyer à tous” par le bloc “envoyer à tous et attendre”. De cette manière, la boucle “répéter” ne va pas recommencer avant que l’explosion ne soit terminée.

```scratch

	quand DRAPEAU pressé
	cacher
	répéter indéfiniment si souris préssée?
		aller à x: souris x y: -200
		jouer le son bang
		montrer
		glisser en 1 secondes à x: souris x y: souris y
		cacher
		envoyer à tous explosion et attendre
	(fin répéter indéfiniment)
```
###Teste ton projet
__Clique sur le drapeau vert. Garde le bouton de la souris enfoncé et déplace la souris autour de la scène.__ 

Est ce que l’explosion apparaît dans le bon endroit et au bon moment ?

Enregistre ton travail.
