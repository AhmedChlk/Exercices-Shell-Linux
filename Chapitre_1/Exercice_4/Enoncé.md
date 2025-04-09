# Exercice 4 : Redirection des flux d'entrée/sortie

## Contexte
Vous voulez sauvegarder le résultat de certaines commandes dans des fichiers ou utiliser le contenu d'un fichier comme entrée d'une commande. De plus, vous devez gérer les messages d'erreur séparément des résultats normaux. Cet exercice vous apprend à rediriger la sortie standard, la sortie d'erreur et l'entrée standard.

## Objectif
Savoir utiliser `>` pour rediriger la sortie d'une commande vers un fichier (et `>>` pour ajouter sans écraser), `2>` pour rediriger les erreurs, et `<` pour rediriger un fichier en entrée d'une commande. Comprendre la différence entre la sortie standard (stdout) et la sortie d'erreur (stderr).

## Consignes

1. À l'aide d'une seule commande, listez le contenu d'un répertoire (au choix) et enregistrez ce listing dans un fichier nommé `listing.txt`. Vérifiez que rien ne s'affiche à l'écran et que le fichier contient bien le résultat voulu.

2. Relancez la même commande de listing mais en ajoutant son résultat **à la suite** du fichier `listing.txt` au lieu de l'écraser.

3. Utilisez une commande permettant de compter le nombre de lignes dans le fichier `listing.txt` en redirigeant le contenu du fichier en entrée de cette commande (plutôt qu'en spécifiant le fichier en argument).

4. Exécutez une commande volontairement incorrecte (par exemple, lister un dossier inexistant) en redirigeant son message d'erreur vers un fichier `erreur.txt`. Vérifiez que rien ne s'affiche dans le terminal et que le fichier contient bien le message d'erreur.

5. (Optionnel) Pour tester la redirection de l'erreur et de la sortie simultanément, essayez une commande produisant à la fois une sortie normale et une erreur, en redirigeant ces deux flux vers des fichiers différents.

## Compétences développées
- Redirection de la sortie standard vers un fichier avec `>`
- Ajout à un fichier existant avec `>>`
- Redirection de l'entrée standard depuis un fichier avec `<`
- Redirection des erreurs avec `2>`
- Distinction entre la sortie standard (stdout) et la sortie d'erreur (stderr)
- Combinaison de plusieurs redirections dans une même commande

## Commandes et opérateurs utilisés
- `>` : Redirige la sortie standard vers un fichier (écrase le contenu existant)
- `>>` : Redirige la sortie standard vers un fichier (ajoute au contenu existant)
- `<` : Redirige l'entrée standard depuis un fichier
- `2>` : Redirige la sortie d'erreur vers un fichier
- `&>` : Redirige à la fois la sortie standard et la sortie d'erreur
- `ls` : Liste le contenu d'un répertoire
- `wc` : Compte les lignes, mots et caractères

## Conseils
- La sortie standard (stdout) correspond au canal 1
- La sortie d'erreur (stderr) correspond au canal 2
- Vous pouvez combiner plusieurs redirections dans une même commande
- Pour rediriger à la fois stdout et stderr vers le même fichier, utilisez `command > fichier 2>&1`
- Pour ignorer complètement une sortie, redirigez-la vers `/dev/null`
