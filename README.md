# Parcours Python progressif : MétéoLocale

Un parcours pour **grands débutants** en formation Data IA : on part d'un ordinateur sans Python et on arrive à
un pipeline de données complet (fichier brut → nettoyage → base SQLite → statistiques → graphique → bulletin).

## Pourquoi ce parcours

L'ancien cours couvrait beaucoup de notions, chacune une seule fois, avec des exercices sans lien entre eux. Les
apprenants oubliaient d'une semaine sur l'autre. Ce parcours fait l'inverse :

| Principe | Concrètement |
|---|---|
| **Un fil rouge** | Tu es stagiaire data chez *MétéoLocale*, une agence qui publie un bulletin pour six villes d'Occitanie. Chaque module ajoute une brique au même projet. |
| **Répéter pour retenir** | Au moins **30 exercices par module**, du plus guidé au plus libre, et 5 exercices de révision des modules précédents. |
| **Prédire avant d'exécuter** | Dans les cours, les cellules 🔮 te demandent ce que le code va afficher avant de l'exécuter. |
| **Les erreurs au programme** | Chaque notion montre les messages d'erreur les plus fréquents et comment les lire. |
| **Vérification immédiate** | Chaque exercice est suivi d'une cellule qui affiche `✅ OK` ou te dit quoi corriger. |

## Par où commencer

1. **[00 — Prérequis et installation](00-prerequis-installation/README.md)** : terminal (Git Bash), uv, Python,
   **environnement virtuel**, VS Code et Jupyter. Rien ne marche sans cette étape : ne la saute pas.
2. Ensuite, les modules dans l'ordre. Dans chaque dossier :
   1. 🎬 la vidéo du module (quand elle est disponible) ;
   2. `01-cours.ipynb` : le cours, à exécuter cellule par cellule ;
   3. `02-exercices.ipynb` : les exercices (30 au minimum) ;
   4. `03-fil-rouge.ipynb` : l'étape MétéoLocale du module ;
   5. la checklist « Je sais faire » du `README.md` du module : tu passes au module suivant quand tout est coché.

## Sommaire

| # | Module | Ce que tu sauras faire | Fil rouge MétéoLocale |
|---|---|---|---|
| 00 | [Prérequis et installation](00-prerequis-installation/) | Ouvrir Git Bash, installer Python avec uv, créer et activer un environnement virtuel, lancer un notebook | Le dossier `meteolocale/` et son `.venv` |
| 01 | [Premiers pas](01-premiers-pas/) | Afficher, calculer, ranger des valeurs dans des variables | La fiche d'une journée à Toulouse |
| 02 | [Les chaînes de caractères](02-chaines/) | Manipuler du texte, convertir, formater avec les f-strings | Lire une ligne brute de relevé |
| 03 | [Les conditions](03-conditions/) | Décider avec `if` / `elif` / `else` | Classer une journée (pluie, vent, chaleur) |
| 04 | [Les boucles](04-boucles/) | Répéter avec `for` et `while`, compter, additionner | Parcourir les 30 jours du mois |
| 05 | [Les listes](05-listes/) | Ranger une série de valeurs et en tirer des statistiques | Les températures de Toulouse |
| 06 | [Les dictionnaires](06-dictionnaires/) | Décrire une ligne de tableau, puis un tableau entier | Le jeu de données en mémoire |
| 07 | [Les fonctions](07-fonctions/) | Écrire ses propres outils réutilisables | Ranger le code du bulletin |
| 08 | [Fichiers et erreurs](08-fichiers-erreurs/) | Lire et écrire CSV/JSON, gérer les erreurs | Charger et nettoyer le vrai fichier |
| 09 | [Modules et API](09-modules-api/) | Importer, installer un paquet, interroger une API | Les prévisions Open-Meteo |
| 10 | [pandas et graphiques](10-pandas-visualisation/) | Analyser un tableau avec pandas, tracer avec matplotlib | Le bulletin mensuel illustré |
| 11 | [Les objets](11-objets/) | Créer une classe, comprendre `fit` / `predict` | Un mini-modèle de prévision |
| 12 | [SQLite](12-sqlite/) | Stocker et interroger des données en base | L'historique en base |
| 13 | [Projet final](13-projet-final/) | Enchaîner tout le pipeline seul | Le bulletin complet |

## Les données

Le dossier [`donnees/`](donnees/) contient des données **fictives**, partagées par tous les modules :

- `meteo.csv` : 180 relevés propres (6 villes × 30 jours de septembre 2026) ;
- `meteo_brut.csv` : les mêmes relevés, abîmés exprès (séparateur `;`, virgules décimales, cases vides, `N/A`,
  doublons), pour apprendre à nettoyer ;
- `open_meteo_toulouse.json` : une réponse enregistrée de l'API Open-Meteo, pour travailler sans réseau.

## Pour le formateur

- **Corrigés** : dans le dépôt `formation-corrections`, même chemin, fichiers `*-CORRIGE.ipynb`.
- **Testé par un apprenant simulé** : chaque module a été passé par un agent IA qui joue une grande débutante
  (Sandrine, profil du studio vidéo) et n'utilise que ce que le cours montre ; ses blocages ont été corrigés.
- **Vidéos** : les scénarios sont dans le studio (`termup-studio-formation/contenu/python-debutant/`), un
  épisode par module, à faire passer par la relecture des apprenants simulés du studio puis au tournage.
- **Rythme conseillé** : un module par demi-journée à une journée. Ouvre chaque séance par 10 minutes de
  révisions espacées (les exercices 🔁 du module en cours), sans notes.
