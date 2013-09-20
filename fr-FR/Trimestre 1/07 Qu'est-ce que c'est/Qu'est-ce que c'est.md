Niveau 3

#Qu’est-ce que c’est ?!

__Introduction__
Un objet apparaît sur le tableau noir. A toi de deviner ce que c’est en cliquant sur l’image qui y correspond. Plus tu es rapide, plus tu marques de points !

##Étape 1 : Fais apparaître différents objets sur le tableau noir

Nous voulons qu’une variété de photos apparaisse sur le tableau noir.

1. Commence un nouveau projet et supprime le chat.
2. Sélectionne la scène puis l’onglet “Arrière-plans”. Importe l'arrière-plan “chalkboard” dans la catégorie “Indoors”.
3. Importe un nouvel objet et donne-lui le costume de ton choix, en puisant dans la catégorie “Things” par exemple.
4. Place l’objet au milieu du tableau noir, puis augmente ou réduis sa taille si nécessaire.
5. Sélectionne l’onglet “Costumes” et importe 4 costumes supplémentaires. (choisis ce que tu veux). Maintenant tu n’as plus qu'à les faire apparaître de manière aléatoire ! 
6. Crée le script suivant :

```scratch

	quand DRAPEAU VERT pressé
	répéter nombre aléatoire entre 1 et 5 fois		
		costume suivant
	(fin répéter)
```

###Teste ton projet
__Clique sur le drapeau vert.__

DEst-ce que l’objet change de costume ?

__Clique à nouveau plusieurs fois. __
Est-ce que le costume change à chaque fois ?
Le même costume peut apparaître deux fois de suite, mais c’est normal. Tu remarqueras aussi que l’objet clignote à chaque changement de costume. On réglera la chose dans l'étape suivante.

Enregistre ton travail.

##Étape 2 : Déforme l’image

__Faisons apparaître les images de manière déformée, pour ensuite les rendre plus claires après quelques secondes.__

Utilisons une variable “score” pour contrôler le niveau de déformation. Si le score est élevé, il y aura beaucoup de déformation. Au fur et à mesure que le score diminuera, l’image s'éclaircira. Le score jouera aussi le rôle de compte a rebours, comme pour la __carte Scratch “Chronomètre”__.

1. Vas dans le l’onglet “Variables” pour créer une variable appelée “score 

2. Change ton script de la manière suivante :

```scratch

	quand DRAPEAU pressé
	cacher
	répéter nombre aléatoire entre 1 et 5 fois		
		costume suivant
	(fin répéter)
	à score attribuer 110
	répéter jusqu'à score = 0
		changer score par -10
		mettre l’effet pixeliser à score
		mettre l’effet couleur à score
		montrer
		attendre 1 secondes
	(fin répéter)
```

Ajoute le bloc “cacher” au-dessus de la “boucle de répétition” et tout le reste en-dessous.

###Teste ton projet
__Presse sur le drapeau vert.__

Est-ce qu’une image déformée apparaît de manière aléatoire ?

Est-ce que l’image s'éclaircit petit a petit ?

Est-ce que le score diminue au fur et à mesure que l’image devient moins déformée ?

Est-ce que l’image est parfaitement claire quand le score arrive à zéro ?

Est-ce que tu obtiens une image différente chaque fois que tu cliques sur le drapeau vert ?


Enregistre ton travail.

##Les choses à essayer

__Essaie de changer le score initial et remarque la manière dont il change à chaque boucle.__ Quelle est son influence sur la manière dont l’image apparaît ? Est-ce que c’est plus difficile ou plus facile de reconnaître l’image ?

__Expérimente avec les différents effets visuels listés dans le menu déroulant.__ Est-ce que ça rend le jeu plus facile ou plus difficile ?


##Étape 3 : Permets au joueur de deviner l’image

Pour le moment on a une image aléatoire qui apparaît lentement et un score qui diminue avec le temps, mais comment gagner la partie ?
Nous allons ajouter quelques objets en bas de l'écran pour permettre au joueur de cliquer dessus. Si le joueur clique sur la bonne image il aura gagné. S’il clique sur la mauvaise alors elle disparaîtra et la partie continuera.

