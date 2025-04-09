# Solution : Affichage du contenu des fichiers

## 1. Création d'un fichier d'exemple

Commençons par créer un fichier texte avec suffisamment de contenu pour tester les différentes commandes d'affichage :

```bash
$ touch notes.txt
```

Pour ajouter du contenu à ce fichier, vous pouvez utiliser un éditeur de texte comme `nano` :

```bash
$ nano notes.txt
```

Ajoutez plusieurs lignes de texte, par exemple :

```
Réunion du 15 avril :
- Présentation du nouveau projet
- Planification des tâches
- Distribution des rôles

Tâches à faire :
1. Rédiger le cahier des charges
2. Contacter les fournisseurs
3. Établir un planning prévisionnel
4. Préparer le budget
5. Organiser la réunion de suivi
6. Faire le point sur l'avancement
7. Mettre à jour la documentation
8. Résoudre les problèmes techniques
9. Tester la solution
10. Présenter les résultats

Notes importantes :
* N'oubliez pas la réunion hebdomadaire
* Les rapports doivent être remis avant vendredi
* Le projet doit être terminé avant la fin du mois
* Prévoyez une marge de sécurité dans vos estimations
* La documentation doit être claire et précise
* Assurez-vous que tous les tests sont passés
* Prévenez immédiatement en cas de retard

Contacts :
- Marie : marie@exemple.com
- Thomas : thomas@exemple.com
- Julie : julie@exemple.com
- Pierre : pierre@exemple.com
```

Sauvegardez le fichier et quittez l'éditeur. Si vous avez déjà un fichier `todo.txt` de l'exercice précédent, vous pouvez simplement le copier :

```bash
$ cp todo.txt notes.txt
```

Dans ce cas, vous pouvez ajouter plus de contenu pour le rendre plus volumineux :


## 2. Affichage complet du fichier

Pour afficher l'intégralité du fichier `notes.txt` dans le terminal, utilisez la commande `cat` (concatenate) :

```bash
$ cat notes.txt
```

Cette commande affiche directement tout le contenu du fichier dans le terminal. C'est pratique pour les fichiers courts, mais pour les fichiers longs, tout le texte défile rapidement et vous ne voyez que la fin.

## 3. Affichage page par page

Pour parcourir le fichier page par page, utilisez la commande `less` :

```bash
$ less notes.txt
```

`less` est un pager qui permet de naviguer dans le fichier :
- Utilisez les flèches ↑ et ↓ pour monter ou descendre d'une ligne
- Utilisez Page Up et Page Down (ou Espace) pour avancer ou reculer d'une page
- Utilisez la touche `q` pour quitter et revenir au terminal
- Utilisez `/` suivi d'un mot pour rechercher ce mot dans le fichier

L'avantage de `less` est qu'il ne charge pas tout le fichier en mémoire, ce qui le rend efficace pour les fichiers volumineux.

## 4. Commande alternative pour la pagination

Une alternative à `less` est la commande `more` :

```bash
$ more notes.txt
```

`more` est un pager plus ancien et plus simple que `less` :
- Appuyez sur Espace pour afficher la page suivante
- Appuyez sur Entrée pour avancer d'une ligne
- Appuyez sur `q` pour quitter

La principale différence est que `more` ne permet que de défiler vers l'avant, alors que `less` permet aussi de revenir en arrière.

## Autres commandes utiles

Si vous souhaitez voir uniquement les premières lignes d'un fichier, utilisez `head` :

```bash
$ head notes.txt       # Affiche les 10 premières lignes par défaut
$ head -n 5 notes.txt  # Affiche les 5 premières lignes
```

Pour voir les dernières lignes d'un fichier, utilisez `tail` :

```bash
$ tail notes.txt       # Affiche les 10 dernières lignes par défaut
$ tail -n 3 notes.txt  # Affiche les 3 dernières lignes
```

Ces commandes sont particulièrement utiles pour examiner rapidement le début ou la fin d'un fichier volumineux comme un fichier journal (log).

## Astuce

Pour les fichiers très longs ou qui changent en temps réel (comme les logs), vous pouvez utiliser `tail -f` pour suivre les ajouts en temps réel :

```bash
$ tail -f /var/log/syslog  # Exemple avec un fichier de log système
```

Cela affichera les dernières lignes du fichier et continuera à afficher les nouvelles lignes à mesure qu'elles sont ajoutées. Utilisez Ctrl+C pour arrêter.