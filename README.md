
Thradrukohat donne au joueur pour but de constuire une intelligence artifcielle dans le cadre d'un jeu de strat�gie type starcraft.
Ce jeu contient une version mono joueur li� � un mode tutoriel permettant de construire une IA en suivant des niveaux de complexit� de plus en plus important.
Ce jeu contient une version multijoueur permettant de hoster une partie avec les programmes de plusieurs joueurs.

Ce jeu devra faire tourner un nombre non limit� de langage de programmation, tant que ceux ci sont capable de lire un input console, et d'envoyer un input console.

Les ordres seront ex�cut�s pour un tour de jeu. Un tour de jeu sera ex�cut� toutes les 100 ms. Si un parcours de boucle d'un joueur se termine au bout de 150ms et qu'il ne transmet ces ordres qu'en fin de boucle, ces ordres seront ex�cut�s en tour 2.
Si jamais les ordres sont envoy�s au fur et � mesure, les ordres seront ex�cut�s dans le tour, de leur �mission.

Les premiers concepts d�velopp�s seront :
- une base centrale construite au d�marrage du jeu
- des localisations de minerai fix�es en d�but de jeu
- une carte fix�e en d�but de jeu
- une unit� "mineur" donn� en d�but de jeu

Chaque joueur pourra alors donner des ordres � 4 types d'items:
- � la base, pour construire une nouvelle unit� d'un des 3 types sous mentionn�s
- � un mineur : d�placement, extraire, d�poser, attaquer
- � une unit� de combat (distance ou corps � corps) :  d�placement, attaquer


Chaque unit� coute un certain nombre d'unit� de minerai.
Chaque unit� � un temps de construction.
Chaque unit� poss�de 3 caract�ristiques:

