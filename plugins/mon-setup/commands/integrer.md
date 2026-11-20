---
description: Intégrer un projet existant au setup (CLAUDE.md, ARCHITECTURE.md, vérifications de base)
---

Projet existant. Ne modifie PAS le code de l'appli, seulement la documentation.

1. **Analyse** : fais explorer le projet par l'agent explorateur (stack, point d'entrée, structure des dossiers, comment le lancer).
2. **CLAUDE.md** : crée-le ou complète-le à partir du modèle ci-dessous, rempli avec ce que tu as trouvé.
3. **ARCHITECTURE.md** : une page maximum, qui décrit le projet tel qu'il est (pas tel qu'il devrait être).
4. **Sécurité** : cherche les secrets (clés API, tokens, mots de passe) dans le code et dans l'historique Git, et vérifie le .gitignore. Si tu en trouves, préviens-moi et explique quoi faire. Ne réécris jamais l'historique sans mon accord.
5. **Problèmes de structure** : liste les 3 plus gros (fichiers énormes, logique dans main, code dupliqué…), avec l'effort estimé pour chacun. Ne corrige rien.
6. **Sauvegarde** avec le skill git-sans-stress (commit + push des fichiers de doc).
7. **Fin** : résumé en 5 lignes maximum.

---
Modèle de CLAUDE.md :
```markdown
# [Nom du projet]

## C'est quoi
[1 à 2 phrases]

## Stack
[langage, framework, où sont les données]

## Lancer / tester
[commandes]

## Règles
- Réponds en français, court, droit au but.
- L'utilisateur débute en dev : explique les choix importants en une phrase, sans faire de cours.
- Solution la plus simple qui marche. Ne change jamais de techno ni d'architecture sans le proposer d'abord.
- Jamais de secret (clé API, token, mot de passe) dans le code ou le repo : variables d'environnement + .gitignore.
- Pas de fausses données ni de TODO caché : si quelque chose n'est pas fait ou pas faisable, dis-le.
- Préviens avant toute action risquée (suppression, gros refactor, migration).
- Structure du projet : voir ARCHITECTURE.md. Où on en est : dernier fichier de docs/handoff/.

## Structure du code
- Le point d'entrée (main) ne fait que lancer l'appli : aucune logique dedans.
- Séparer interface, logique, données et services externes (API).
- Un fichier = un rôle. Au-delà de ~300 lignes, découper.
- Dossiers rangés par fonctionnalité, pas par type de fichier.
- Configuration et secrets à part, jamais en dur dans le code.
- Avant de créer un fichier, vérifier s'il existe déjà un endroit logique pour ce code.
```
