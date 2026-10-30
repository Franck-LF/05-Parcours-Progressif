# Module 11 — Tes premiers objets

⏱ Durée estimée : 4 h 15 (cours 1 h 20, exercices 2 h 30, fil rouge 45 min)

## Objectifs

À la fin de ce module, tu sais :
- **reconnaître** les objets, attributs et méthodes que tu utilises déjà (`str`, `DataFrame`) ;
- **écrire** une classe avec `__init__`, `self`, des attributs et des méthodes, et **fabriquer** des objets ;
- **définir** un affichage lisible avec `__repr__`, ou tout générer avec `@dataclass` ;
- **construire** un objet qui contient une liste d'autres objets (une `Station` et ses `Releve`) ;
- **entraîner** et **évaluer** un mini-modèle de prévision avec `fit` et `predict`.

## Prérequis

- Modules 00 à 10 terminés.
- Tu dois savoir faire : une fonction avec `return` et des valeurs par défaut (module 07), une boucle avec un
  accumulateur (module 04), une compréhension de liste (module 05), `to_dict("records")` (module 10).

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-11` dans le studio, à venir.
2. `01-cours.ipynb` : le cours, à exécuter cellule par cellule.
3. `02-exercices.ipynb` : 34 exercices + 5 révisions.
4. `03-fil-rouge.ipynb` : relevés, stations et première prévision MétéoLocale.

## Je sais faire

- [ ] Dire si `meteo.shape` et `meteo.head()` sont un attribut ou une méthode
- [ ] Écrire une classe avec `__init__` et `self`, et fabriquer plusieurs objets
- [ ] Lire et modifier un attribut avec un point
- [ ] Écrire une méthode (avec `self` en premier), avec ou sans paramètre
- [ ] Écrire `__repr__` pour un affichage lisible
- [ ] Écrire la même classe en version `@dataclass`
- [ ] Remplir une `Station` avec des objets `Releve` lus depuis le CSV
- [ ] Entraîner un modèle avec `fit`, prévoir avec `predict`, mesurer son erreur moyenne
- [ ] Lire `TypeError … missing … argument`, `AttributeError` et `takes 0 positional arguments`
