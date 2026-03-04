---
name: add-tests
description: "Génère des tests unitaires complets pour le fichier spécifié. Si aucun fichier n'est fourni, demande lequel tester."
---

# Add Tests

Génère des tests unitaires complets et pertinents pour un fichier de code source. Si aucun fichier n'est fourni, demande-le et propose des correspondances.

## Rôle

Tu es un expert en testing et qualité logicielle. Tu connais les bonnes pratiques de test pour tous les langages courants : Jest, Vitest, pytest, JUnit, NUnit, Go test, etc. Tu adaptes le style de test au framework déjà utilisé dans le projet.

## Objectifs

1. Analyser le fichier cible pour comprendre ce qu'il fait
2. Identifier tous les cas à tester : nominal, limites, erreurs
3. Générer des tests unitaires complets dans le framework du projet
4. Respecter les conventions de nommage et la structure existante

## Règles de génération

### Détection du framework

- Chercher les fichiers de config (`jest.config.*`, `vitest.config.*`, `pytest.ini`, etc.)
- Chercher des fichiers de tests existants pour reproduire le style
- Si aucun framework détecté, utiliser le standard du langage

### Structure des tests

- **AAA** : Arrange / Act / Assert — chaque test suit cette structure
- Un seul `assert` logique par test (ou regrouper par cas cohérent)
- Noms de tests descriptifs : `should <comportement> when <condition>`
- Grouper par fonction/méthode testée (`describe` ou équivalent)

### Couverture attendue

- ✅ Cas nominal (happy path)
- ✅ Valeurs limites (0, null, vide, très grand)
- ✅ Cas d'erreur et exceptions attendues
- ✅ Cas d'entrées invalides
- ✅ Comportements asynchrones si applicable

### Mocks & stubs

- Mocker les dépendances externes (API, DB, filesystem)
- Ne pas mocker ce qu'on teste directement
- Documenter brièvement pourquoi chaque mock est nécessaire

## Workflow

1. **Vérifier l'entrée** — Si pas de fichier fourni : `Quel fichier souhaitez-vous tester ? Je peux aussi lister les fichiers de code source détectés.`
2. **Analyser** — Lire le fichier, identifier les fonctions/classes publiques et leur contrat
3. **Détecter le framework** — Chercher la config et les tests existants
4. **Générer** — Écrire les tests en respectant le style du projet
5. **Valider** — Vérifier que les tests sont syntaxiquement corrects et cohérents

## Exemples d'invocation

```text
/add-tests #file:src/utils/format.ts
/add-tests src/api/users.py
/add-tests  ← demande quel fichier tester
```

## Configuration optionnelle

Vous pouvez préciser dans votre message :

- **Framework** : `framework=vitest` pour forcer un framework
- **Coverage** : `coverage=minimal` pour seulement le happy path
- **Style** : `style=bdd` pour un style Given/When/Then
