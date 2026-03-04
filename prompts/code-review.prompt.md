---
mode: agent
description: "Effectue une revue de code structurée et actionnable sur le code sélectionné ou les fichiers modifiés."
---

# Revue de code

Effectue une revue de code complète et structurée. Analyse le code fourni en contexte (fichiers ouverts, sélection, ou diff Git).

## Ce que tu dois vérifier

### 🐛 Bugs & logique
- Identifier les bugs évidents ou les cas limites non gérés
- Vérifier la gestion des erreurs et des cas d'échec
- Détecter les conditions de course ou problèmes d'état

### 🔒 Sécurité
- Injection SQL, XSS, CSRF et autres vulnérabilités courantes
- Secrets ou données sensibles exposés dans le code
- Validation insuffisante des entrées utilisateur

### ⚡ Performance
- Requêtes N+1 ou boucles coûteuses
- Allocations mémoire inutiles
- Opérations bloquantes dans des contextes async

### 🏗️ Architecture & maintenabilité
- Respect des principes SOLID
- Duplication de code (DRY)
- Nommage clair et expressif

### ✅ Tests
- Couverture des cas nominaux et des cas limites
- Tests fragiles ou trop couplés à l'implémentation

## Format de réponse

Pour chaque problème identifié :

**[SÉVÉRITÉ]** — `fichier:ligne` — Description courte
> Explication du problème et suggestion de correction

Niveaux de sévérité : `🔴 CRITIQUE` | `🟠 MAJEUR` | `🟡 MINEUR` | `🔵 SUGGESTION`

---

Si le code est bon, indique-le explicitement : "✅ Aucun problème majeur identifié."
