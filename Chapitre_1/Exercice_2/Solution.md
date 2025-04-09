# Solution : Gestion de fichiers et de dossiers

Pour créer un nouveau dossier, on utilise la commande `mkdir` (make directory). Positionnez-vous d'abord dans votre répertoire d'exercices :

```bash
$ cd ~/ExercicesTerminal
$ mkdir MonProjet
```

Cette commande crée un répertoire nommé `MonProjet` dans le répertoire courant. Vous pouvez vérifier sa création avec `ls`.

Pour créer un sous-dossier `Notes` à l'intérieur de `MonProjet`, utilisez `mkdir` en précisant le chemin du dossier parent :

```bash
$ mkdir MonProjet/Notes
```

Ceci crée le dossier `Notes` à l'intérieur de `MonProjet`. Désormais, `MonProjet` contient un sous-répertoire `Notes`.

Pour créer un fichier vide, utilisez la commande `touch`. Placez-vous dans le dossier `MonProjet` puis exécutez :

```bash
$ cd MonProjet
$ touch todo.txt
```

La commande `touch` crée un nouveau fichier s'il n'existe pas. Ici, elle crée un fichier texte nommé `todo.txt` dans `MonProjet`.

Utilisez `ls` pour lister le contenu de `MonProjet` et vérifier que le fichier a bien été créé :

```bash
$ ls
Notes  todo.txt
```

Vous devriez voir le sous-dossier `Notes` et le fichier `todo.txt`. À ce stade, `todo.txt` est vide.

Ouvrez `todo.txt` dans un éditeur de texte et ajoutez quelques lignes de tâches à accomplir :

```bash
$ nano todo.txt
```

Par exemple, le fichier pourrait contenir :
```
- Préparer la présentation du projet X
- Envoyer le rapport à l'équipe
- Planifier la réunion de la semaine prochaine
```



Pour créer une copie du fichier `todo.txt`, on utilise la commande `cp` (copy) :

```bash
$ cp todo.txt todo_backup.txt
```

Cette commande copie le contenu de `todo.txt` vers un nouveau fichier `todo_backup.txt` dans le même dossier.

Pour renommer un fichier, on utilise la commande `mv` (move) :

```bash
$ mv todo_backup.txt archive.txt
```

Après cette commande, le dossier `MonProjet` contient `todo.txt` et `archive.txt` (au lieu de `todo_backup.txt`).

Pour déplacer le fichier `archive.txt` dans le sous-dossier `Notes`, on utilise encore `mv` :

```bash
$ mv archive.txt Notes/
```

Cette commande déplace `archive.txt` dans le dossier `Notes`. Vous pouvez vérifier en listant `MonProjet` puis `MonProjet/Notes` :

```bash
$ ls 
Notes  todo.txt
$ ls Notes
archive.txt
```

Pour supprimer un fichier, utilisez la commande `rm` (remove) :

```bash
$ rm Notes/archive.txt
```

Cette action supprime définitivement le fichier `archive.txt`. Attention : `rm` ne passe pas par la corbeille, le fichier est donc irrécupérable directement.

Maintenant, supprimez le dossier vide `Notes`. On peut utiliser `rmdir` pour supprimer un répertoire vide :

```bash
$ rmdir Notes
```

Cette commande ne fonctionne que si le dossier est vide. Dans notre cas, après avoir supprimé `archive.txt`, `Notes` est vide et `rmdir` le supprime.

Après ces étapes, vous devriez avoir uniquement le fichier `todo.txt` dans le dossier `MonProjet`. Si vous n'avez plus besoin de ces éléments, vous pouvez aussi les supprimer :

```bash
$ rm todo.txt
$ cd ..
$ rmdir MonProjet
```

## Astuce
- Pour supprimer un dossier non vide en une seule commande, utilisez `rm -r NomDossier` (option récursive), mais c'est dangereux car tout le contenu du dossier est supprimé sans confirmation. Il est préférable de s'assurer manuellement qu'on ne supprime rien d'important.

- Vous pouvez aussi ajouter du contenu sans ouvrir d'éditeur en utilisant la redirection :

```bash
$ echo "- Préparer la présentation du projet X" > todo.txt
```