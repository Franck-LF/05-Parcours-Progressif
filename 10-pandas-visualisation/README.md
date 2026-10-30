# Module 10 — pandas et les graphiques

⏱ Durée estimée : 4 h 30 (cours 1 h 30, exercices 2 h 30, fil rouge 45 min)

## Objectifs

À la fin de ce module, tu sais :
- **charger** un fichier CSV dans un DataFrame et **l'inspecter** (`head`, `shape`, `dtypes`) ;
- **sélectionner** des colonnes, **filtrer** des lignes et **calculer** des statistiques (`mean`, `max`, `sum`…) ;
- **regrouper** par ville (`groupby`) et **trier** (`sort_values`) ;
- **nettoyer** un fichier abîmé (`str.strip`, `replace`, `to_numeric`, `dropna`, `drop_duplicates`) ;
- **tracer** une courbe et des barres avec matplotlib, et les **enregistrer** en image.

## Prérequis

- Modules 00 à 09 terminés.
- Tu dois savoir faire : une boucle `for` sur une liste de dictionnaires, un dictionnaire d'accumulateurs
  (module 06), une f-string, lire un CSV avec `csv.DictReader` (module 08), `import` (module 09).
- pandas et matplotlib installés dans ton `.venv` (`uv pip install -r requirements.txt`, module 00).

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-10` dans le studio, à venir.
2. `01-cours.ipynb` : le cours, à exécuter cellule par cellule.
3. `02-exercices.ipynb` : 39 exercices + 5 révisions.
4. `03-fil-rouge.ipynb` : le bulletin mensuel MétéoLocale.

Les fichiers produits (images, bulletin) vont dans le dossier `sorties/` de ce module.

## Je sais faire

- [ ] Charger un CSV avec `pd.read_csv`, y compris avec `sep=";"`
- [ ] Lire `head()`, `shape` et `dtypes` d'un DataFrame
- [ ] Choisir une colonne (`meteo["temp_max"]`) ou plusieurs (`meteo[["ville", "temp_max"]]`)
- [ ] Filtrer des lignes, avec `&` et `|` et des parenthèses
- [ ] Calculer une moyenne par ville avec `groupby`, et trier avec `sort_values`
- [ ] Nettoyer une colonne de texte et la convertir en nombres
- [ ] Enlever les cases vides et les doublons
- [ ] Tracer une courbe et des barres, avec titre et axes, et les enregistrer dans `sorties/`
- [ ] Expliquer ce que pandas fait à ma place par rapport à la version « à la main »