D’abord il nous faut savoir quelle réponse est la bonne :

1. 1.	Crée une nouvelle variable __appelée  réponse__, applicable pour tous les objets.
2. 2.	Change le script que tu as écrit pour capturer la bonne réponse : ajoute le bloc “À réponse attribuer costume n°” juste après la première boucle :

```scratch

	quand DRAPEAU pressé
	cacher
	répéter nombre aléatoire entre 1 et 5 fois		
		costume suivant
	(fin répéter)
	à réponse attribuer costume n°
	à score attribuer 110 
	répéter jusqu'à score = 0
		changer score par -10
		mettre l’effet pixeliser à score
		mettre l’effet couleur à score
		montrer
		attendre 1 secondes
	(fin répéter)
```
__Maintenant il faut ajouter les objets sur lesquels le joueur pourra cliquer.__

3. Copie l’objet principal et glisse la copie en bas à gauche de la scène.
4. Renomme l’objet __réponse1__ pour rendre la lecture de ces instructions plus facile.
5. Supprime le script de __réponse1__ ainsi que tous ses costumes, à l’exception du premier.
6. Répète ces 3 étapes, mais place __réponse2__ à cote de __réponse1__ et supprime tous ses costumes, à l’exception du second
7. Répète l'opération pour __réponse3__, __réponse4__ et __réponse5__. Tu devrais alors obtenir une rangée de 5 objets possibles en bas de la scène, chacun avec leur propre costume qui pourrait correspondre à l’objet principal à identifier. __Aucun des objets du bas ne doit avoir un script.__

Maintenant on veut faire en sorte que chacun des objets du bas puissent être cliqués et qu’ils réagissent différemment, suivant qu’ils soient la bonne ou la mauvaise réponse.

8. 1.	Crée ce script pour réponse1 :

```scratch

	quand réponse1 est pressé
	si réponse = 1
		envoyer à tous Gagné !
	sinon
		cacher
	(fin si)
```

9.2.	Glisse ce script avec la souris sur chacun des autres objets du bas et, __pour chacun, renomme le nom avec le chiffre correspondant (2,3,4,5).__
10. 3.	Maintenant il faut créer une réaction qui corresponde a la “bonne réponse”. Ajoute le script suivant :

```scratch

	quand je reçois Gagné !
	dire regroupe Félicitations, ton score est score
```

###Teste ton projet
__Clique sur le drapeau vert.__

Quand tu testes le jeu, tu peux utiliser le __moniteur de réponses__ pour vérifier la bonne réponse. Ça peut aider.

Que se passe-t-il quand tu cliques sur __la bonne réponse__ ?

Que se passe-t-il quand tu cliques sur __la mauvaise réponse__ ?

Qu’arrive-t-il à la mauvaise réponse __quand tu commences une nouvelle partie__?

Le teste révèle 2 problèmes : d’une part, les mauvaises réponses ne réapparaissent pas quand une nouvelle partie commence. D’autre part, le compteur ne s'arrête pas une fois que la bonne réponse est trouvée. 

11. Pour résoudre le premier problème, ajoutez le script suivant pour chacun des 5 objets du bas :

```scratch

	quand DRAPEAU pressé
	montrer
```

Pour résoudre le second problème, il faut arrêter la “boucle de répétition” de l’objet principal une fois que la bonne réponse est cliquée. 
Pour cela on va créer une nouvelle variable qui démarre à __0__ quand la partie commence, puis passe à __1__ quand la bonne réponse est trouvée. On fera alors arrêter la “boucle infinie”, __soit lorsque le score atteindra 0, soit lorsque la nouvelle variable “gagné” passera à 1__ :

12. Crée la nouvelle variable “gagné ?”
13. Change les scripts de la manière suivante :

```scratch

	Quand DRAPEAU VERT pressé
	Cacher
	Répéter nombre aléatoire entre 1 et 5 fois		
		Costume suivant
	(fin répéter)
	À réponse attribuer costume n°
	À score attribuer 110 
	À gagné attribuer 0
	Répéter jusqu'à score = 0 ou gagné = 1
		Changer score par -10
		Mettre l’effet pixeliser à score
		Mettre l’effet couleur à score
		Montrer
		Attendre 1 secondes
	(fin répéter)
	
	Quand je reçois Gagné !
	À gagné ? attribuer 1 
	Annuler les effets graphiques
	Dire regroupe Félicitations, ton score est score
```

