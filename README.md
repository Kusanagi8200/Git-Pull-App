# Script de Mise à Jour des Dépôts Git

Ce script bash est conçu pour mettre à jour automatiquement une liste de dépôts Git locaux. Il utilise des couleurs pour mettre en évidence les différentes étapes et les résultats de ces opérations.

## Fonctionnement

Le script parcourt une liste de chemins vers des dépôts Git locaux. Pour chaque dépôt, il tente d'exécuter `git pull` pour le mettre à jour. Si un dépôt contient des modifications non commitées, le script affiche un avertissement et passe au dépôt suivant.

## Mise en Forme du Texte

Des variables de couleur sont définies pour améliorer la lisibilité des messages :

- `HIGHLIGHT` : Fond orange avec texte noir en gras.
- `ERROR` : Fond rouge avec texte blanc en gras.
- `SUCCESS` : Fond pourpre avec texte blanc en gras.
- `NC` (No Color) : Réinitialise la couleur à la normale.

## Liste des Dépôts

Les dépôts sont définis dans un tableau `REPOS`, avec chaque chemin vers un dépôt sur une ligne distincte.

## Boucle de Mise à Jour

Le script itère sur chaque dépôt :

1. Il se déplace dans le répertoire du dépôt (`cd`).
2. Vérifie s'il y a des modifications non commitées.
   - Si oui, affiche un message d'erreur et continue avec le prochain dépôt.
   - Sinon, exécute `git pull` pour mettre à jour le dépôt.

## Exemple de Sortie

- Les messages en orange indiquent le début de la mise à jour d'un dépôt.
- Les messages en rouge indiquent la présence de changements non commités.
- Le message final en pourpre indique que la mise à jour de tous les dépôts est terminée.

## Utilisation

Pour utiliser ce script, assurez-vous qu'il est exécutable :

```bash
chmod +x nom_du_script.sh
