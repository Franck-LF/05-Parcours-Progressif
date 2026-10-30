# Module 09 — Modules et API météo

⏱ Durée estimée : **5 h** (cours 1 h 30, exercices 2 h 45, fil rouge 45 min)

🎬 Vidéo : scénario `python-debutant-09` dans le studio, à venir.

## Objectifs

À la fin de ce module, tu sais :

- **importer** un module avec `import`, `from ... import` et `as`, et lire les erreurs d'import ;
- **utiliser** les modules standard `math`, `random` (avec `seed`), `datetime` (dates simples) et `statistics` ;
- **créer** ton propre module `.py` et l'importer (et le recharger après une modification) ;
- **installer** un paquet dans ton environnement virtuel avec `uv pip install` et `requirements.txt` ;
- **expliquer** ce qu'est une API HTTP qui répond en JSON, et **exploiter** sa réponse (ici, les prévisions Open-Meteo).

## Prérequis

- Modules **01 à 08** faits, et l'environnement virtuel du module 00 (`~/meteolocale/.venv`) en place.
- Tu dois savoir faire : écrire des fonctions (module 07), lire et écrire des fichiers CSV et JSON, `try/except`
  (module 08), parcourir une liste de dictionnaires (module 06).

## Ordre de travail

1. `01-cours.ipynb` : lis et exécute chaque cellule, dans l'ordre. Fais les prédictions 🔮 avant d'exécuter.
   Une seule cellule utilise Internet (l'appel à l'API) : sans réseau, elle affiche un message et le cours continue.
2. `02-exercices.ipynb` : 34 exercices (16 pour imiter, 12 pour adapter, 6 pour transposer) + 5 révisions espacées. **Aucun n'utilise Internet** :
   ils lisent la réponse figée `../donnees/open_meteo_toulouse.json`.
3. `03-fil-rouge.ipynb` : tu ranges ta boîte à outils dans ton module `meteolocale.py` et tu fusionnes les
   prévisions d'octobre avec l'historique de septembre.

## ✅ Je sais faire

- [ ] Écrire `import math` puis `math.sqrt(...)`, et `from statistics import mean` puis `mean(...)`
- [ ] Lire un `ModuleNotFoundError`, un `ImportError` et un `AttributeError` liés aux imports
- [ ] Fixer le hasard avec `random.seed(...)` pour obtenir toujours le même tirage
- [ ] Créer une date (`date(2026, 9, 1)`, `date.fromisoformat(...)`), ajouter des jours avec `timedelta`, trouver le jour de la semaine
- [ ] Calculer moyenne, médiane et écart-type avec `statistics`
- [ ] Créer un fichier `.py` de fonctions et l'importer ; le recharger avec `importlib.reload`
- [ ] Activer le venv dans Git Bash et taper `uv pip install -r requirements.txt`
- [ ] Expliquer ce que fait `requests.get(url, params=..., timeout=10)` et `reponse.json()`
- [ ] Transformer une réponse JSON d'API en liste de dictionnaires
