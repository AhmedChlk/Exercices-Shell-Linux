# Navigation dans le système de fichiers Linux

## Afficher le répertoire courant
Pour connaître le répertoire courant, on utilise la commande `pwd` (*print working directory*). Elle affiche le chemin absolu du dossier dans lequel on se trouve.

```bash
$ pwd
/home/utilisateur
```

Dans cet exemple, le terminal indique que le répertoire courant est `/home/utilisateur` (le dossier personnel de l'utilisateur).

## Lister le contenu d'un répertoire
Pour lister le contenu du répertoire courant, on utilise la commande `ls`. Sans argument, `ls` liste les fichiers et dossiers du répertoire dans lequel on se trouve.

```bash
$ ls
Bureau  Documents  Images  fichier.txt
```

Dans cet exemple, `ls` affiche trois dossiers (Bureau, Documents, Images) et un fichier (fichier.txt) présents dans le répertoire courant.

### Options utiles pour ls
- `ls -l` : Affiche une liste détaillée avec permissions, propriétaire, taille, date de modification, etc.
- `ls -a` : Affiche tous les fichiers, y compris les fichiers cachés (ceux dont le nom commence par un point).
- `ls -la` : Combine les deux options précédentes.

## Se déplacer dans l'arborescence

### Accéder au répertoire racine
Le répertoire racine du système s'appelle `/` (c'est la base de l'arborescence). La commande pour y accéder est :

```bash
$ cd /
```

Après cette commande, le répertoire courant devient la racine du système. Vous pouvez le vérifier avec `pwd`, qui devrait maintenant afficher simplement `/`.

Listez le contenu du répertoire racine avec `ls` pour voir les principaux dossiers système :

```bash
$ ls
bin  boot  dev  etc  home  lib  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
```

Ces dossiers constituent la structure standard d'un système Linux :
- `/home` : contient les dossiers des utilisateurs
- `/etc` : contient les fichiers de configuration
- `/bin` et `/sbin` : contiennent les programmes exécutables essentiels
- `/var` : contient les données variables comme les logs

### Revenir au répertoire personnel
Pour revenir dans votre répertoire personnel, plusieurs méthodes existent :

```bash
$ cd        # Sans argument, ramène au répertoire personnel
$ cd ~      # Le symbole ~ représente le répertoire personnel
$ cd $HOME  # La variable d'environnement HOME contient le chemin du répertoire personnel
```

### Naviguer dans la hiérarchie
Pour se déplacer dans un sous-répertoire, utilisez `cd` suivi du nom du dossier :

```bash
$ cd Documents
$ pwd
/home/utilisateur/Documents
```

Pour remonter d'un niveau dans l'arborescence (aller au dossier parent), utilisez `cd ..` :

```bash
$ cd ..
$ pwd
/home/utilisateur
```

## Astuces de navigation

### Retour au répertoire précédent
La commande `cd -` permet de revenir au dernier répertoire utilisé :

```bash
$ pwd
/home/utilisateur
$ cd /etc
$ pwd
/etc
$ cd -
$ pwd
/home/utilisateur
```

C'est particulièrement utile pour basculer rapidement entre deux répertoires.

### Chemins absolus vs relatifs
- **Chemins absolus** : commencent par `/` et sont relatifs à la racine du système
  ```bash
  $ cd /home/utilisateur/Documents
  ```
  
- **Chemins relatifs** : sont relatifs au répertoire courant
  ```bash
  $ cd Documents
  ```

### Autocomplétion avec la touche Tab

L'autocomplétion est une fonctionnalité puissante qui permet de :
- Gagner du temps en évitant de taper les noms complets
- Éviter les erreurs de frappe
- Explorer les possibilités disponibles

**Utilisation** :
1. Commencez à taper le début d'une commande ou d'un chemin
2. Appuyez sur la touche Tab
3. Si une seule complétion est possible, le terminal la complète automatiquement
4. Si plusieurs options sont disponibles, appuyez deux fois sur Tab pour voir la liste des possibilités