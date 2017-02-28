
Thradrukohat donne au joueur pour but de constuire une intelligence artifcielle dans le cadre d'un jeu de stratégie type starcraft.
Ce jeu contient une version mono joueur lié à un mode tutoriel permettant de construire une IA en suivant des niveaux de complexité de plus en plus important.
Ce jeu contient une version multijoueur permettant de hoster une partie avec les programmes de plusieurs joueurs.

Ce jeu devra faire tourner un nombre non limité de langage de programmation, tant que ceux ci sont capable de lire un input console, et d'envoyer un input console.

Les ordres seront exécutés pour un tour de jeu. Un tour de jeu sera exécuté toutes les 100 ms. Si un parcours de boucle d'un joueur se termine au bout de 150ms et qu'il ne transmet ces ordres qu'en fin de boucle, ces ordres seront exécutés en tour 2.
Si jamais les ordres sont envoyés au fur et à mesure, les ordres seront exécutés dans le tour, de leur émission.

Les premiers concepts développés seront :
- une base centrale construite au démarrage du jeu
- des localisations de minerai fixées en début de jeu
- une carte fixée en début de jeu
- une unité "mineur" donné en début de jeu

Chaque joueur pourra alors donner des ordres à 4 types d'items:
- à la base, pour construire une nouvelle unité d'un des 3 types sous mentionnés
- à un mineur : déplacement, extraire, déposer, attaquer
- à une unité de combat (distance ou corps à corps) :  déplacement, attaquer


Chaque unité coute un certain nombre d'unité de minerai.
Chaque unité à un temps de construction.
Chaque unité possède 3 caractéristiques:

