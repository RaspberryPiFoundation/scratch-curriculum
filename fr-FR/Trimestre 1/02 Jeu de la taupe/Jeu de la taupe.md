Niveau 1

#La chasse aux sorcières

__Introduction:__
Ce projet est comme le jeu du __Tir aux Pigeons__. Tu gagnes des points en touchant les sorcières qui apparaissent à l’écran. Le but du jeu est de gagner le plus de points possibles en 30 secondes.

##Étape 1 : Crée une sorcière volante

1. Démarre un nouveau projet Scratch
2. Enlève l’objet chat et remplace l’arrière plan par l’arrière plan __nature/woods__.
3. Clique sur le bouton `Choisir un nouvel objet dans un dossier` pour ajouter un nouvel objet au projet (utilise le costume __fantasy/witch1__). 

__Maintenant, nous voulons faire bouger notre sorcière.__

4. Ajoute une `variable` pour l’objet sorcière. Appelle la variable `vitesse ` et coche “Seulement pour cet objet” Sur la __scène__, tu dois voir écrit “Objet 1 vitesse”. Si il est écrit seulement “vitesse”, supprime la variable et recommence. Lors de la création, il faut s’assurer de cliquer sur le bouton ‘Seulement pour cet objet”. On ne veut pas afficher la vitesse. Clique sur la zone à gauche de la variable ‘vitesse' dans __la palette des variables__. La variable ‘vitesse’ va contrôler la vitesse de déplacement de la sorcière. Nous allons utiliser une variable pour pouvoir changer la vitesse au cours du jeu.
5. Nous voulons que la sorcière commence à bouger quand le jeu démarre. __Écris donc un script comme ceci__ :

```scratch

	Quand drapeau préssé

	à vitesse attriber 5

	répéter indéfiniment

		avancer de vitesse pas

	(fin répéter indéfiniment)
```
		
###Teste ton projet
__Clique sur le drapeau vert__ et regarde ce que fait ta sorcière. Pourquoi reste-t-elle collée dans le coin de l’écran ?

6. Pour décoller la sorcière nous devons la faire partir dans l’autre sens quand elle touche le bord de l’écran. Au niveau de ton script, au dessous du bloc `avancer de vitesse pas ` ajoute le bloc `rebondir si le bord est atteint` 

```scratch

	Quand drapeau préssé

	à vitesse attriber 5

	répéter indéfiniment

		avancer de vitesse pas

		rebondir si le bord est atteint

	(fin répéter indéfiniment)
```
7. Pour que la sorcière n'ait pas la tête en bas quand elle touche le bord, clique sur le bouton `retournement gauche-droite uniquement`. 

###Teste ton projet
__Clique sur le drapeau vert.__ 
Est ce que la sorcière se déplace d’un bord à l’autre de l’écran ?

Enregistre ton travail.

###A essayer
__Essaie de changer la valeur de la variable “vitesse” pour faire voler la sorcière plus rapidement ou plus lentement.__

__Comment ferais-tu pour que la sorcière bouge de plus en plus vite ?__
(C’est une tâche délicate. Ne t’inquiète pas si tu n’arrives pas à le faire. Tu vas avoir plus d’indices en continuant le projet.)

##Étape 2 : Fais apparaître et disparaître la sorcière de manière aléatoire

Pour rendre le jeu plus amusant, nous voulons faire apparaître et disparaître la sorcière de manière aléatoire. Nous ferons ça avec un autre script qui va tourner en même temps que celui du mouvement de la sorcière. Ce script doit faire disparaître la sorcière pendant un temps aléatoire, puis la faire apparaître de nouveau pour un temps alétoire. Et recommencer indéfiniment (ou jusqu’à la fin du jeu) 

__Crée ce script pour la sorcière :__

```scratch

	quand drapeau préssé 

	répéter indéfiniment

		cacher

		attendre nombre aléatoire entre 2 et 5 secondes

		montrer

		attendre nombre aléatoire entre 3 et 5 secondes

	(fin répéter indéfiniment)
```
###Teste ton projet
__Clique sur le drapeau vert.__ 
Est-ce que la sorcière se déplace d’un bord à l’autre de l’acran, apparaît et disparaît d’une manière aléatoire ?

Enregistre ton projet.

