# Exercice 2 : Gestion de fichiers et de dossiers

## Contexte
Vous souhaitez organiser des fichiers pour un projet. Pour cela, vous devez créer une structure de dossiers, y ajouter des fichiers, puis éventuellement les renommer, les copier ou les supprimer. Cet exercice se déroule dans votre répertoire d'exercices (par exemple, créez un dossier `ExercicesTerminal` dans votre home pour y travailler).

## Objectif
Apprendre à créer des répertoires et fichiers, copier et déplacer des fichiers, ainsi que supprimer des éléments. Vous utiliserez pour cela `mkdir` (créer des dossiers), `touch` (créer des fichiers vides), `cp` (copier), `mv` (déplacer ou renommer) et `rm` (supprimer).

## Consignes

1. Dans votre répertoire d'exercices, créez un nouveau dossier nommé `MonProjet`.

2. À l'intérieur de `MonProjet`, créez un sous-dossier nommé `Notes`.

3. Dans `MonProjet`, créez un fichier texte vide nommé `todo.txt`.

4. Vérifiez la présence du fichier en listant le contenu du dossier `MonProjet`.

5. Écrivez du contenu dans `todo.txt` – par exemple quelques tâches à faire (vous pouvez éditer le fichier avec un éditeur de texte de votre choix, ou utiliser une redirection comme vu plus tard).

6. Faites une copie du fichier `todo.txt` et nommez-la `todo_backup.txt` (copie de sauvegarde).

7. Renommez le fichier de sauvegarde `todo_backup.txt` en `archive.txt`.

8. Déplacez le fichier `archive.txt` dans le sous-dossier `Notes`.

9. Supprimez le fichier `archive.txt` (qui se trouve désormais dans `Notes`).

10. Supprimez le dossier `Notes` (qui est devenu vide après la suppression du fichier qu'il contenait).

## Compétences développées
- Création de structures de répertoires avec `mkdir`
- Création de fichiers avec `touch`
- Copie de fichiers avec `cp`
- Déplacement et renommage de fichiers avec `mv`
- Suppression de fichiers et répertoires avec `rm` et `rmdir`
- Vérification des opérations par observation du contenu des répertoires

## Commandes utilisées
- `mkdir` : Make Directory (créer un dossier)
- `touch` : Créer un fichier vide ou mettre à jour la date de modification
- `cp` : Copy (copier des fichiers ou répertoires)
- `mv` : Move (déplacer ou renommer des fichiers ou répertoires)
- `rm` : Remove (supprimer des fichiers ou répertoires)
- `rmdir` : Remove Directory (supprimer un répertoire vide)
- `ls` : List (lister le contenu d'un répertoire)

## Conseils
- Utilisez `mkdir -p` pour créer des structures de répertoires imbriqués en une seule commande
- Pour éditer un fichier texte, vous pouvez utiliser `nano`, `vim`, ou `gedit` selon vos préférences
- Pour supprimer un répertoire non vide, utilisez `rm -r` (option récursive) avec précaution
- Vérifiez régulièrement le résultat de vos opérations avec `ls` ou `ls -la`