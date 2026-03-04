---
mode: agent
description: "Perform a structured, actionable code review on the selected code or modified files."
---

# Code Review

Perform a complete and structured code review. Analyze the code provided in context (open files, selection, or Git diff).

## What to check

### 🐛 Bugs & logic
- Identify obvious bugs or unhandled edge cases
- Check error handling and failure paths
- Detect race conditions or state issues

### 🔒 Security
- SQL injection, XSS, CSRF and other common vulnerabilities
- Secrets or sensitive data exposed in code
- Insufficient user input validation

### ⚡ Performance
- N+1 queries or expensive loops
- Unnecessary memory allocations
- Blocking operations in async contexts

### 🏗️ Architecture & maintainability
- SOLID principles adherence
- Code duplication (DRY)
- Clear and expressive naming

### ✅ Tests
- Coverage of happy path and edge cases
- Brittle tests or over-coupling to implementation details

## Response format

For each issue found:

**[SEVERITY]** — `file:line` — Short description
> Explanation of the problem and suggested fix

Severity levels: `🔴 CRITICAL` | `🟠 MAJOR` | `🟡 MINOR` | `🔵 SUGGESTION`

---

If the code is good, state it explicitly: "✅ No major issues found."
