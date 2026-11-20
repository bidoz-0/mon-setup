---
description: Fin de session (vérifie, fait relire, sauvegarde sur GitHub et prépare la reprise)
---

Fin de session. Dans l'ordre :

1. **Vérification** : utilise le skill verification-before-completion. Lance le build et les tests s'il y en a. Si ça échoue, arrête-toi et explique le problème simplement.

2. **Relecture** : fais relire par l'agent relecteur tout ce qui a changé depuis le dernier push. S'il trouve un problème sérieux, montre-le et demande à l'utilisateur s'il veut corriger maintenant ou sauvegarder quand même.

3. **Sauvegarde** : utilise le skill git-sans-stress (commit + push sur la bonne branche).

4. **Reprise** : utilise le skill handoff et enregistre le document dans `docs/handoff/AAAA-MM-JJ.md` (date du jour). Commite-le et pousse-le aussi.

5. **Fin** : résume en 3 lignes ce qui est sauvegardé, où, et la prochaine étape.
