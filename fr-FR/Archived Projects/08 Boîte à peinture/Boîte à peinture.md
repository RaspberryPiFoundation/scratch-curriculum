Niveau 3

#Boîte à peinture

__Introduction:__
Ce projet permet de te réaliser un outil de dessin pour faire ton propre art. Tu peux changer la couleur d’une ligne, effacer l’écran, faire des tampons et beaucoup d’autres choses.

##Étape 1 : Clique et dessine

Nous allons commencer par un crayon qui dessine quand tu le déplaces autour de la scène.

1. Commence un nouveau projet Scratch. Supprime le chat en cliquant dessus avec le bouton droit de la souris puis en cliquant sur ‘supprimer’.
2. Clique sur ‘Scène’ puis __Arrière-plans’__. Importe __l’arrière plan__ : __indoors/chalkboard__.
3. Créé un nouvel objet appelé : __Crayon__. Importe le fichier __resources\crayon-vert__.
4. Bascule vers l’onglet __costumes__ et clique sur le bouton ‘Edit’. Dans __l’éditeur graphique__, change le centre de l’image pour qu’il soit à la pointe du crayon. Pour cela, clique sur le bouton _Définir le centre du costume_ et déplace les lignes jusqu’à ce qu’elles soient à la pointe.
5. 5.	Nous allons programmer le crayon pour suivre la souris lors de son mouvement dans la scène. On va utiliser les blocs __Répeter indéfiniment__ et __aller à pointeur de souris__.

```scratch
Quand DRAPEAU pressé
Répéter indéfiniment
	aller à pointeur de souris
(fin répéter indéfiniment)
```

__Maintenant, nous voulons utiliser l’objet ‘Crayon’ comme un vrai stylo.__ Dans la section "Stylo", tu trouveras toute sorte de blocs pour dessiner. Commencons par les blocs  __abaisser le stylo__ et __relever le stylo__.

6. Nous voulons utiliser le bouton de la souris pour contrôler le crayon. Quand ce bouton est préssé, le crayon doit être abaisé. Et quand il est relaché, le crayon doit être relevé. On peut réaliser ça en utilisant les blocs ‘si … sinon’ et ‘souris préssée’

```scratch
Quand DRAPEAU préssé
Répéter indéfiniment
	aller à pointeur de souris
	si souris préssée
	abaisser le stylo
	sinon
	relever le stylo
	(fin si)
(fin répéter indéfiniment)
```
##Teste ton projet
__Clique sur le drapeau vert.__
Est-ce que le crayon suit la souris ? Qu’est-ce qui se passe si tu maintient préssé le bouton de la souris et que tu la déplaces autour de la scène ? Ne t’inquiète pas pour le moment pour la couleur de la souris.


7. L'écran sera vite rempli de gribouillages. Le bloc ‘effacer tout’ sert à nettoyer la scène.

```scratch
Quand DRAPEAU préssé
effacer tout
Répéter indéfiniment
	aller à pointeur de souris
	si souris préssée
	abaisser le stylo
	sinon
	relever le stylo
	(fin si)
(fin répéter indéfiniment)
```

##Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que le dessin que tu a fait disparaît quand tu clique sur le drapeau vert ?

Enregistre ton travail

##Étape 2 : Effacement

Au lieu d’être obligé d’arrêter et de lancer le projet, nous allons ajouter un bouton qui efface le dessin. ça va se faire avec le bloc ‘effacer tout’

1. Créé un nouvel objet à partir du costume __resources/cancel button__  
2. Change le nom de l’objet à __Effacer__
3. Positionne l’objet près du coté inférieur gauche de la scène
4. Ajoute ce script à l’objet ‘Effacer’


```scratch
Quand ‘Effacer’ préssé
     effacer tout
```

##Teste ton projet
__Clique sur le drapeau vert__

Est-ce que le bouton effacer permet d’effacer tout ce que tu as dessiné ? 

Enregistre ton travail. 

##Étape 3 : Changement de couleurs

Pour le moment, on ne peut dessiner que des lignes bleues. Ajoutons plein d’autres couleurs ! Pour cela, nous allons mettre de nouveaux objets en bas du cadre : des boutons de différentes couleurs. Un clic sur l'un des boutons changera la couleur du trait. Pour savoir quelle est la couleur en cours, nous ferons également changer la couleur de l'objet Crayon. 

