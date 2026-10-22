# Sécurité

## Signaler une vulnérabilité

Ne publiez pas de vulnérabilité dans une issue publique. Utilisez le **signalement privé** de GitHub :
onglet *Security* du dépôt, puis *Report a vulnerability*. Merci d'indiquer la version concernée, le
scénario et, si possible, une façon de le reproduire.

## Ce que le plugin promet, et ce qu'il ne promet pas

- Les deux relecteurs (`tech-lead`, `code-reviewer`) n'ont que `Read`, `Grep` et `Glob` : ils ne
  peuvent lancer aucune commande ni modifier aucun fichier.
- Le plugin n'embarque **aucun script** et **aucun hook**.
- `security-engineer` et `ux-ui-designer` gardent tous leurs outils, parce qu'ils construisent aussi ;
  en mode revue, leur lecture seule ne tient qu'à leur consigne.
- Risque restant connu : les règles de Claude Code comparent le texte de la commande. Une forme
  imprévue (guillemets, options inhabituelles) peut leur échapper. Les caractères de shell, barre
  oblique inverse comprise, sont refusés dans `git push`. `git add` ne bloque pas toutes les formes
  de `-f` (par exemple collée à une autre option) : ce qui est commité se relit dans la PR. Dans tous
  les cas, mais seule la protection de branche côté serveur ferme le risque.
- Les règles de `settings.example.json` sont un **filet côté client** : elles n'empêchent un merge ou
  un push sur une branche protégée que si vous les copiez dans votre projet et que vous n'utilisez pas
  le mode `bypassPermissions`. Seule une **protection de branche côté serveur** (GitHub, Gitea…) le
  garantit.
- Sur un dépôt public, le contenu des issues, PR et commentaires peut venir de n'importe qui. Le skill
  le traite comme une donnée, ne reprend jamais une PR venue d'un fork et ne retient que les réponses
  des membres du dépôt. Relisez quand même ce que la chaîne propose avant de merger.
