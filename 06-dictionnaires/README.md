# Module 06 — Les dictionnaires, ta fiche (et ton premier tableau)

⏱ Durée estimée : 4 h 30 (cours 1 h 30, exercices 2 h 15, fil rouge 45 min)

## Objectifs

À la fin de ce module, tu sauras :

- **ranger** les informations d'un relevé dans un dictionnaire, et les **lire** par leur nom (la clé) ;
- **modifier, ajouter, supprimer** une rubrique, et éviter la `KeyError` avec `.get` et `in` ;
- **parcourir** un dictionnaire avec `.keys()`, `.values()`, `.items()` et le déballage de tuples ;
- **manipuler une table** (une liste de dictionnaires) : lire une colonne, filtrer des lignes, calculer une moyenne
  par ville ;
- **dédoublonner** avec un ensemble (`set`).

## Prérequis

- Modules à avoir faits : 00 à 05.
- Tu dois savoir faire : créer une liste, `append`, parcourir une liste avec `for` et `enumerate`, `sum`, `len`,
  `max`, `sorted`, une compréhension de liste, un accumulateur et un compteur.

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-06` dans le studio, à venir.
2. `01-cours.ipynb` : le cours, à exécuter cellule par cellule, dans l'ordre.
3. `02-exercices.ipynb` : 36 exercices en 3 niveaux + 5 révisions des modules précédents.
4. `03-fil-rouge.ipynb` : MétéoLocale, ton premier vrai tableau de données (12 lignes) et la moyenne par ville.

## Je sais faire

- [ ] Je crée un dictionnaire `{"ville": "Albi", "temp_max": 26.8}` et je lis `releve["ville"]`.
- [ ] Je modifie ou j'ajoute une rubrique avec `releve["cle"] = valeur`, et j'en retire une avec `del`.
- [ ] Je lis une rubrique qui peut manquer avec `.get("cle", 0)`, et je teste sa présence avec `in`.
- [ ] Je parcours un dictionnaire avec `for cle, valeur in d.items():`.
- [ ] Je déballe un tuple : `lat, lon = (43.6, 1.44)`.
- [ ] Je compte par catégorie avec `comptes[c] = comptes.get(c, 0) + 1`.
- [ ] Je vois une liste de dictionnaires comme un tableau Excel : une ligne = un dictionnaire, une colonne = une clé.
- [ ] J'extrais une colonne, je filtre des lignes, je calcule une moyenne par ville.
- [ ] Je dédoublonne avec `set()` et je trie le résultat avec `sorted()`.
- [ ] Je lis le message `KeyError: 'vent'`.
