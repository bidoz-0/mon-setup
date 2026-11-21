---
description: Démarre un nouveau projet ou une grosse fonctionnalité (cadrage, architecture, plan, fichiers de base)
argument-hint: [idée du projet ou de la fonctionnalité]
---

L'utilisateur veut démarrer : $ARGUMENTS
(Si c'est vide, demande-lui son idée en une phrase.)

Il débute en architecture et en cadrage de projet. Suis ces étapes dans l'ordre :

1. **Vérifie le setup.** Si le plugin Ponytail n'est pas installé, rappelle-lui les deux lignes à taper : `/plugin marketplace add DietrichGebert/ponytail` puis `/plugin install ponytail@ponytail`. Continue quand même.

2. **Cadrage : utilise le skill brainstorming**, avec ces adaptations :
   - Pour chaque choix technique (langage, framework, stockage des données…), propose 2 ou 3 options avec leurs avantages et inconvénients en mots simples, puis **ta recommandation**.
   - Privilégie toujours la solution la plus simple qui marche.
   - Définis une **V1 minimale** qui marche vite, et une liste claire « pas dans la V1 ».

3. **Plan : utilise le skill writing-plans** pour la V1.

4. **Fichiers de base** (crée-les ou complète-les s'ils existent déjà) :
   - `CLAUDE.md` à partir du modèle ci-dessous, rempli pour ce projet.
   - `ARCHITECTURE.md`, une page maximum : les grandes briques, où sont les données, qui parle à qui, et les choix de techno avec leur raison en une ligne chacun.
   - `.gitignore` adapté à la stack, avec les fichiers de secrets (.env…).
   - `README.md` court : ce que c'est et comment le lancer.

5. **Sauvegarde** avec le skill git-sans-stress : premier commit puis push.

6. **Fin** : résume en 5 lignes maximum ce qui a été décidé, et donne la première étape du plan à attaquer.

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
- Agents : l'utilisateur donne son accord permanent, sans redemander, pour utiliser l'agent explorateur dès qu'une recherche demande de lire plus de 3 fichiers, l'agent codeur pour écrire du code sur plusieurs fichiers, et l'agent relecteur avant chaque commit.
- Structure du projet : voir ARCHITECTURE.md. Où on en est : dernier fichier de docs/handoff/.

## Structure du code
- Le point d'entrée (main) ne fait que lancer l'appli : aucune logique dedans.
- Séparer interface, logique, données et services externes (API).
- Un fichier = un rôle. Au-delà de ~300 lignes, découper.
- Dossiers rangés par fonctionnalité, pas par type de fichier.
- Configuration et secrets à part, jamais en dur dans le code.
- Avant de créer un fichier, vérifier s'il existe déjà un endroit logique pour ce code.
```
