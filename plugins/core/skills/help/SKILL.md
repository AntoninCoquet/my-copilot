---
name: help
description: "Quick reference for the my-copilot marketplace — agents, skills, and Copilot CLI commands. Use this when you need a cheatsheet or want to know what's available."
---

# my-copilot — Help & Cheatsheet

## Plugins & agents

| Plugin | Agent | Best for |
|--------|-------|----------|
| `core` | `helper` | Finding the right tool, Copilot CLI usage |
| `frontend` | `frontend-dev` | Building UI components and features |
| `frontend` | `frontend-reviewer` | Code review (a11y, perf, patterns, bugs) |

Invoke an agent: `/agent` → select from the list

## Skills

| Plugin | Skill | Invoke |
|--------|-------|--------|
| `core` | `help` | `/help` |

## VSCode / Copilot Chat

| Type | How to use |
|------|------------|
| Instructions | Copy `instructions/*.instructions.md` → `.github/instructions/` of target project |
| Code review prompt | Copy `prompts/code-review.prompt.md` → `.github/prompts/` → invoke with `/code-review` |

## Copilot CLI quick reference

```
/agent                              → browse and select an agent
/skills list                        → list available skills
/plugin list                        → list installed plugins
/plugin install <name>              → install a plugin
/plugin update <name>               → update a plugin
/plugin marketplace add <owner/repo>→ register a marketplace source
/model                              → switch model
/diff                               → review current changes
/review                             → run code review
/plan                               → switch to plan mode
```

## Marketplace repo

https://github.com/AntoninCoquet/my-copilot
