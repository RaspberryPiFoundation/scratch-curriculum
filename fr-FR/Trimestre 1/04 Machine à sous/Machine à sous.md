Niveau 2

#Machine à sous

__Introduction:__
Dans ce jeu, il y a trois objets qui changent de costume. Pour gagner, il faut que les 3 s’arrêtent sur le même costume. C'est comme une machine à sous !

##Étape 1 : Crée un objet avec plusieurs costumes

__Importons les images dont nous aurons besoin__

1. Crée un nouveau projet. Efface le chat.
2. Importe un nouvel objet.
3. Choisi une image de n’importe quel dossier. Notre exemple utilise things/bananas1, mais tu peux prendre celle que tu veux.
4. Clique sur l’onglet “Costumes” et importe deux autres images et qu’il y en ait trois au total (nous avons pris animals/bee1 et things/lego, mais tu peux prendre n’importe quelle image).

__Maintenant qu'on a les images , nous voulons que l'objet change tout le temps de costume.__

##Étape 2 : Fais défiler les images

1. Clique sur l’onglet Scripts.
2. 2.	Clique sur Contrôle et fais glisser “quand *drapeau* est pressé” dans la zone des scripts. Cela mettra le jeu en marche quand tu appuieras sur le drapeau.
3. Ajouter le bloc “répéter indéfiniment” en le collant juste en dessous.
4. Clique sur le drapeau vert, en haut à droite. Tu vois la ligne blanche autour du script ? C’est parce qu’il est en marche.
5. Maintenant clique sur “Apparence” et fais glisser “costume suivant” dans le script. 
6. Commence faire pour qu’il change moins vite ? Clique sur Contrôle et fais glisser “attendre 1 secondes” dans le script
7. Règle la durée d’attente pour que cela soit plus rapide : clique sur le 1 et écris 0.1. Que se passe-t-il s’il manque le “attendre … secondes” ?

```scratch

	quand DRAPEAU pressé
	répéter indéfiniment		
		costume suivant
		attendre 0.1 secondes
	(fin de répéter)
```

###Teste ton projet
__Clique sur le drapeau vert.__ 
Est-ce que les costumes changent à une vitesse raisonnable ?

Enregistre ton travail

###À essayer

Change la durée du bloc "Attente". À ton avis, quelle durée d'attente rendrait le jeu trop facile ? Quel réglage serait trop dur ?

##Étape 3 : Arrêt sur image

Nous avons fait défiler les images. Mais comment faire pour que ça s'arrête quand on clique dessus ?

1. Clique sur “Variables” puis sur “Nouvelle variable”. Appelle-la “arrêt” et coche “Pour tous les objets”. Finalement, décoche la case pour que la variable ne s’affiche pas sur la scène.
2. Met “arrêt” à 1 quand on clique sur l’image, en utilisant les blocs “quand Object1 pressé” et “à arrêt attribuer 1”.
3. Ensuite il faut que l’image arrête de changer quand la variable “arrêt” vaut 1. Clique sur “Contrôle” et remplace le bloc “répéter indéfiniment” par le bloc “répéter indéfiniment si”. Clique sur “Opérateurs” et glisse le bloc avec un signe ” = “ à droite du “si”. A gauche du “=”, glisse la variable “arrêt”. Clique dans la case à droite du “=” et écrit “1”
4. Enfin, sous “quand DRAPEAU pressé”, glisse un bloc “à arrêt attribuer 0”.

###Teste ton projet
__Clique sur le drapeau vert, attends un petit instant, puis clique sur l'objet.__ 

Est-ce que les costumes changent comme il faut ? 
Est-ce que ça s'arrête sur une des images quand tu cliques ? 
__Fais les défiler de nouveau__ Est-ce que ça s'arrête quand tu mets simplement le curseur de souris dessus mais sans cliquer ? Est-ce que ça s'arrête quand tu cliques ailleurs sur la scène ? Ou autre part dans la fenêtre de Scratch ? Ou en dehors de Scratch ?

Enregistre ton travail

##Étape 4 : Crée les autres objets
__Avant de pouvoir jouer à notre jeu, nous devons encore créer les deux autres objets !__