###A essayer
__Essaie de changer les limites des nombres aléatoires. Qu’est ce qui se passe si tu choisis de grands nombres ou de petits nombres ?__
(Est-ce que ça te donne plus d’indices sur la manière d’accélerer la vitesse de la sorcière au fur et à mesure du jeu ?)

##Étape 3 : Fais disparaître la sorcière quand on clique dessus

Pour transformer notre projet en jeu, il faut donner aux joueurs quelque chose à faire. Ils ont besoin de cliquer sur la sorcière pour la faire disparaître. Quand ils la touchent, nous voulons qu’elle disparaisse tout en jouant un son.

1. Dans l’onglet __son__, importe le son __electronic/fairydust__. 

2. Ajoute ce script à la sorcière:

```scratch

	quand objet 1 pressé

	cacher

	jouer le son Fairydust
```
###Teste ton projet
__Clique sur le drapeau vert__ 

Est ce que la sorcière disparaît et joue un son quand tu cliques sur elle ?

Enregistre ton projet

###A essayer
__Demande si tu peux enregistrer toi même ta voix__

##Étape 4 : Ajoute un score et un chronomètre

Nous avons notre sorcière , mais nous voulons réaliser un vrai jeu ! Nous voulons marquer des points à chaque fois que nous cliquons sur la sorcière, ainsi qu’un temps de jeu limité. On va utiliser une variable pour le score et une pour le chronomètre.


1. Crée une nouvelle `variable`. Appelle la __Score__ et coche “Pour tous les objets”. Et change le script de la sorcière pour que le score augmente d’un point chaque fois qu’elle est pressée. 

```scratch

	quand objet 1 pressé

	cacher

	jouer le son Fairydust

	changer score par 1
```

2. Clique sur la __scène__ et crée une __nouvelle variable__ (cette fois juste pour la scène). Appelle la __chronomètre__. Ajoute un nouveau script qui s’exécute quand on appuie sur le drapeau vert. Le script met le chronomètre à __30__ et remet le score à __0__. Ensuite, utilise le bloc “répéter jusqu’à” pour attendre une seconde puis diminuer le “chronomètre” par 1. Il faut répéter tout ça jusqu’à ce que le chronomètre soit à 0. A ce moment là, utilise le bloc “arrêter tout” pour arrêter le jeu. 

```scratch

	quand drapeau pressé

	à chronomètre attribuer 30

	à score attribuer 0

	répéter jusqu’à chronomètre = 0

		attendre 1 seconde

		changer score par -1

	(fin répéter)

	arrêter tout
```


###Teste ton projet
__Clique sur le drapeau vert__ 

Enregistre ton travail

###A essayer
__Comment tu peux faire bouger la sorcière de plus en plus vite ?__


__Très bien. Tu as terminé le jeu de base. Mais tu peux encore améliorer le jeu. Relève ces défis !__

##Défi : ajoute d’autres sorcières

Une sorcière, c'est bien. Plus de sorcières, c’est encore mieux ! __Ajoutons deux autres sorcières volantes__
1. Duplique la sorcière en __cliquant dessus avec le bouton droit__ de la souris dans la zone des objets (la zone inférieure droite de l’écran) 
2. Change la taille de chaque objet pour avoir des sorcières de differentes tailles.
3. Pour chaque sorcière, change __la variable vitesse__ pour avoir des sorcières qui volent à des vitesses différentes.
4. Déplace les sorcières dans differents endroits de la scène.

###Teste ton projet
__Clique sur le drapeau vert.__ 

Est ce que tu as trois sorcières qui se déplacent d’un côté à l’autre de la scène ? Est ce qu’elles apparaissent et disparaissent d’une manière aléatoire ? Est ce qu’elles disparaissent quand tu cliques dessus ? 

Enregistre ton travail

###A essayer
1. Quel est le bon nombre de sorcières pour le jeu ?
2. Est ce que tu peux changer l’apparence des sorcières ? Tu pourrais éditer leurs costumes, ou bien utiliser des blocs de la palette “Apparence” pour les changer.
3. Est ce que tu peux faire marquer un nombre de points différent pour chaque sorcière ? Que penses-tu de faire que la plus rapide (et la plus petite) sorcière soit celle qui donne le plus de points ?


__Bravo ! Tu as terminé. Maintenant, tu peux t’amuser avec le jeu.__
N’oublie pas que tu peux partager ton jeu avec tous tes amis et ta famille en cliquant sur le bouton __Partage__ dans la barre des menus.
