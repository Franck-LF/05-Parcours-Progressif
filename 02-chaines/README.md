# Module 02 — Les chaînes de caractères

🟢 Débutant | ⏱ 3 h 30 (cours 1 h 15, exercices 1 h 45, fil rouge 30 min) | 🔑 guillemets, len, +, f-strings, int/float/str, [ ], tranches, méthodes, split

Les relevés météo arrivent souvent sous forme de **texte** : `"2026-09-01,Toulouse,12.0,25.9,17.4,11"`. Dans ce module,
tu apprends à mesurer, assembler, découper et nettoyer du texte, à le transformer en nombres, et à fabriquer un
affichage propre.

## Objectifs

À la fin de ce module, tu sauras :

1. **Écrire** une chaîne de caractères (y compris avec une apostrophe) et **mesurer** sa longueur avec `len`.
2. **Assembler** du texte avec `+` et, surtout, avec les **f-strings** (`f"{temp:.1f} °C"`).
3. **Convertir** un texte en nombre (`int()`, `float()`) et un nombre en texte (`str()`).
4. **Extraire** un caractère ou un morceau d'un texte avec `[ ]` et les tranches `[début:fin]`.
5. **Nettoyer** et **découper** un texte avec `.strip()`, `.upper()`, `.lower()`, `.replace()` et `.split()`.

## Prérequis

- Modules à avoir faits : [00](../00-prerequis-installation/README.md) et [01 — Premiers pas](../01-premiers-pas/README.md).
- Tu dois savoir faire : créer une variable, afficher avec `print`, reconnaître `int`/`float`/`str`/`bool` avec
  `type()`, calculer avec `+ - * /`, arrondir avec `round`, lire une `NameError` et une `SyntaxError`.

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-02` dans le studio, à venir (pas encore disponible : passe à l'étape suivante).
2. `01-cours.ipynb` : le cours (prédis avant d'exécuter les cellules 🔮).
3. `02-exercices.ipynb` : 35 exercices en trois niveaux, puis 5 révisions espacées des modules 00 et 01.
4. `03-fil-rouge.ipynb` : lire une ligne brute de relevé et l'afficher proprement.

## ✅ Je sais faire

- [ ] Écrire un texte entre guillemets, avec des `"` quand il contient une apostrophe
- [ ] Mesurer la longueur d'un texte avec `len`
- [ ] Assembler des textes avec `+`, et corriger la `TypeError` quand un nombre s'y glisse (avec `str()`)
- [ ] Écrire une f-string avec des variables et un format `:.1f`
- [ ] Transformer `"25.9"` en `25.9` avec `float()`, `"11"` en `11` avec `int()`, et lire une `ValueError`
- [ ] Prendre le premier caractère `[0]`, le dernier `[-1]` et une tranche `[0:4]`
- [ ] Nettoyer un texte avec `.strip()`, `.upper()`, `.lower()`, `.replace(",", ".")`
- [ ] Découper une ligne avec `.split(",")` et récupérer un morceau avec `[1]`
- [ ] Simuler une saisie au clavier avec une variable au lieu de `input()`
