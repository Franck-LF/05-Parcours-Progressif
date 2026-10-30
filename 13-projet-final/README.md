# Module 13 — Projet final : le bulletin complet

⏱ Durée estimée : 4 à 6 h

## Objectifs

À la fin de ce projet, tu sais :
- **enchaîner** les gestes des modules 01 à 12 dans un pipeline complet, du fichier brut au bulletin ;
- **nettoyer** un fichier réel abîmé avec des fonctions réutilisables (pandas) et **contrôler** la qualité du résultat ;
- **ranger** les données propres dans une base SQLite avec des requêtes paramétrées, puis les **relire** ;
- **produire** des statistiques, une prévision naïve, un graphique et un bulletin texte et JSON ;
- **automatiser** le tout dans une fonction qu'on relance sur un nouveau fichier.

## Prérequis

- Modules 00 à 12 terminés (fil rouge compris).
- Tu dois savoir faire : nettoyer une colonne pandas, `groupby` et `sort_values` (module 10), une classe avec `fit` /
  `predict` (module 11), `CREATE TABLE`, `INSERT` avec `?`, `SELECT … ORDER BY`, `pd.read_sql` (module 12),
  écrire un fichier texte et un JSON (module 08).

## Ce qui est nouveau (un peu)

Presque tout a déjà été vu ; chaque étape te dit **dans quel module** retrouver le geste. Trois petites choses sont
nouvelles, et expliquées sur place quand elles arrivent :
- `tableau.copy()` (étape 3) : un double indépendant d'un DataFrame, pour ne jamais abîmer l'original ;
- un **dictionnaire dans un dictionnaire** (étape 14) : une fiche dont une rubrique contient d'autres fiches ;
- les conversions `float(...)` et `int(...)` avant `json.dump` (étape 14) : `json` ne connaît que les nombres Python
  de base, pas ceux de pandas.

Si une étape te bloque, c'est le signal de relire le module indiqué.

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-13` dans le studio, à venir.
2. `01-enonce.ipynb` : le projet, en 15 étapes enchaînées (exécute-les dans l'ordre).

Les fichiers produits vont dans `sorties/` : `meteolocale_final.db`, `bulletin_final.png`, `bulletin_final.txt`,
`bulletin_final.json`, `pipeline_test.db`.

## Je sais faire

- [ ] Diagnostiquer un fichier brut (villes mal écrites, cases vides, doublons) avant de le réparer
- [ ] Ranger un nettoyage dans une fonction qui reçoit et renvoie un DataFrame
- [ ] Vérifier la qualité des données avec des filtres et des booléens
- [ ] Créer une base, y insérer les données propres avec des `?`, et la relire avec `pd.read_sql`
- [ ] Construire un tableau par ville trié, et trouver des records avec `ORDER BY`
- [ ] Réutiliser un modèle `fit` / `predict` pour chaque ville
- [ ] Produire un graphique, un bulletin texte et un bulletin JSON dans `sorties/`
- [ ] Assembler tout le traitement dans une fonction `pipeline` qu'on peut relancer
