
Thradrukohat donne au joueur pour but de constuire une intelligence artifcielle dans le cadre d'un jeu de strat�gie type starcraft.
Le joueur proc�dera � l'�criture de scripts permettant de g�rer le comportement de chaque type d'unit�. Il pourra l'�crire dans le langage de son choix, tant qu'il est support� par le jeu.
Ce jeu contient une version mono joueur li� � un mode tutoriel permettant de construire une IA en suivant des niveaux de complexit� de plus en plus important.
Ce jeu contient une version multijoueur permettant de hoster une partie avec les programmes de plusieurs joueurs.

Ce jeu devra faire tourner un nombre non limit� de langage de programmation, tant que ceux ci sont capable de lire un input console, et d'envoyer un input console.

Les ordres seront ex�cut�s pour un tour de jeu. Un tour de jeu par exemple, est ex�cut� toutes les 100 ms. Si un parcours de boucle d'un joueur se termine au bout de 150ms et qu'il ne transmet ces ordres qu'en fin de boucle, ces ordres seront ex�cut�s en tour 2.
Si jamais les ordres sont envoy�s au fur et � mesure, les ordres seront ex�cut�s dans le tour, de leur �mission.

Les premiers concepts d�velopp�s seront :
- une carte fix�e en d�but de jeu
- une base centrale construite au d�marrage du jeu
- des localisations de minerai fix�es en d�but de jeu
- une unit� "mineur" donn�e en d�but de jeu

Chaque joueur pourra alors donner des ordres � 4 types d'items:
- � la base, pour construire une nouvelle unit� d'un des types sous mentionn�s
- � un mineur : d�placement, extraire, d�poser, attaquer
- � une unit� de combat (distance ou corps � corps) :  d�placement, attaquer

----

**Gestion des unit�s**

Chaque unit� co�te un certain nombre d'unit� de minerai.

Chaque unit� a un temps de construction.

Chaque unit� poss�de des caract�ristiques:
- vitesse de d�placement
- port�e d'attaque / minage
- puissance d'attaque / de minage
- capacit� de transport (nb d'unit�s de minerai)
- points de vie
- armure
- champ de vision

----

**D�but de partie**

L'instance transmet aux joueurs des donn�es g�n�riques sur la configuration du jeu:
- caract�ristiques des 3 types d'unit�s
- taille de la carte (?)

----

**Tour de jeu**

L'instance transmet aux joueurs les donn�es des �l�ments dans le champ de vision du joueur (au travers de ses structures et de ses unit�s).
L'instance transmet une liste de valeurs pour d�crire chaque case visible. Pour chaque case visible, elle transmet son contenu:
- vide
- unit� ou b�timent(avec ses caract�ristiques instanci�es : type,armure, vie et propri�taire)
- Minerai (nombre restant � r�colter)
- rocher (obstacle)


----

**IHM**

L'interface joueur doit pouvoir:
- permettre de se cr�er un compte
- de se logguer
- de modifier ses informations personnelles
- de pouvoir voir la liste des joueurs
	- de pouvoir suivre un joueur
- de pouvoir ajouter des scripts (par upload, ou par saisie dans une IHM?)
- de pouvoir lancer une partie contre un joueur s�lectionn�
- de pouvoir visualiser le r�sultat de sa partie de son point de vue (?? choisir le point de vue, ou retirer le brouillard de guerre?)
	- temps r�el ou temps acc�l�r�, gestion de pause, possibilit� de revenir � un tour pr�c�dent
	- visualiser les commandes transmises au serveur et les erreurs remont�es par le serveur
- de pouvoir visualiser les parties d'autres joueurs (?)


----

**Reflexions sur options avanc�es**

- capacit� � d�truire un obstacle ??? Comment?? certains types d'obstacles?
- recyclage d'unit�s d�truites
- plus de diversit�s d'unit�s
	- unit� d'exploration
	- unit� de si�ge
- ouvrier avec un champ d'action plus large (construction de b�timent, upgrade de b�timent ou d'unit�s)
- caract�ristiques "al�atoires" en d�but de partie
- taille non connue de la carte
- autres b�timents 
	- permettant l'upgrade des unit�s (�quilibrage investissement b�timent vs avantage des upgrades)
	- Tour de vision
	- Tour de d�fense
	- Silo
- g�n�ration proc�durale de cartes �quilibr�es
- gestion de point d'action par unit� (dans un m�me tour, faire 3 mouvements, ou 2 mouvements et une attaque?)
- doit on pr�voir un classement?
- peut on lancer une partie � 4?

