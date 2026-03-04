# 🤖 my-copilot

Ma marketplace personnelle de plugins GitHub Copilot — agents, skills, instructions et prompts que j'utilise et fais évoluer selon mes projets.

## Structure du repo

```
my-copilot/
├── agents/                    # Custom agents (.agent.md)
├── instructions/              # Instructions Copilot (.instructions.md)
├── prompts/                   # Prompts réutilisables (.prompt.md)
├── skills/                    # Skills Copilot (dossier + SKILL.md)
│   └── <skill-name>/
│       └── SKILL.md
└── .github/
    └── copilot-instructions.md  # Instructions globales du repo
```

## Comment utiliser ces plugins

### Dans GitHub Copilot (VSCode / GitHub.com)

| Type | Emplacement cible | Déclencheur |
|------|-------------------|-------------|
| **Instructions** | `.github/instructions/` du projet cible | Automatique selon `applyTo` |
| **Prompts** | `.github/prompts/` du projet cible | `/nom-du-prompt` dans le chat |
| **Agents** | `.github/agents/` du projet cible (ou global) | `@nom-agent` dans le chat |
| **Skills** | Référencé dans la config Copilot CLI | Invoqué par le CLI |

### Copier un plugin dans un projet

```bash
# Copier une instruction
cp instructions/mon-instruction.instructions.md ../mon-projet/.github/instructions/

# Copier un prompt
cp prompts/mon-prompt.prompt.md ../mon-projet/.github/prompts/

# Copier un agent
cp agents/mon-agent.agent.md ../mon-projet/.github/agents/
```

## Conventions de nommage

- **Instructions** : `<sujet>.instructions.md` (ex: `typescript.instructions.md`)
- **Prompts** : `<action>.prompt.md` (ex: `code-review.prompt.md`)
- **Agents** : `<nom>.agent.md` (ex: `senior-dev.agent.md`)
- **Skills** : dossier `<skill-name>/SKILL.md` (ex: `add-tests/SKILL.md`)

## Catalogue

### 🎯 Instructions

| Nom | Description | `applyTo` |
|-----|-------------|-----------|
| [example](./instructions/example.instructions.md) | Instruction d'exemple | `**` |

### 💬 Prompts

| Nom | Description |
|-----|-------------|
| [code-review](./prompts/code-review.prompt.md) | Revue de code structurée |

### 🤖 Agents

| Nom | Modèle | Description |
|-----|--------|-------------|
| [senior-dev](./agents/senior-dev.agent.md) | Claude Sonnet | Agent développeur senior autonome |

### 🛠️ Skills

| Nom | Description |
|-----|-------------|
| [add-tests](./skills/add-tests/SKILL.md) | Génère des tests unitaires pour un fichier |

## Contribuer / Évoluer

Ce repo est personnel et évolue selon mes besoins. Pour ajouter un plugin :

1. Respecter les conventions de nommage ci-dessus
2. Toujours inclure le frontmatter YAML requis
3. Documenter le plugin dans ce README (tableau Catalogue)
4. Tester le plugin sur un projet réel avant de committer
