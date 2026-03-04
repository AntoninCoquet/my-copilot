# Instructions globales — my-copilot

Ce repo contient mes plugins GitHub Copilot personnels (agents, skills, instructions, prompts).

## Conventions générales

- Toujours inclure le frontmatter YAML requis pour chaque type de plugin
- Les fichiers d'instructions utilisent `applyTo` pour cibler des fichiers spécifiques
- Garder les plugins concis, ciblés et réutilisables
- Documenter chaque plugin dans le README.md principal (tableau Catalogue)

## Structure attendue

```
agents/          → *.agent.md
instructions/    → *.instructions.md
prompts/         → *.prompt.md
skills/<name>/   → SKILL.md
```
