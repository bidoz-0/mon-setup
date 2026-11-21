# mon-setup

Mon setup Claude Code, réutilisable dans tous mes projets.

## Installer (une fois par PC)

Dans Claude Code, taper ces 4 lignes une par une, puis redémarrer la session :

```
/plugin marketplace add bidoz-0/mon-setup
/plugin install mon-setup@mon-setup
/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail
```

## Commandes

| Commande | Quand |
|---|---|
| `/nouveau-projet [idée]` | Démarrer un projet ou une grosse fonctionnalité |
| `/integrer` | Ajouter un projet existant au setup (doc, sécurité, problèmes de structure) |
| `/reprends` | Revenir sur un projet : où on en était |
| `/sauvegarde` | Fin de session : vérification, relecture, push, résumé de reprise |
| `/wait-what` | Je n'ai pas compris la réponse |
| `/ponytail` | Voir ou changer le niveau de Ponytail (« stop ponytail » pour le couper) |

Si une commande entre en conflit avec une autre, utiliser la forme longue : `/mon-setup:sauvegarde`.

## Contenu

**Mes fichiers**
- Agents : `explorateur` (Haiku), `codeur` (Sonnet), `relecteur` (Sonnet, ou Opus en changeant une ligne)
- Skill : `git-sans-stress`
- Commandes : `nouveau-projet`, `integrer`, `reprends`, `sauvegarde`
- `CLAUDE-global.md` : mes règles, à mettre dans `~/.claude/CLAUDE.md`

**Skills officiels (copiés sans modification, voir THIRD_PARTY.md)**
- obra/superpowers : brainstorming, writing-plans, verification-before-completion
- mattpocock/skills : handoff, diagnosing-bugs, wait-what, codebase-design, grill-me, grilling
- emilkowalski/skills : apple-design, animation-performance
- blader/humanizer : humanizer
- JuliusBrussee/caveman : caveman

**Installé à part (plugin officiel)** : Ponytail

## Choisir le modèle une fois pour toutes
Dans `~/.claude/settings.json` sur le PC, ajouter `"model": "opusplan"` : Opus quand on est en mode plan (Maj+Tab), Sonnet le reste du temps. Mettre `"model": "opus"` pour toujours parler à Opus.

## Mettre à jour le setup sur un PC
- Dans Claude Code : `/plugin marketplace update mon-setup`, puis redémarrer la session. Le plugin est alors à jour dans tous les projets.
- Pour ne plus y penser : `/plugin` > Marketplaces > mon-setup > activer la mise à jour automatique.
- Ce qui ne se met **pas** à jour tout seul : `~/.claude/CLAUDE.md` (à recopier depuis `CLAUDE-global.md`) et les `CLAUDE.md` déjà créés dans les projets (relancer `/integrer` ou demander à Claude de les aligner sur le modèle).
- Après chaque modification du plugin, augmenter `version` dans `plugins/mon-setup/.claude-plugin/plugin.json` (ex. 1.1.0 → 1.2.0) : sinon la mise à jour n'est pas proposée.
- Le modèle de CLAUDE.md est copié dans 2 commandes (`nouveau-projet` et `integrer`) : le modifier dans les deux.

## Mettre à jour les skills officiels
Demander à Claude Code : « mets à jour les skills officiels de mon-setup depuis leurs repos d'origine, sans les modifier, et mets à jour THIRD_PARTY.md ».
