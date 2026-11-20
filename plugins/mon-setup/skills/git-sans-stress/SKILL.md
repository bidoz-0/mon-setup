---
name: git-sans-stress
description: Gère Git et GitHub à la place de l'utilisateur, qui débute. À utiliser dès qu'il parle de sauvegarder, envoyer sur GitHub, commit, push, branche, pull request (PR), fusionner (merge), conflit, revenir en arrière ou annuler une erreur, et à la fin d'une tâche de code.
---

# Git sans stress

L'utilisateur débute avec Git. Tu fais les manipulations à sa place et tu l'empêches de faire des bêtises.

## Toujours
- Commence par `git status` et `git branch` pour savoir où on en est.
- Explique chaque action en **une ligne**, sans jargon. Si un mot technique est inévitable, explique-le entre parenthèses la première fois.
- Termine par un résumé de 1 à 2 lignes : ce qui est sauvegardé, sur quelle branche, et le lien de la PR s'il y en a une.

## Branches
- Nouvelle fonctionnalité : crée une branche `feat/nom-court`. Correctif : `fix/nom-court`.
- Avant de commiter directement sur `main`, demande une fois si c'est voulu.

## Commits
- Messages en français, clairs, au présent : « Ajoute le tri par date dans la bibliothèque ».
- Un commit par changement logique, pas un commit fourre-tout.
- Avant chaque commit, vérifie qu'aucun secret n'est inclus (clés, tokens, mots de passe, .env). Si oui, retire-le, complète le `.gitignore` et préviens l'utilisateur.
- Après le commit, fais le push, sauf si l'utilisateur a dit non.

## Pull requests
- Quand une fonctionnalité est terminée, propose une PR avec : ce qui change, pourquoi, et comment tester.
- **Fusionner dans `main` : toujours demander confirmation avant.**

## Interdit sans accord explicite
`push --force`, `reset --hard`, `clean`, `rebase` sur une branche déjà poussée, suppression de branche, réécriture de l'historique.
Si l'une de ces actions semble nécessaire, explique le risque en une phrase et demande.

## Annuler une erreur
- Préfère `git revert` (annule proprement sans effacer l'historique) à `reset`.
- Avant toute opération risquée, crée une branche de secours `secours/AAAA-MM-JJ`.

## Conflits
- Dis quels fichiers sont en conflit et ce que chaque version fait, en clair.
- Propose une résolution. Si le choix n'est pas évident, demande avant de trancher.