1. Ajoute un nouvel objet, appelé ‘Rouge’, en utilisant le costume __resources/red-selector costume__
2. Place le quelque part au dessous du cadre, près du __bouton effacer__
3. Quand l’objet ‘Rouge’ est préssé, il doit envoyer à tous le message _Rouge_

```scratch
Quand ‘rouge’ préssé
envoyer à tous ‘rouge’.
```
__Oui, c’est tout ! Le gros du travail sera fait par le crayon__

Séléctionne l’objet Crayon. Puis importe un nouveau costume __resources/red-pencil__. Modifie le centre du crayon pour qu’il soit à la pointe du crayon comme tu l’as déjà fait pour le costume original.

4. Ajoute un nouveau script pour le crayon. Quand le crayon reçoit le message __Rouge__, il doit changer la couleurs du costume vers le costume rouge et change la couleur du crayon à la couleur rouge. (en utilisant le bloc ‘mettre la du stylo à ‘)

__Astuce :__ Si tu clique sur le carré coloré au niveau du bloc __mettre la couleur du stylo à__ tu peux cliquer avec la pipette sur l’objet rouge pour s’assurer que c’est la même couleur. 

```scratch
Quand je reçoit rouge
Basculer sur le costume red-pencil
Mettre la couleur du stylo à Rouge.
```

##Teste ton projet
__Clique sur le drapeau vert__

Commence par dessiner une ligne. Puis clique sur l’objet ‘rouge’ (que tu viens d’ajouter) et dessine encore. Est-ce que le crayon change de costume ? Est-ce qu’il dessine maintenant avec la couleur rouge ? Est-ce qu’il dessine de la pointe du crayon ?

Enregistre ton travail.

5. Répete ce que tu viens de faire pour les objets ‘Bleu’, ‘jaune’ et ‘vert’. 

##Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que tous les selectionneurs de couleurs fonctionnent ? Est-ce qu’ils changent le bon costume du crayon ? Est-ce qu’ils permettent au crayon de dessiner avec la bonne couleur ? Est-ce que tous les costumes dessinent avec la pointe de la souris ? 

Enregistre ton travail

##Étape 4 : Dessiner uniquement dans la bordure

Tu sans probablement remarqué qu’il est possible de dessiner partout sur la scène, même sur la bordure. On ne veux pas que cela se produise. On veux garder le dessin au mileu de la scène. On peut faire ça en s’assurant que le crayon n’est pas autorisé à quitter la zone de dessin - la zone gris claire de la scène.

Rappelle toi que Scratch définit un point en utilisant les axes X et Y. Notre zone de dessin se trouve entre -230 et 230 sur l’axe X, et entre -170 et 170 sur l’axe Y. On peut utiliser ces valeurs dans un bloc __si__ pour être sûr que la souris est à l’intérieur de cette zone . 

Pour réaliser ça, enveloppe ce que tu as déjà fait (blocs __aller à__ et __Si souris préssé__) dans un nouveau bloc ‘Si’. A l’intérieur de ce nouveau bloc, tu dois vérifier que : 

Souris Y est supérieur à -120 et souris Y est inférieur à 170 et souris X est supérieur à -230 et souris X est inférieur à 230

__Note__: Pour le faire, tu as besoin d'utiliser à plusieurs reprises le bloc __ET__ (dans la section Opérateurs) : 1 bloc pour les deux conditions de la position souris X, un autre pour les deux conditions de la position souris Y, et au final un autre bloc pour joindre tous ensemble. 

```scratch
effacer tout
répéter indéfiniment si souris Y > -120 ET souris Y < 170 ET souris X > -230 ET souris X < 230 
aller à pointeur de souris
```

Puisqu’on ne peux pas dessiner à l’éxtérieur de la zone de dessin, il est possible de cacher le crayon quand il la quitte. Pour cela, remplace le bolc __si__ avec le bloc __si … sinon__. Garde la même condition pour le __si__, et montre le crayon si c’est vrai. Sinon, cache le. 

```scratch
Quand DRAPEAU préssé
relever le stylo
effacer tout
Répéter indéfiniment
	si souris Y > -120  ET souris Y < 170 ET souris X > -230 ET souris X < 230 
		aller à pointeur de souris
		montrer
		si souris préssée
			abaisser le stylo
		sinon
			relever le stylo
		(fin si)
	sinon
		cacher
	(fin si)
(fin répéter indéfiniment)
```

##Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que tu peux encore dessiner à l’intérieur de la zone de dessin ? Est-ce que tu peux dessiner à l’éxtérieur de la zone ? Que se passe-t-il pour le crayon quand tu quittes la zone de dessin et que tu y reviens ? 

