# Module 04 — Les boucles : répéter sans recopier

⏱ Durée estimée : 3 h 30 (cours 1 h 15, exercices 1 h 45, fil rouge 30 min)

## Objectifs

À la fin de ce module, tu sauras :

- **parcourir** une chaîne de caractères lettre par lettre avec `for` ;
- **répéter** une action un nombre précis de fois avec `for` et `range()` ;
- **calculer** une somme, un nombre de jours, une moyenne et un record avec un accumulateur ;
- **répéter tant qu'une condition est vraie** avec `while`, sans tomber dans la boucle infinie ;
- **arrêter** une boucle (`break`) ou **sauter** un tour (`continue`).

## Prérequis

- Modules à avoir faits : 00 (installation), 01 (premiers pas), 02 (chaînes), 03 (conditions).
- Tu dois savoir faire : créer une variable, faire un calcul, écrire une f-string avec `:.1f`,
  convertir avec `int()`, `float()` et `str()`, prendre un caractère avec `texte[0]` ou un morceau avec `texte[0:2]`,
  écrire un `if / elif / else` bien indenté.

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-04` dans le studio, à venir.
2. `01-cours.ipynb` : le cours, à exécuter cellule par cellule, dans l'ordre.
3. `02-exercices.ipynb` : 34 exercices en 3 niveaux + 5 révisions des modules précédents.
4. `03-fil-rouge.ipynb` : MétéoLocale, on parcourt les 30 jours de septembre à Toulouse.

## Je sais faire

- [ ] J'écris une boucle `for lettre in texte:` avec les deux-points et le corps indenté.
- [ ] Je sais que `range(5)` donne 0, 1, 2, 3, 4 (le 5 n'est pas compris) et que `range(1, 31)` donne 1 à 30.
- [ ] Je crée un accumulateur **avant** la boucle (`total = 0`) et je l'augmente **dans** la boucle.
- [ ] Je compte les tours qui respectent une condition (`if ...: compteur = compteur + 1`).
- [ ] Je calcule une moyenne : total divisé par le nombre de valeurs.
- [ ] Je garde le plus grand nombre vu jusqu'ici (le record), et je sais remettre un compteur à zéro (la série).
- [ ] J'écris une boucle `while` dont la condition finit par devenir fausse.
- [ ] Je sais interrompre une boucle infinie (bouton ■ « Interrupt »).
- [ ] J'utilise `break` pour sortir de la boucle et `continue` pour passer au tour suivant.
- [ ] Je lis les messages `IndentationError`, `SyntaxError: expected ':'` et `TypeError: 'int' object is not iterable`.
