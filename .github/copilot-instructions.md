# Global instructions — my-copilot

This repository contains my personal GitHub Copilot plugins (agents, skills, instructions, prompts).

## General conventions

- Always include the required YAML frontmatter for each plugin type
- Instruction files use `applyTo` to target specific files
- Keep plugins concise, focused, and reusable
- Document each plugin in the main README.md (catalog table)

## Expected structure

```
plugins/<name>/    → installable CLI plugins
  .github/plugin/plugin.json
  agents/          → *.agent.md
  skills/<name>/   → SKILL.md
instructions/      → *.instructions.md  (VSCode/Chat)
prompts/           → *.prompt.md        (VSCode/Chat)
```
