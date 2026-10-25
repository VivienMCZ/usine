# Changelog

## Non publié

- CI `Validation du plugin` : `claude plugin validate`, JSON valides, version présente dans le
  CHANGELOG, relecteurs toujours en lecture seule. Actions épinglées par SHA, droits en lecture seule.

## 0.1.0 — 22/10/2026

Première version, extraite de la chaîne `/usine` du projet Shift et rendue générique.

- Skill `usine` : spec → build → revues en parallèle → approbation, toujours une PR, jamais un merge.
- 7 agents : `tech-lead`, `code-reviewer` (lecture seule), `backend-engineer`, `frontend-engineer`,
  `devops-engineer`, `security-engineer`, `ux-ui-designer`.
- Modèle de garde-fous `settings.example.json` à copier dans chaque projet.
- Revue de sécurité avant publication : relecteurs sans `Bash` (dossier de revue préparé par la
  session principale), contenu d'issue et de PR traité comme une donnée, PR de fork jamais reprises,
  refus de `git push … heads/main`, des caractères de shell dans `git push` et des pushes par l'API
  GitHub ; ouverture de PR et commentaires soumis à confirmation ; `git add -f`, `--output` et
  `--no-index` refusés.
