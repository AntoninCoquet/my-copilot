# 🤖 my-copilot

My personal GitHub Copilot plugin marketplace — agents, skills, instructions, and prompts that I use and evolve across my projects.

## Repository structure

```
my-copilot/
├── .github/
│   ├── copilot-instructions.md          # Global repo instructions
│   └── plugin/
│       └── marketplace.json             # 📦 Marketplace registry
├── instructions/                        # For VSCode/Copilot Chat (.instructions.md)
├── prompts/                             # For VSCode/Copilot Chat (.prompt.md)
└── plugins/                             # Installable plugins via Copilot CLI
    └── <plugin-name>/
        ├── .github/plugin/plugin.json   # Plugin manifest
        ├── agents/                      # Custom agents (.agent.md)
        └── skills/                      # Skills (folder + SKILL.md)
            └── <skill-name>/
                └── SKILL.md
```

## Installation via Copilot CLI

```bash
# 1. Register this repo as a marketplace source
/plugin marketplace add acoquet/my-copilot

# 2. List available plugins
/plugin list

# 3. Install a plugin
/plugin install core

# 4. Update a plugin
/plugin update core
```

## Available plugins

### 📦 core

Essential cross-project tools.

| Type | Name | Description |
|------|------|-------------|
| 🤖 Agent | [helper](./plugins/core/agents/helper.agent.md) | Marketplace guide — find the right tool |
| 🛠️ Skill | [help](./plugins/core/skills/help/SKILL.md) | Quick cheatsheet — agents, skills, CLI commands |

### 📦 frontend

Frontend development — UI, React, TypeScript, accessibility, performance.

| Type | Name | Description |
|------|------|-------------|
| 🤖 Agent | [frontend-dev](./plugins/frontend/agents/frontend-dev.agent.md) | Build UI components and features |
| 🤖 Agent | [frontend-reviewer](./plugins/frontend/agents/frontend-reviewer.agent.md) | Review frontend code (a11y, perf, patterns, bugs) |

## For VSCode / Copilot Chat

The `instructions/` and `prompts/` files are meant to be copied into the `.github/` folder of the target project.

| Type | Target location | Trigger |
|------|-----------------|---------|
| **Instructions** | `.github/instructions/` | Automatic based on `applyTo` |
| **Prompts** | `.github/prompts/` | `/prompt-name` in chat |

## Adding a new plugin

1. Create `plugins/<name>/` with its structure
2. Add `plugins/<name>/.github/plugin/plugin.json`
3. Register the plugin in `.github/plugin/marketplace.json`
4. Document it in this README (table above)

## Conventions

- **Agents**: `<name>.agent.md` — frontmatter: `name`, `description`, `model`
- **Skills**: folder `<skill-name>/SKILL.md` — frontmatter: `name`, `description`
- **Instructions**: `<subject>.instructions.md` — frontmatter: `applyTo`
- **Prompts**: `<action>.prompt.md` — frontmatter: `mode`, `description`
