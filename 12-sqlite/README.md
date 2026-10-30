# Module 12 — Ranger les données en base : SQLite

⏱ Durée estimée : 4 h 15 (cours 1 h 20, exercices 2 h 30, fil rouge 45 min)

## Objectifs

À la fin de ce module, tu sais :
- **expliquer** ce qu'est une base de données, une table, une requête SQL ;
- **créer** une base SQLite et une table avec `sqlite3` (`connect`, `execute`, `CREATE TABLE`, `commit`) ;
- **insérer** des lignes avec des requêtes **paramétrées** (`?`) et **justifier** pourquoi on n'utilise jamais de f-string ;
- **interroger** (`SELECT … WHERE … ORDER BY`, `fetchall`), **corriger** (`UPDATE`) et **supprimer** (`DELETE`) ;
- **récupérer** une requête dans un DataFrame avec `pd.read_sql`.

## Prérequis

- Modules 00 à 11 terminés.
- Tu dois savoir faire : un tuple et son déballage (module 06), une fonction avec `return` (module 07),
  `to_dict("records")` et `groupby` (module 10), lire les attributs d'un objet (module 11).

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-12` dans le studio, à venir.
2. `01-cours.ipynb` : le cours, à exécuter cellule par cellule, **dans l'ordre**.
3. `02-exercices.ipynb` : 33 exercices + 5 révisions (chaque exercice crée sa petite base dans `sorties/`).
4. `03-fil-rouge.ipynb` : l'historique MétéoLocale dans `sorties/meteolocale.db`.

## Je sais faire

- [ ] Ouvrir une base avec `sqlite3.connect` et la fermer avec `close()`
- [ ] Créer une table à neuf (`DROP TABLE IF EXISTS` puis `CREATE TABLE`) avec les types `TEXT`, `REAL`, `INTEGER`
- [ ] Insérer une ligne avec des `?` et un tuple, y compris un tuple à un élément `(valeur,)`
- [ ] Expliquer les deux dangers d'une f-string dans une requête (apostrophe, injection SQL)
- [ ] Valider avec `commit`, et savoir ce qui se passe sans
- [ ] Lire avec `SELECT … WHERE … ORDER BY` et `fetchall`, et déballer les tuples
- [ ] Corriger avec `UPDATE` et supprimer avec `DELETE`, toujours avec un `WHERE`
- [ ] Récupérer un DataFrame avec `pd.read_sql(..., params=(...,))`
- [ ] Lire `OperationalError` et `ProgrammingError: Incorrect number of bindings`
