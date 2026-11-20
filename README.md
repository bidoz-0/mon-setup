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
| `/reprends` | Revenir sur un projet : où on en était |
| `/sauvegarde` | Fin de session : vérification, relecture, push, résumé de reprise |
| `/wait-what` | Je n'ai pas compris la réponse |
| `/ponytail` | Voir ou changer le niveau de Ponytail (« stop ponytail » pour le couper) |

Si une commande entre en conflit avec une autre, utiliser la forme longue : `/mon-setup:sauvegarde`.

## Contenu

**Mes fichiers**
- Agents : `explorateur` (Haiku), `codeur` (Sonnet), `relecteur` (Sonnet, ou Opus en changeant une ligne)
- Skill : `git-sans-stress`
- Commandes : `nouveau-projet`, `reprends`, `sauvegarde`
- `CLAUDE-global.md` : mes règles, à mettre dans `~/.claude/CLAUDE.md`

**Skills officiels (copiés sans modification, voir THIRD_PARTY.md)**
- obra/superpowers : brainstorming, writing-plans, verification-before-completion
- mattpocock/skills : handoff, diagnosing-bugs, wait-what, codebase-design
- emilkowalski/skills : apple-design, animation-performance
- blader/humanizer : humanizer

**Installé à part (plugin officiel)** : Ponytail

## Mettre à jour les skills officiels
Demander à Claude Code : « mets à jour les skills officiels de mon-setup depuis leurs repos d'origine, sans les modifier, et mets à jour THIRD_PARTY.md ».
