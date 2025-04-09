# Exercice 3 : Affichage du contenu des fichiers

## Contexte
Vous avez un fichier texte contenant des informations (par exemple une liste de notes ou un extrait de log) et vous souhaitez le consulter rapidement en ligne de commande, sans passer par un éditeur graphique. Cet exercice vous fait pratiquer les commandes permettant d'afficher le contenu d'un fichier dans le terminal, y compris pour les fichiers longs.

## Objectif
Savoir afficher le contenu d'un fichier texte entier avec `cat`, ou page par page avec un pager comme `less` ou `more`. Comprendre quand utiliser l'une ou l'autre de ces commandes.

## Consignes

1. Si vous n'avez pas de fichier texte d'exemple, créez-en un nommé `notes.txt` et ajoutez-y du contenu. Par exemple, vous pouvez reprendre le fichier `todo.txt` de l'exercice précédent, ou créer un fichier contenant quelques lignes de texte libre (plus d'une vingtaine de lignes pour tester le défilement).

2. Affichez l'intégralité du fichier `notes.txt` dans le terminal à l'aide d'une seule commande.

3. Utilisez une commande permettant de parcourir le fichier `notes.txt` page par page (ou ligne par ligne) plutôt que de tout afficher d'un coup. Assurez-vous de savoir faire défiler le contenu et quitter cette commande.

4. (Optionnel) Essayez une commande alternative pour la pagination et notez la différence de comportement, s'il y en a une.

## Compétences développées
- Affichage direct du contenu d'un fichier avec `cat`
- Navigation dans un fichier avec des pagers comme `less` et `more`
- Choix de la méthode appropriée selon la taille du fichier

## Commandes utilisées
- `cat` : Affiche le contenu complet d'un fichier
- `less` : Permet de parcourir un fichier page par page avec de nombreuses fonctionnalités
- `more` : Affiche le contenu d'un fichier page par page (version plus simple)
- `head` : Affiche les premières lignes d'un fichier
- `tail` : Affiche les dernières lignes d'un fichier

## Conseils
- Utilisez `cat` pour les fichiers courts dont vous voulez voir rapidement tout le contenu
- Préférez `less` pour les fichiers volumineux
- Dans `less`, utilisez les flèches ou Page Up/Down pour naviguer, et `q` pour quitter
- `head` et `tail` sont utiles pour voir seulement le début ou la fin d'un fichier long