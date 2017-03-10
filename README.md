
Thradrukohat donne au joueur pour but de constuire une intelligence artifcielle dans le cadre d'un jeu de stratégie type starcraft.
Le joueur procèdera à l'écriture de scripts permettant de gérer le comportement de chaque type d'unité. Il pourra l'écrire dans le langage de son choix, tant qu'il est supporté par le jeu.
Ce jeu contient une version mono joueur lié à un mode tutoriel permettant de construire une IA en suivant des niveaux de complexité de plus en plus important.
Ce jeu contient une version multijoueur permettant de hoster une partie avec les programmes de plusieurs joueurs.

Ce jeu devra faire tourner un nombre non limité de langage de programmation, tant que ceux ci sont capable de lire un input console, et d'envoyer un input console.

Les ordres seront exécutés pour un tour de jeu. Un tour de jeu par exemple, est exécuté toutes les 100 ms. Si un parcours de boucle d'un joueur se termine au bout de 150ms et qu'il ne transmet ces ordres qu'en fin de boucle, ces ordres seront exécutés en tour 2.
Si jamais les ordres sont envoyés au fur et à mesure, les ordres seront exécutés dans le tour, de leur émission.

Les premiers concepts développés seront :
- une carte fixée en début de jeu
- une base centrale construite au démarrage du jeu
- des localisations de minerai fixées en début de jeu
- une unité "mineur" donnée en début de jeu

Chaque joueur pourra alors donner des ordres à 4 types d'items:
- à la base, pour construire une nouvelle unité d'un des types sous mentionnés
- à un mineur : déplacement, extraire, déposer, attaquer
- à une unité de combat (distance ou corps à corps) :  déplacement, attaquer

----

**Gestion des unités**

Chaque unité coûte un certain nombre d'unité de minerai.

Chaque unité a un temps de construction.

Chaque unité possède des caractéristiques:
- vitesse de déplacement
- portée d'attaque / minage
- nb d'attaque par tour
- vitesse de minage
- puissance d'attaque / de minage
- capacité de transport (nb d'unités de minerai)
- points de vie
- armure
- champ de vision

----

**Début de partie**

L'instance transmet aux joueurs des données génériques sur la configuration du jeu:
- caractéristiques des 3 types d'unités
- taille de la carte (?)

----

**Tour de jeu**

***Input***

L'instance transmet aux joueurs les données des éléments dans le champ de vision du joueur (au travers de ses structures et de ses unités).
L'instance transmet une liste de valeurs pour décrire chaque case visible. Pour chaque case visible, elle transmet son contenu:
- vide
- unité ou bâtiment(avec ses caractéristiques instanciées : type,armure, vie et propriétaire)
- Minerai (nombre restant à récolter)
- rocher (obstacle)


***Gestion des ordres***

Question ?
- un tir sur une autre unité est géré sur sa position initiale ou sa position finale (si l'unité ennemie a lancé un mouvement de deux cases, au bout des 2 cases elle est hors de portée, alors qu'elle était à portée initialement et au mouvement 1 également).
- si une unité a 3 de mouvements, et une 2e 1, la 2e s'arrête dans le chemin tracé par la 1ere, que se passe-t-il?

2 options:
- simple
	- on résout uniquement les états finaux
	- le tir est résolu sur l'unité en fin de déplacement
	- les collisions sont gérés sur la fin de déplacement uniquement
	- l'ordre des ordres passées à une unité n'a pas d'importance, on résout mouvement puis tir
- complexe
	- on découpe un tour en 100 unités
	- si une unité à 4 actions (2 mvts et 2 tirs), chaque action se tient dans une portion de tour (25,50,75 et 100)
	- chaque action est résolue dans le laps de temps lui correspondant, et on recherche chez l'ennemi son état dans cette fraction de tour.
	- l'ordre des ordres passés est important
	- en cas d'obstruction, que fait on des ordres suivants (notamment de déplacement)
	



----

**IHM**

L'interface joueur doit pouvoir:
- permettre de se créer un compte
- de se logguer
- de modifier ses informations personnelles
- de pouvoir voir la liste des joueurs
	- de pouvoir suivre un joueur
- de pouvoir ajouter des scripts (par upload, ou par saisie dans une IHM?)
- de pouvoir lancer une partie contre un joueur sélectionné
- de pouvoir visualiser le résultat de sa partie de son point de vue (?? choisir le point de vue, ou retirer le brouillard de guerre?)
	- temps réel ou temps accéléré, gestion de pause, possibilité de revenir à un tour précédent
	- visualiser les commandes transmises au serveur et les erreurs remontées par le serveur
- de pouvoir visualiser les parties d'autres joueurs (?)

----

**Serveur**

***Considérations générales***

Le serveur a pour but de:
- gérer une persistance d'information (joueurs, résultats, configuration, ....)
- fournir des informations à l'IHM
- lancer des matchs entre joueurs
- veiller à la stabilité et à la sécurité du système
- être en capacité d'exécuter du code externe dans différents langages

***Stabilité & Sécurité***

Le serveur va devoir exécuter du code dont il n'est pas le propriétaire.
Il est tout à fait entendable que des personnes tentent d'injecter du code malveillant, dans des buts de triche, ou tout simplement de malveillance.
Il est tout à fait possible que du code soit injecté, alors que sa bonne exécution n'ait pas été validée:
- Code ne compilant pas
- Code sans output
- Code avec des boucles infinies
- Code surconsommant CPU & mémoire

Le serveur aura besoin de gérer toutes ces problématiques de sécurité, de surveillance et de monitoring du code externe exécuté.




----

**Reflexions sur options avancées**

- capacité à détruire un obstacle ??? Comment?? certains types d'obstacles?
- recyclage d'unités détruites
- plus de diversités d'unités
	- unité d'exploration
	- unité de siège
- ouvrier avec un champ d'action plus large (construction de bâtiment, upgrade de bâtiment ou d'unités)
- caractéristiques "aléatoires" en début de partie
- taille non connue de la carte
- autres bâtiments 
	- permettant l'upgrade des unités (équilibrage investissement bâtiment vs avantage des upgrades)
	- Tour de vision
	- Tour de défense
	- Silo
- génération procédurale de cartes équilibrées
- gestion de point d'action par unité (dans un même tour, faire 3 mouvements, ou 2 mouvements et une attaque?)
- doit on prévoir un classement?
- peut on lancer une partie à 4?

