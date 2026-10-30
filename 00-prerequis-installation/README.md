# Module 00 — Prérequis et installation

🟢 Débutant | ⏱ 2 h 30 à 3 h (installation comprise) | 🔑 terminal, Git Bash, uv, environnement virtuel, notebook, kernel

Avant d'écrire la moindre ligne de Python, on prépare le poste de travail. C'est le module le plus « technique »
du parcours, et pourtant il ne demande **aucune** connaissance : il suffit de suivre les étapes dans l'ordre.

## Objectifs

À la fin de ce module, tu sauras :

1. **Ouvrir** un terminal (Git Bash sur Windows) et t'y déplacer avec `pwd`, `ls`, `cd`, `mkdir`.
2. **Installer** Python 3.13 avec uv.
3. **Créer**, **activer** et **désactiver** l'environnement virtuel d'un projet, et vérifier lequel est actif.
4. **Ouvrir** un notebook dans VS Code, **choisir** le kernel `.venv` et **exécuter** des cellules dans l'ordre.
5. **Relancer** le kernel quand le notebook se comporte bizarrement.

## Prérequis

- Modules à avoir faits : aucun. C'est le point de départ.
- Tu dois savoir faire : allumer ton ordinateur, utiliser un navigateur web, télécharger un fichier, ouvrir un
  dossier avec l'explorateur de fichiers (ou le Finder sur Mac).
- Il te faut : un ordinateur Windows 10/11, macOS ou Linux (Ubuntu/Debian), une connexion Internet, et les droits
  pour installer des logiciels (si ton ordinateur est géré par une entreprise, préviens ton formateur).

## Ordre de travail

1. 🎬 Vidéo : scénario `python-debutant-00` dans le studio, à venir (pas encore disponible : passe à l'étape suivante).
2. 📘 **[GUIDE-INSTALLATION.md](GUIDE-INSTALLATION.md)** : l'installation complète, pas à pas, pour Windows, macOS et
   Linux. Suis-le **en entier** avant d'ouvrir un notebook (sans lui, aucun notebook ne s'exécute).
3. `01-cours.ipynb` : ce qu'est un notebook, une cellule, le kernel ; les gestes du terminal à retenir.
4. `02-exercices.ipynb` : 34 exercices qui répètent les gestes du terminal et de l'environnement virtuel. Tu tapes
   les commandes dans Git Bash, et une cellule du notebook vérifie le résultat sur ton disque.
5. `03-fil-rouge.ipynb` : on vérifie que le projet MétéoLocale est prêt pour la suite.

> Les exercices travaillent uniquement dans `~/meteolocale/bac-a-sable/` : tu peux y faire toutes les erreurs que
> tu veux, rien d'autre n'est touché.

## ✅ Je sais faire

- [ ] Ouvrir Git Bash (ou le Terminal) et dire où je suis avec `pwd`
- [ ] Lister un dossier avec `ls` et `ls -a`, entrer dans un dossier avec `cd`, remonter avec `cd ..`
- [ ] Créer un dossier avec `mkdir`, et une arborescence avec `mkdir -p`
- [ ] Créer un environnement virtuel avec `uv venv --python 3.13`
- [ ] L'activer avec `source` (`Scripts` sur Windows, `bin` ailleurs) et le reconnaître dans le prompt
- [ ] Vérifier le Python utilisé avec `which python` et `python --version`, puis `deactivate`
- [ ] Installer des paquets dans l'environnement avec `uv pip install`
- [ ] Ouvrir un notebook dans VS Code et choisir le kernel `.venv`
- [ ] Exécuter une cellule avec `Maj + Entrée` et relancer le kernel (Restart)
