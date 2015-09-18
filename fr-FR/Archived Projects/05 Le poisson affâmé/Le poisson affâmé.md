Niveau 2

#Le poisson affâmé

__Introduction:__
On va faire un jeu de mâchage de poisson. Guide le gros poisson affamé et essaye de manger les proies qui nagent tout autour. 

##Étape 1 : Crée un objet qui change de costume
__Programmons le poisson pour qu’il puisse nager dans la mer :__

1. Commence un nouveau projet Scratch.
2. Séléctionne la scène puis sélectionne l’onglet ‘Arrière-plans’. Importe l’arrière-plan “underswater” qui se trouve dans le dossier ‘nature’ et supprime “arrière-plan1”.
3. Change le nom du chat et appelle le “Le poisson affamé”.
4. Importe le costume du poisson “hungry-fish” depuis le dossier “resources” puis supprime les costumes existants costume1 et costume
5 Utilise le bouton au dessus des costumes pour faire en sorte que le costume du poisson ne se retourne qu’horizontalement, de gauche à droite.
6. Maintenant, nous allons créer un script pour “Le poisson affamé” afin qu’il suive ta souris :

```scratch

	quand DRAPEAU pressé
	répéter indéfiniment		
		pointer vers pointeur de la souris
		avancer de 3 pas
	(fin répéter indéfiniment)
```

###Teste ton projet
__Clique sur le drapeau vert.__ 
Déplace le pointeur de la souris partout dans la mer. Est-ce que le poisson suit le pointeur ? Qu’est qui se passe si tu ne bouges pas le pointeur de la souris et que le poisson le touche ? Comment ça a l’air ? Pourquoi il se comporte de cette façon ?



7. Tu peux empêcher le poisson affamé de se retourner comme un fou. Il ne doit bouger que s’il n’est pas trop près de la souris (le bloc __distance de__ se trouve dans la palette “Capteurs”) 


```scratch

	quand DRAPEAU pressé
	répétrer indéfiniment si distance de pointeur de souris > 10
		pointer vers pointeur de souris
		avancer de 3 pas
	(fin répéter indéfiniment)
```


###Teste ton projet

Enregistre ton travail

##A essayer

Si tu veux, tu peux changer les nombres qui sont dans le script.
Comment cela influence-t-il le mouvement du poisson ?
Change la distance seuil à un grand nombre (par exemple 100) ou un petit (par exemple 1). Change le nombre de pas du poisson à une grande valeur (par exemple 20) ou une petite (par exemple 1 ou même 0).


##Étape 2 : Ajoute une proie

1. Ajoute un nouveau object à partir du fichier “animals/lobster1” 
2. Utilise l’outil “réduire” (au dessus de la scène) pour rendre le l’objet plus petit.
3. Nous allons créer un script pour permettre à la proie de nager. Nous voulons qu’elle se déplace d’une façon aléatoire. Donc, elle va se déplacer en avant. Puis, elle va se tourner aléatoirement à droite ou à gauche et ainsi de suite :

```scratch

	quand DRAPEAU pressé
	Répéter indéfiniment		
		avancer de 2 pas
		tourner de nombre aléatoire entre -20 et 20 degrés
		rebondir si le bord est atteint
	(fin répéter indéfiniment)
```

###Teste ton projet
__Clique sur le drapeau vert__ vert et regarde la proie nager. 
Est-ce qu’elle nage comme tu t’attendais ? Est-ce que son mouvement est réaliste ?

__Pour le moment, le poisson affamé et la proie n’intéragisse pas encore entre eux. On va résoudre cela dans la prochaine étape.__

Enregistre ton travail.

###A essayer

* Essaie de changer les nombres des blocs “nombre aléatoire” et “avancer de”. Comment cela affecte-t-il le mouvement de la proie ?
* Que fait le bloc __rebondir si le bord est atteint__ ? Enlève-le et regarde ce qu’il se passe.

##Étape 3 : Le poisson affamé mange la proie

__Maintenant, nous allons programmer le poisson affamé pour qu’il mange la proie !__ Une fois que le poisson a pris la proie dans sa bouche, deux choses doivent se passer :
* Le poisson affamé doit fermer sa bouche et faire un bruit de mâchage.
* La proie doit disparaître, et réapparaît après quelques instants.

1. Au début, nous allons faire disparaître la proie si elle touche le poisson affamé, puis elle va réapparaître 3 secondes plus tard. 
Pour effectuer cette tâche, utilise le bloc “touché” :