Enregistre ton travail

##Étape 5 : Gomme
__Dessiner des lignes est sympa, mais parfois tu fais des erreurs et tu as envie de les effacer.__ On peut faire ça avec un nouveau crayon qui dessine avec la couleur grise ( la même que le fond) 

Ajoute un nouvel objet-bouton à la scène pour selectionner la gomme. Pour cela, utilise le costume __resources/eraser__. Il faut le rendre plus petit pour s’adapter à sa position en bas de la scène. ça doit fonctionner de la même façon que les autres boutons (selectionneur de couleurs), ç-a-d il envoie un message ‘Effacer’

L’objet crayon doit répondre à ce message en changeant la couleur à gris (Rappelle toi que tu peux utiliser __la pipette pour selectionner__ la couleur de l’arrière-plan). Tu as besoin aussi d’un nouveau costume pour répresenter la gomme : Utilise le costume __resources/eraser__. __Rappelle toi de supprimer le centre du costume__. 


##Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que la gomme efface les lignes ? Est-ce que ça marche jusqu’à la pointe ? Est-ce que tu peux baculer entre la gomme et le crayon ?

Enregistre ton projet

##Étape 6 : Estampille

La chose suivante à faire est d’ajouter un outil pour estampiller des petites images. Voici comment procéder:

1. Ajoute un nouvel objet en utilisant n’importe quel image ou costume tu veux. Réduit la taille de l’objet et place le au dessous de la scène près des autres outils. Quand cet objet est préssé, il doit envoyer le message __estampille__
2. Ajoute un nouveau costume pour l’objet crayon. Il doit être le même que celui choisis pour le bouton __estampiller__
3. Selectionne l’objet crayon et créé une nouvelle variable __mode écriture__ pour cet objet uniquement. Nous allons utiliser cette variable pour savoir si on est en train de dessiner ou d’estampiller. 
4. Ajoute un nouveau script pour répondre au message ‘estampille’. Le script doit basculer le costume vers le costume ‘estampiller’ et attribuer la valeur __Faux__ à la variable __mode écriture__. 
5. Modifie les autres scripts qui répondent au message de selection de couleur (Rouge, vert, bleu et effacer) en attribuant la valeur __Vrai__ à la variable __mode écriture__
6. Finalement, nous allons contrôler la variable __quand le bouton de la souris est préssé__ et voir si ça doit dessiner ou estampiller. Si ‘mode écriture’ = Vrai, nous devons utiliser le bloc __abaisser le stylo__. Sinon, nous devons estampiller.  

##Teste ton projet
__Clique sur le drapeau vert__

Est-ce que l’outil ‘estampiller’ marche correctement ? 

Qu’est-ce qui se passe quand tu reviens vers l'un des outils "crayon" normaux ?

Enregistre ton travail. 

__Bravo, tu as terminé les étapes de base pour ce projet. Essaye ces défis.__

##Défi 1 : Le crayon en arc-en-ciel

Ajoutons un crayon spécial qui dessine avec les couleurs de l’arc-en-ciel. C’est une chose qu’il n’est pas possible de faire un un stylo ou crayon ordinaire. ça va être sympa de montrer comment dessiner avec un ordinateur permet de faire tant de choses. Le secret pour le réaliser est le changement de la couleur du crayon par bloc.

Avant tout, ajoute un objet qui permet de selectionner l’outil arc-en-ciel. Puis, ajoute un costume à l’objet crayon. 

1. Créé un nouvel objet comme outil de selection et place le au dessous de la scène, à coté des autres objets de selection. Utilise le costume resources/rainbow-selector et programme le pour envoyer le message arc-en-ciel quand il est cliqué
2. Ajoute le costume resources/rainbow-pencil à l’objet crayon

Tu as besoin de faire un script qui change la couleur du crayon plusieurs fois par seconde pour donner l’effet de l’arc-en-ciel (J’ai trouvé que le changer par 5 changer 0.05 secondes fonctionne bien, mais tu dois essayer differentes valeurs). La carte Scratch "minuteur" montre comment rendre une chose changer fréquemment. Utilise le bloc ‘modifier la couleur du stylo par’ au lieu de changer le compteur de temps par -1 à l’intérieur de la boucle.

