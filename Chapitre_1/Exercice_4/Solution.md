# Solution : Redirection dans le Terminal

Pour manipuler efficacement les flux d'entrée et de sortie dans le terminal, on utilise des opérateurs de redirection. Cet exercice explore comment rediriger la sortie standard vers un fichier, ajouter à un fichier existant, et rediriger l'entrée standard.

## Redirection de la sortie standard (>)

Pour rediriger la sortie d'une commande vers un fichier, on utilise le symbole `>` :

```bash
$ ls /etc > listing.txt
```

Cette commande capture la liste des fichiers du répertoire `/etc` et l'écrit dans `listing.txt`. Rien n'est affiché dans le terminal car toute la sortie est redirigée vers le fichier. Si `listing.txt` existe déjà, son contenu est écrasé.

Pour vérifier le contenu du fichier créé :

```bash
$ cat listing.txt
acpi
adduser.conf
aliases
apt
bash.bashrc
...
```

## Ajout à un fichier existant (>>)

Pour ajouter le résultat d'une commande à la fin d'un fichier sans écraser son contenu, on utilise `>>` :

```bash
$ ls /bin >> listing.txt
```

Cette commande ajoute la liste des fichiers de `/bin` à la suite du contenu de `listing.txt`. Le fichier contient maintenant les listes de `/etc` suivies de celles de `/bin`.

Pour séparer visuellement les sections, on peut ajouter un en-tête :

```bash
$ echo "---- Listing de /bin ----" >> listing.txt
$ ls /bin >> listing.txt
```

## Redirection de l'entrée standard (<)

La redirection d'entrée permet de fournir le contenu d'un fichier comme entrée à une commande :

```bash
$ wc -l < listing.txt
172
```

Cette commande compte les lignes du fichier `listing.txt`. Contrairement à `wc -l listing.txt`, l'utilisation de `<` ne fait pas apparaître le nom du fichier dans la sortie, seulement le nombre de lignes.

## Redirection des erreurs (2>)

Les messages d'erreur (stderr) sont normalement affichés même si la sortie standard est redirigée. Pour rediriger aussi les erreurs, on utilise `2>` :

```bash
$ ls /dossier/introuvable 2> erreur.txt
```

Cette commande tente de lister un répertoire inexistant. Au lieu d'afficher le message d'erreur dans le terminal, il est écrit dans `erreur.txt` :

```bash
$ cat erreur.txt
ls: impossible d'accéder à '/dossier/introuvable': Aucun fichier ou dossier de ce type
```

## Combinaison des redirections

On peut combiner plusieurs redirections dans une même commande :

```bash
$ (ls /etc; ls /dossier/introuvable) > sortie.txt 2> erreur.txt
```

Cette commande groupe deux instructions : la première produit une sortie normale écrite dans `sortie.txt`, la seconde génère une erreur écrite dans `erreur.txt`.

## Redirection combinée (&>)

Pour rediriger à la fois la sortie standard et les erreurs vers un même fichier :

```bash
$ commande &> tout.txt
```

Cette syntaxe capture tous les messages (normaux et erreurs) dans le fichier `tout.txt`.

## En résumé

- `>` : Redirige la sortie standard (écrase le fichier de destination)
- `>>` : Redirige la sortie standard (ajoute à la fin du fichier)
- `<` : Fournit un fichier comme entrée standard
- `2>` : Redirige les erreurs
- Combinaisons possibles : `commande > fichier 2> erreurs.txt`

Ces opérateurs sont essentiels pour construire des pipelines complexes et automatiser des tâches dans le terminal.

## Approfondissement : Concepts et Détails des Redirections

### A. Les Descripteurs de Fichiers
* **Définition des descripteurs :** Sous Unix/Linux, chaque processus possède des descripteurs de fichiers qui représentent les canaux de communication :
   * **0** : Entrée standard (stdin)
   * **1** : Sortie standard (stdout)
   * **2** : Sortie d'erreur (stderr)
* **Utilisation :** En redirigeant avec `>`, vous manipulez le descripteur 1. Avec `2>`, c'est le descripteur 2 qui est détourné vers un fichier.

### B. Redirection de la Sortie Standard et de l'Entrée
* **Sortie standard (**`>`) : Lorsque vous utilisez `>`, la commande envoie son résultat « normalement » au terminal mais, en redirigeant, le texte est envoyé dans le fichier spécifié.
* **Ajout (**`>>`) : Utilisez `>>` pour éviter d'écraser les données existantes et simplement concaténer de nouvelles sorties à la fin du fichier.
* **Entrée standard (**`<`) : Cette redirection permet à une commande de lire les données provenant d'un fichier au lieu de lire le clavier. L'avantage, comme pour `wc -l`, est de travailler sur le contenu du fichier sans que le nom ne soit affiché dans le résultat.

### C. Redirection des Erreurs (2>)
* **Pourquoi rediriger les erreurs ?** Dans la gestion des scripts et l'automatisation, il est crucial de séparer le flux d'erreur du flux normal pour analyser les erreurs indépendamment des résultats valides.
* **Fonctionnement :** L'utilisation de `2>` garantit que le message d'erreur est écrit dans un fichier séparé, ce qui peut être très utile pour déboguer ou maintenir une trace des anomalies lors de l'exécution d'un script.

## Astuces

- Pour rediriger les erreurs vers la sortie standard (pour les traiter ensemble), utilisez la syntaxe `2>&1` :
  ```bash
  $ ls /dossier/introuvable > resultat.txt 2>&1
  ```

- Pour ignorer complètement une sortie (la jeter), redirigez-la vers `/dev/null` :
  ```bash
  $ ls -la > /dev/null  # Ignore la sortie standard
  $ ls -la 2> /dev/null  # Ignore les erreurs
  ```

- Pour voir le résultat d'une commande à l'écran tout en l'enregistrant dans un fichier, utilisez la commande `tee` :
  ```bash
  $ ls /etc | tee listing.txt
  ```

- Le symbole `|` (pipe) est différent des redirections mais complémentaire - il permet d'envoyer la sortie d'une commande vers l'entrée d'une autre :
  ```bash
  $ ls /etc | grep conf
  ```

- Pour éviter d'écraser accidentellement vos fichiers avec `>`, vous pouvez activer l'option `noclobber` dans votre terminal :
  ```bash
  $ set -o noclobber
  ```
  Ensuite, pour forcer l'écrasement si nécessaire, utilisez `>|` au lieu de `>`.