```scratch

	quand DRAPEAU pressé
	répéter indéfiniment		
		avancer de 2 pas
		tourner de nombre aléatoire entre -20 et 20 degrés
		rebondir si le bord est atteint
		si Le poisson affamé touché
			cacher
			attendre 3 secondes
			montrer
		(fin si)
	(fin répéter indéfiniment)
```

###Teste ton projet
__Essaye de nouveau ton programme. Est-ce que tu as détecté un problème ?__ Remarque que la proie disparaît indépendamment de l’endroit où elle touche le poisson. En plus, le poisson peut juste attendre 3 secondes au même endroit et manger la proie une fois réapparue. Ce n’est pas juste !

2. Comment on peut faire pour  	que la proie ne disparaît que si elle touche la bouche du poisson ? Dans ce cas, il est possible d’utiliser le bloc “couleur touchée” et vérifier si elle touche les dents bleues. Pour cela, remplace le bloc “touché” par le bloc “couleur touchée” dans le script. Clique sur la couleur (dans le bloc) puis clique sur les dents du poisson. 
3. Ensuite, nous pouvons déplacer la proie à un point aléatoire de la scène avant de le faire réapparaître. Nous allons utiliser le bloc “aller à x: y:” et donner des valeurs aléatoires à x et y.

```scratch

	quand DRAPEAU pressé
	répéter indéfiniment		
		avancer de 2 pas
		tourner de nombre aléatoire entre -20 et 20 degrés
		rebondir si le bord est atteint
		si couleur [] touchée
			cacher
			attendre 3 secondes
			aller à x: nombre aléatoire entre -220 et 220 y: nombre aléatoire entre -170 et 170
			montrer
		(fin si)
	(fin répéter indéfiniment)
```
###Teste ton projet

Est-ce que la proie disparaît quand elle touche uniquement les dents du poisson ? Est-ce qu’elle réapparaît à un endroit aléaotoire de l’écran au lieu de l’endroit où elle a été mangée ? 

4. Le poisson a besoin de savoir quand il a mangé une proie pour pouvoir jouer un son et changer son apparence. Pour cela, il est possible que la proie diffuse un message pour dire qu’elle s’est faite manger. 

```scratch

	quand DRAPEAU pressé
	répéter indéfiniment		
		avancer de 2 pas
		tourner de nombre aléatoire entre -20 et 20 degrés
		rebondir si le bord est atteint
		si couleur [] touchée
			envoyer à tous mangé
			cacher
			attendre 3 secondes
			aller à x: nombre aléatoire entre -220 et 220 y: nombre aléatoire entre -170 et 170
			montrer
		(fin si)
	(fin répéter indéfiniment)
```
__Maintenant, nous voulons que le poisson réponde à ce message en faisant le bruit du mâchage et en claquant ses mâchoires.__

5. Ajoute le costume “resources/mouth-closed” et le son “resources/chomp” au poisson affamé.
6. Ensuite, ajoute-lui un nouveau script en réponse au message diffiusé par la proie. Ce script doit jouer le son “chomp”, puis effectuer un changement vers le costume “mouth-closed”. Après, il y un cours moment d’attente suivi par un changement vers le costume original.

```scratch

	quand je reçois mangé
	jouer le son chomp
	répéter 2 fois
		basculer vers le costume mouth-closed
		attendre 0.5
		basculer vers le costume hungry-fish
	(fin répéter)
```

__Maintenant, ton poisson affamé est prêt à manger. Nous allons remplir la mer avec des proies. Clique sur la proie avec le bouton droit de la souris puis clique sur le bouton “dupliquer” plusieurs fois.__

###Teste ton projet
Clique sur le drapeau vert.
Est-ce que le poisson mange les proies ? Est-ce qu’il mange chacune des différentes proies ? 

Enregistre ton travail.

###Réfléchis à ces questions
Pourquoi doit-on ajouter le bloc “montrer” au début du script de la proie ?
Pense à ce qui peut se passer si la proie est mangée et que le jeu est arrêté avant son apparition. Que se passerait-il si je jeu était relancé de nouveau ?

__Très bien ! Tu as terminé la base du jeu. Il y a d’autres choses que l’on peut dans ton jeu. Es-tu prêt pour le défi ?__


##Défi 1 : La proie se déplace autrement

Pour le moment, toutes les proies avancent de la même façon. __Peux-tu faire en sorte qu’une d’elles se déplace d’une manière différente des autres?__ 
__Astuce__ Ne perds pas trop de temps dans cette partie sans jeter un oeil sur les autres acitvités du projet.

