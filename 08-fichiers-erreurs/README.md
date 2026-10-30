# Module 08 — Fichiers et erreurs : lire le vrai fichier

⏱ Durée estimée : **5 h** (cours 1 h 30, exercices 2 h 45, fil rouge 45 min)

🎬 Vidéo : scénario `python-debutant-08` dans le studio, à venir.

## Objectifs

À la fin de ce module, tu sais :

- **construire** le chemin d'un fichier avec `Path` et **vérifier** qu'il existe ;
- **lire** un fichier texte et un fichier CSV (`csv.reader`, `csv.DictReader`) avec `with open(...)` en UTF-8 ;
- **écrire** un fichier CSV (`csv.DictWriter`) et un fichier JSON (`json.dump`), puis le **relire** (`json.load`) ;
- **nettoyer** des données abîmées (virgule décimale, cases vides, `N/A`, doublons) ;
- **gérer** une erreur prévisible avec `try` / `except` / `else` (`FileNotFoundError`, `ValueError`).

## Prérequis

- Modules **01 à 07** faits.
- Tu dois savoir faire : `split`, `strip`, `replace`, `float()` (module 02) ; une boucle `for` ; une liste de
  dictionnaires (module 06) ; écrire une fonction avec `return` (module 07).

## Ordre de travail

1. `01-cours.ipynb` : lis et exécute chaque cellule, dans l'ordre. Fais les prédictions 🔮 avant d'exécuter.
2. `02-exercices.ipynb` : 35 exercices (niveaux 1, 2, 3) + 5 révisions espacées.
3. `03-fil-rouge.ipynb` : tu charges le vrai `meteo.csv`, tu nettoies `meteo_brut.csv` et tu écris un résumé JSON.

Les fichiers que tu écris vont dans le dossier `sorties/` de ce module (il est créé automatiquement). On ne
touche **jamais** aux fichiers de `donnees/` : ce sont les originaux.

## ✅ Je sais faire

- [ ] Écrire un chemin relatif vers `../donnees/meteo.csv` et vérifier qu'il existe avec `.exists()`
- [ ] Ouvrir un fichier avec `with open(chemin, encoding="utf-8") as fichier:`
- [ ] Parcourir les lignes d'un fichier et les nettoyer avec `.strip()`
- [ ] Lire un CSV en liste de dictionnaires avec `csv.DictReader` (et convertir les nombres avec `float`)
- [ ] Lire un CSV séparé par des `;` avec `delimiter=";"`
- [ ] Écrire un CSV avec `csv.DictWriter` (`writeheader`, `writerow`)
- [ ] Écrire et relire un fichier JSON avec `json.dump` et `json.load`
- [ ] Lire un `FileNotFoundError` et corriger le chemin
- [ ] Protéger une conversion avec `try` / `except ValueError`