Tu as besoin aussi de contrôler cette boucle de façon à ce que le changement de couleur ne se fasse que si le crayon en arc-en-ciel est selectionné. Sinon, tous les crayons vont avoir l’effet arc-en-ciel. C’est réalisable de la même façon avec laquelle tu as fais le changement entre le mode crayon et le mode estampille. Tu as besoin de créer une variable appelé ‘changement Arcenciel’ qui contient la valeur vrai quand tu veux l’effet d’arc-en-ciel, sinon elle va contenir la valeur faux. A chaque fois que le crayon réponde à un message de selection de l’un des outils, ça doit affecter la valeur de la variable ‘changement arcenciel’ en conséquence. 

Utilise ce que tu as appris précédement dans l’étape 6 pour contrôler l’effet arc-en-ciel. Le script qui répond au message de selection d’outils va modifier deux variables : ‘mode écriture’ et ‘changement Arcenciel’. 

##Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que l’outil arc-en-ciel fonctionne correctement ?

Que ce passe-t-il quand tu bascules de nouveau à un des outils de selection ?
 
Enregistre ton travail.

##Défi 2 : Raccourcis clavier

Au lieu d’utiliser les objets du bas de la scène comme outils de selection, tu peux utiliser le clavier pour selectionner les differents outils. Tu peux utiliser le bloc ‘Quand [] est préssé’ pour réagir au clavier. Pour chaque touche de raccourci que tu veux utiliser, tu auras besoin d’un nouveau bloc ‘Quand touché préssé’. Ce bloc devra envoyer le même message que l'objet correspondant diffuse au clic. Ajoute tous ces scripts à la scène.

Essaye d'ajouter les raccourcis suivants :
* Effacer -e
* Gomme -g
* Crayon rouge -r 
* Crayon bleu -b
* Crayon jaune -j
* Crayon vert -v
* Crayon en arc-en-ciel -c
* Estampille -s

##Teste ton projet
__Clique sur le drapeau vert__

Est-ce que tous les outils sont selectionnés avec le bon raccourcis clavier ? Est-ce que chacun des outils fonctionne convenablement quand il est séléctionné avec le clavier ? Est-ce que les outils sont toujours séléctionnés convenablement avec les objets d’en bas de la scène ?

Enregistre ton travail

##Défit 3 : Grand et petit
Une autre caractéristique que la plus part des outils de dessin possède est la possibilité de changer la taille du stylo. Ajoutons cela ! Il y a quand même une complication. Parfois, le redimensionnement doit changer la taille du stylo et parfois ça doit changer la taille du costume de l’objet. Cela dépend si vous utilisez un crayon ou un estampille.

Créé deux nouveaux objets de selection appelé : agrandir et réduire. Ils doivent les costumes resources/bigger-selector (pour agrandir) and resources/smaller-selector ( pour réduire). Ils doivent aussi envoyer le message agrandir et réduire. 

L’objet crayon peut répondre à ces messages en changeant soit la taille du stylo par 1 ou la taille de costume par 10. Cela dépend de la valeur du mode d’écriture (utilise le bloc si-sinon, de la même manière avec la quelle l’objet choisisse entre abaisser le stylo ou le relever) Rappelle toi de faire les raccourcis pour les nouveaux objets. J’ai utilisé la flèche haut et la flèche bas. 

Enregistre ton travail.

Tu as sans doute remarqué que le changement de la taille de l’estampille change aussi la taille du crayon quand tu bascules à cet outil. Pour arrêter ça, tu as besoin de fixer la taille à 100% à chaque fois tu bascule au crayon. De cette façon, l’outil apparaît avec la bonne taille. 

Pour améliorer, change le script pour que l’estamille se rappelle de la taille qu’il avait avant la selection du crayon. Il doit récupérer cette taille quand tu le selectionnes de nouveau. La façon la plus facile pour le faire est de créer une nouvelle variabale que tu peux appeler tailleEstampille. La variable est mise à jour à chaque fois que la taille de l’estampille change. Quand l’outil estampille est selectionné, il peut définir sa taille à partir du contenu de cette variable. 

##Teste ton projet
__Clique sur le drapeau vert.__

Est-ce que le contrôl de la taille fonctionne pour le crayon ? 

Qu’est-ce qui se passe quand tu bascules à l’estampille, tu changes la taille puis tu bascules de nouveau au crayon ?

Enregistre ton travail

_Très bien ! Tu as terminé ! Maintenant, tu peux t’amuser avec le jeu._


Rappelle toi que tu peux partager ton jeu avec tous tes amis et famille en cliquant sur le bouton __Partager__ dans la barre des menus.