__Prends une des proies pour y faire des expériences.__ S’ils ont le même costume, tu peux modifier la couleur avec le boc __mettre l’effet couleur à__. Ainsi, tu pourras différencier ta proie de test du reste des proies.

Ralentis le déplacement de ta proie par rapport aux autres. __Astuce:__ Regarde le bloc “avancer de 2 pas”.


###Teste ton projet
Est-ce que ta proie se déplace plus lentement ? Est-ce que ça améliore le jeu ? Si tu arrives à faire ça, __tu peux aussi accélerer une autre proie.__ 

Est-ce que ces changements améliorent le jeu ?
__Astuce:__ Si la proie nage en rond, vérifie la valeur l’angle dans “tourner de x degrés”.

Et si tu changeais le comportement de chaque proie pour qu’elles se comportent toutes différemment, en combinant tous ces changements ?

Est-ce que l’un de ces changements améliore le jeu ?
Est-ce que ça rend le jeu plus intéressant, encore plus amusant, plus difficile ou facile ?
Est-ce qu’il y a un changement qui est le meilleur que les autres ? 


Enregistre ton travail.

##Défi 2 : La proie doit éviter le poisson affamé

Les proies dans ce jeu sont vraiment stupides ! Elles nagent au hasard jusqu’à ce qu’elles soient mangées !
Les vrais poissons nagent loins de leurs prédateurs. __Nous allons permettre à l’une des proies de nager loin du poisson affamé.__

Il n’y a pas de bloc dans Scratch qui informe de la direction qu’un autre objet est en train de prendre. Mais, il est possible de faire bouger un objet vers un autre, puis de le retourner dans le sens inverse. Les blocs dont tu as besoin se trouvent dans la palette __Mouvemen__

En t'inspirant de cette idée, __tu peux programmer une des proies à toujours se déplacer loin du poisson affamé__. Tu pourrais même avoir envie de la voir se tortiller quand elle s’enfuit.

###Teste ton projet
Est-ce que cette proie est plus difficile à attrapper ? Est-ce que ça améliore le jeu ? 

Enregistre ton travail.

##Défi 3 : Ajoute un score
Ce n’est pas suffisant de juste manger les poissons. Comment savoir que tu es le meilleur parmi tous tes amis ? __Tu as besoin d’un moyen pour conserver le score__. Nous allons ajouter un tableau des scores. 
Regarde __la carte Scratch “Garder les scores”__ pour avoir une idée sur la façon de le faire.

Où faut-il mettre le tableau des scores ?

Assure-toi que le score commence à 0 quand le jeu commence. Où peux-tu mettre ce bloc de code ?

###Teste ton projet
Est-ce que le score commence par 0 quand le jeu démarre ? Est-ce qu’il augmente à chaque fois que tu manges une proie ?

Enregistre ton travail.

##Défi 4 : Ajoute un compte à rebours

__Fixe-toi une limite de temps dans le jeu.__ Combien de proies es-tu capable de manger en 30 secondes ?

Regarde __la carte Scratch “Chronomètre”__ pour savoir comment ajouter un compte à rebours au jeu. Commence avec un jeu qui dure 30 secondes.

###Teste ton projet
Est-ce que le compte à rebours commence à 30 ?

Est-ce qu’il diminue à la bonne vitesse ?

Est-ce qu’il est possible d’attrapper une proie quand le compteur est en marche ? 

Est-ce que le jeu se termine quand le compte à rebours atteint 0 ?

Enregistre ton travail.

##Défit 5 : Ajoute un score de bonus
Fais gagner un super bonus si tu arrives à manger 3 proies en même temps. Comment peux-tu dire combien de proies ont été mangées ? 

__Astuce__: Une façon de le faire est __d’utiliser une variable qui compte le nombre de proies qui nagent ensemble__

Enregistre ton travail.

##Défi 6 : Change la règle - garde une proie en vie

Parfois, tu peux avoir de nouvelles idées géniales partant d’une idée et en faisant le contraire. __Modifie ton jeu de sorte que, au lieu de contrôler le poisson affâmé qui essaie de manger les autres, tu contrôles une proie dans une mer pleine de poissons affamés.__ 
Combien de temps peux-tu jouer avant d’être mangé ?

Enregistre ton travail

__Très bien. Tu as términé. Maintenant, tu peux t’amuser en jouant à ton jeu !__
N’oublie pas que tu peux partager ton jeu avec tous tes amis et ta famille en cliquant sur le bouton __Partager__  dans la barre de menus.

