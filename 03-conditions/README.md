# Module 03 — Les conditions

🟢 Débutant | ⏱ 3 h 30 (cours 1 h 15, exercices 1 h 45, fil rouge 30 min) | 🔑 comparaisons, if / elif / else, indentation, and / or / not

Jusqu'ici, Python exécutait toutes les lignes, dans l'ordre. Dans ce module, il apprend à **décider** : « s'il
pleut plus de 10 mm, c'est une forte pluie ; sinon, s'il pleut un peu, c'est de la pluie ; sinon, c'est sec ».

## Objectifs

À la fin de ce module, tu sauras :

1. **Comparer** deux valeurs (`==`, `!=`, `<`, `>`, `<=`, `>=`) et **ranger** le résultat `True`/`False` dans une variable.
2. **Écrire** un bloc `if` / `elif` / `else` correctement **indenté**, et choisir l'ordre des conditions.
3. **Combiner** des conditions avec `and`, `or` et `not`.
4. **Imbriquer** une condition dans une autre.
5. **Lire** une `IndentationError` (et la `SyntaxError` du `=` à la place de `==`), et les corriger.

## Prérequis

- Modules à avoir faits : [00](../00-prerequis-installation/README.md), [01](../01-premiers-pas/README.md) et
  [02 — Les chaînes](../02-chaines/README.md).
- Tu dois savoir faire : créer des variables, calculer, connaître le type `bool` (`True`/`False`), écrire une
  f-string, convertir un texte en nombre avec `float()`, découper une ligne avec `.split()`, nettoyer un texte avec
  `.strip().lower()`.

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-03` dans le studio, à venir (pas encore disponible : passe à l'étape suivante).
2. `01-cours.ipynb` : le cours (prédis avant d'exécuter les cellules 🔮).
3. `02-exercices.ipynb` : 32 exercices en trois niveaux, puis 5 révisions espacées des modules 00 à 02.
4. `03-fil-rouge.ipynb` : classer une journée et lui associer un pictogramme.

## ✅ Je sais faire

- [ ] Écrire une comparaison et dire si elle vaut `True` ou `False`
- [ ] Ne pas confondre `=` (ranger) et `==` (comparer)
- [ ] Comparer deux textes après les avoir nettoyés avec `.strip().lower()`
- [ ] Écrire un `if` avec ses deux-points et son bloc indenté de 4 espaces
- [ ] Ajouter un `else`, puis des `elif`, en mettant la condition la plus exigeante en premier
- [ ] Ranger le résultat d'un `if` dans une variable (`classe = "pluie"`)
- [ ] Combiner deux conditions avec `and` ou `or`, en inverser une avec `not`
- [ ] Écrire un `if` dans un `if` (8 espaces au deuxième niveau)
- [ ] Lire une `IndentationError` et corriger les espaces