1. Fais un clique-droit sur Objet1 et utilise Dupliquer.
2. Duplique le encore une fois. On a maintenant 3 Objets à l’écran.
3. Déplace les objets : mets les en ligne. Réduis-les si ils se chevauchent un peu.

###Teste ton projet
__Clique sur le drapeau vert.__ Tous les objets devraient changer de costume. Essaie de les arrêter tous sur la même image !

Enregistre ton travail

###À essayer

Quand on lance le jeu juste après l'avoir ouvert, tous les objets commencent par le même costume. Ils montrent aussi la même image quand ils défilent. Et si tu prenais un costume au hasard pour chacun des 3 objets quand on clique sur le drapeau vert ?

__Bravo, tu as fini les bases du jeu. Mais tu peux sûrement faire encore mieux. Essaye les défis suivants !__


##Défi 1 : Rends le jeu plus difficile

Essaie de changer la difficulté du jeu. C'est facile de faire défiler les images plus rapidement, alors utilise ton imagination pour trouver autre chose !
Tu pourrais essayer de 

1. Changer le nombre de costumes de chaque objet.
2. Donne des costumes uniques à certains objets.
3. Fais des pauses différentes entre les changements de costume.
4. Choisis le prochain costume au hasard au lieu de garder toujours le même ordre. 

__Amuse-toi à trouver de nouvelles idées !__

À chaque changement, demande-toi si ça rend le jeu plus dur ou plus facile. Est-ce trop facile ou trop difficile maintenant ? Essaie de trouver le juste milieu : le bon niveau de difficulté.


##Défi 2 : Adapte la difficulté

Tout le monde ne sera pas aussi doué que toi pour gagner le jeu. __Comment pourrais-tu ajuster le niveau de difficulté du jeu pour chaque joueur ?__

Une possibilité serait d' __adapter la vitesse de changement des costumes à la fin de chaque partie__. Tu peux utiliser une variable __délai__ et la mettre à la place de la durée du bloc "attente". Si le joueur gagne, tu peux réduire ce délai pour rendre le jeu un peu plus difficile. Et si le joueur perd, il faudra augmenter le délai pour rendre la prochaine partie plus facile.

##Défi 3 : Détecte si on a gagné ou perdu

__Le but du jeu est d’avoir 3 fois la même image. On a donc gagné quand les trois objets sont arrêtés sur le même costume. Comment annoncer au joueur s'il a gagné ou perdu ? Tu pourrais faire en sorte que la scène détecte si les 3 costumes sont les mêmes.__

D'abord, la scène doit savoir quand le jeu est terminé. Pour cela, à chaque fois que l'on clique l'un des objets, la scène peut vérifier si les 3 objets sont arrêtés. Va donc modifier le bloc "quand objet# pressé" des 3 objets et ajoute l'envoi d'un message "vérifierFin".

Quand la scène reçoit ce message, elle peut vérifier si la variable "arrêté" des 3 objets est égal à 1. Utilise pour cela des blocs "position x de felix", puis remplace "position x" par "arrêté" et "felix" par les objet#. Si les trois ont la valeur 1, alors la partie est terminée, et nous pouvons ensuite regarder si le joueur a gagné.

Pour savoir si on a gagné ou perdu, nous allons vérifier le costume des 3 objets : Si objet1 a le même costume que objet2, et si objet2 a le même costume que objet3 alors c'est gagné ! Tu peux réutiliser des blocs "position x de felix".

Pour comparer les 3 objets, tu auras besoin d'un bloc "si" pour vérifier les variables "arrêté" et à l'intérieur tu mettras un bloc "si... sinon" pour vérifier si le joueur a gagné ou perdu en comparant les costumes des objets..

À partir de là, tu pourrais envoyer un message "gagné" ou "perdu" et y répondre avec un nouvel objet : Peut-être pourrais-tu faire apparaître Félix pour féliciter ou plaindre le joueur ?

__Bravo, tu as fini ! Tu peux maintenant t’amuser !__
N’oublie pas que tu peux partager ton jeu avec tes amis et ta famille en cliquant sur le bouton __Partager ce projet__ en haut à droite. à côté du globe et de la disquette
