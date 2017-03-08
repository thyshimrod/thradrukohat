
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

L'instance transmet aux joueurs les données des éléments dans le champ de vision du joueur (au travers de ses structures et de ses unités).
L'instance transmet une liste de valeurs pour décrire chaque case visible. Pour chaque case visible, elle transmet son contenu:
- vide
- unité ou bâtiment(avec ses caractéristiques instanciées : type,armure, vie et propriétaire)
- Minerai (nombre restant à récolter)
- rocher (obstacle)


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