Enregistre ton travail

__Bravo, tu as complété la création du jeu de base !__

Mais il pourrait être amélioré de plusieurs façons. Alors pourquoi n’essaies-tu pas les défis suivants ?


##Défi 1 : Change la difficulté du jeu

Change la difficulté du jeu

* Essaie de changer la vitesse a laquelle l’image s'éclaircit et le score diminue.
* Essaie de changer la manière dont l’image se déforme
* Essaie de changer les images à deviner pour les rendre plus similaires ou plus différentes. Mais n’oublie pas de modifier les costumes de manière correspondante.

Enregistre ton travail

##Défi 2 : Déforme l’image de manière différente à chaque partie

Pour le moment toutes les parties utilisent le même effet de déformation. A l’étape 2 tu as essayé d’autres effets qui fonctionnent aussi bien que couleur + pixelisation.

Trouves-en plusieurs autres.

Change le jeu pour qu’il utilise une déformation différente dans la _boucle de répétition_.

__Astuce :__ Crée une nouvelle variable appelée “distorsion”. Donne-lui une valeur aléatoire au début de chaque partie. Utilise un bloc “Si” a l'intérieur de la “boucle de répétition” de manière a donner la valeur nécessaire à “distorsion”.

Enregistre ton travail.

##Défi 3 : Fais une partie en plusieurs manches

Pour le moment chaque partie est indépendante. Fais que la partie soit sur plusieurs manches. Pour commencer mets 3 manches dans une partie, pour que le joueur puisse identifier 3 images et que son score puisse atteindre 3000 points.

__Astuce :__ tu auras besoin d’une nouvelle variable pour sauvegarder le score total. Il te faudra aussi une nouvelle “boucle” pour passer d’une manche à l’autre.

__Astuce : __Il faudra aussi faire réapparaître tous les mauvais choix précédents au début de chaque manche. Tu pourrais peut-être utiliser un “envoi a tous” ?
 
Enregistre ton travail.


##Défi 4 : Rends les manches plus difficiles au fur et a mesure

Rends chaque manche plus difficile que la précédente ?

Est-ce que les points obtenus doivent rester les mêmes ? 

Le joueur devrait-il gagner plus de points dans les manches plus difficiles ?

__Astuce :__ Comment est-ce que le jeu compte les manches ? Comment peux-tu utiliser ce compteur pour augmenter la difficulté et le score de chaque manche ?

Enregistre ton travail.


##Défi 5 : Termine quand le joueur fait un mauvais choix

Au lieu de limiter la partie à un nombre de manches précis, fais-la continuer jusqu’au moment ou le joueur ne devine pas la bonne image. Ça n’est probablement possible que si tu augmentes la difficulté du jeu d’un manche à l’autre.

Enregistre ton travail.

##Défi 6 : Fais correspondre la difficulté du jeu au niveau du joueur

Si le joueur devine les images rapidement, alors rends le jeu plus difficile et vice-versa. Mais attention : ce défi ne marche que si les parties ne sont composées que d’une manche !

Enregistre ton travail.


##Défi 7 : Garde le meilleur score en mémoire

Si un joueur bat le meilleur score demande lui d’entrer son nom. Le meilleur score et le nom du joueur doivent être affichés à l'écran. 

Enregistre ton travail.


##Défi 8 : Enlève des points si on se trompe

Jusque là on peut marquer des points en cliquant le plus vite possible sur toutes les réponses. Change le jeu pour que le score du joueur diminue s’il choisi une des mauvaises réponses.

Est-ce que ça rend le jeu plus amusant ?

Enregistre ton travail.


__Bravo, tu as fini, maintenant tu peux t’amuser ! __
! Et souviens-toi que tu peux partager ton jeu avec tes amis et ta famille, en pressant le bouton __Partager__ dans le menu du haut.
