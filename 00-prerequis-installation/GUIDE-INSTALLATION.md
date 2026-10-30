# Guide d'installation pas à pas

🟢 Débutant | ⏱ 1 h à 1 h 30 (la première fois) | 💻 Windows, macOS, Linux (Ubuntu/Debian)

Ce guide installe **tout** ce qu'il faut pour le parcours, dans un ordre précis. Suis les étapes **dans l'ordre**,
sans en sauter : chaque étape a besoin de la précédente.

À la fin, tu auras :

- un **terminal** (Git Bash sur Windows, le Terminal sur macOS et Linux) ;
- **VS Code**, l'éditeur dans lequel tu ouvriras les notebooks ;
- **uv**, l'outil qui installe Python ;
- **Python 3.13** ;
- le dossier du projet **`meteolocale`**, avec son **environnement virtuel** `.venv` ;
- les paquets du parcours (Jupyter, pandas, matplotlib, requests) installés **dans** cet environnement ;
- un premier notebook qui s'exécute.

> **Comment lire ce guide**
>
> - Les blocs gris comme celui-ci contiennent une **commande** à taper dans le terminal :
>
>   ```bash
>   pwd
>   ```
>
>   Tu tapes le texte (ou tu le colles), puis tu appuies sur la touche **Entrée**.
> - Quand une étape est différente selon ton système, elle est découpée en trois paragraphes :
>   **🪟 Windows**, **🍎 macOS**, **🐧 Linux**. Lis seulement le tien.
> - Chaque étape finit par une **✅ vérification**. Ne passe à l'étape suivante que si elle donne le bon
>   résultat. Sinon, va voir la section [« Ça ne marche pas »](#9-ça-ne-marche-pas) en bas de page.

---

## Sommaire

0. [Les mots à connaître avant de commencer](#0-les-mots-à-connaître-avant-de-commencer)
1. [Ouvrir un terminal (Git Bash)](#1-ouvrir-un-terminal-git-bash)
2. [Installer VS Code et ses extensions](#2-installer-vs-code-et-ses-extensions)
3. [Installer uv](#3-installer-uv)
4. [Installer Python avec uv](#4-installer-python-avec-uv)
5. [Créer l'environnement virtuel du projet (le plus important)](#5-créer-lenvironnement-virtuel-du-projet)
6. [Récupérer le parcours et installer les paquets](#6-récupérer-le-parcours-et-installer-les-paquets)
7. [Ouvrir le projet dans VS Code et exécuter une cellule](#7-ouvrir-le-projet-dans-vs-code-et-exécuter-une-cellule)
8. [Plan B : installer sans uv](#8-plan-b--installer-sans-uv)
9. [Ça ne marche pas](#9-ça-ne-marche-pas)
10. [Aide-mémoire](#10-aide-mémoire)

---

## 0. Les mots à connaître avant de commencer

| Mot | Ce que ça veut dire | Image de la vie de bureau |
|---|---|---|
| **Dossier** | Un rangement qui contient des fichiers et d'autres dossiers. | Un classeur. |
| **Fichier** | Un document : un texte, un tableau, une image, un notebook… | Une feuille dans le classeur. |
| **Chemin** | L'adresse d'un fichier ou d'un dossier, dossier par dossier, séparés par `/`. Exemple : `/home/sandrine/meteolocale`. | L'adresse postale : pays / ville / rue / numéro. |
| **Dossier personnel** | Ton dossier à toi sur l'ordinateur. Dans le terminal, il s'écrit `~` (le *tilde*). | Ton bureau dans l'agence. |
| **Terminal** | Une fenêtre où l'on donne des ordres à l'ordinateur **en tapant du texte**, au lieu de cliquer. | Le guichet où tu dictes une demande à un employé très rapide mais très pointilleux. |
| **Commande** | Un ordre tapé dans le terminal, par exemple `pwd`. | La demande que tu dictes. |
| **Prompt** (invite) | Le début de ligne que le terminal affiche tout seul, qui finit par `$`. Il veut dire : « je suis prêt, tape ta commande ». | L'employé qui lève la tête : « Suivant ! » |
| **Python** | Un langage de programmation : une façon d'écrire des instructions que l'ordinateur sait suivre. | Une langue que l'employé comprend. |
| **Paquet** | Un ensemble d'outils écrits par d'autres, qu'on ajoute à Python (exemple : `pandas` pour les tableaux). | Une boîte à outils qu'on achète en plus. |
| **Environnement virtuel** | Un dossier (`.venv`) qui contient **une copie de Python réservée à un projet**, avec ses propres paquets. | Une trousse par matière, à l'école : la trousse de dessin ne se mélange pas avec celle de maths. |

Pas besoin de tout retenir maintenant : ces mots reviendront à chaque étape.

---

## 1. Ouvrir un terminal (Git Bash)

**Règle du parcours : on tape toutes les commandes dans le même terminal.** Sur Windows, ce sera **Git Bash**.
Sur macOS et Linux, ce sera le **Terminal** déjà installé. Les commandes sont **les mêmes** partout (sauf deux,
signalées le moment venu).

### 1.1 Installer ou ouvrir le terminal

**🪟 Windows : installer Git for Windows (qui contient Git Bash)**

1. Va sur **https://git-scm.com/downloads/win** et clique sur le premier lien de téléchargement
   (« Click here to download »). Un fichier `Git-…-64-bit.exe` se télécharge.
2. Double-clique dessus. Windows demande « Voulez-vous autoriser cette application… » : clique sur **Oui**.
3. L'installateur pose beaucoup de questions, en anglais. **Garde tous les choix proposés par défaut** : clique sur
   **Next** à chaque écran, puis **Install**. (Si un écran te demande l'éditeur par défaut, tu peux choisir
   « Use Visual Studio Code as Git's default editor » ; sinon garde le choix proposé.)
4. À la fin, décoche « View Release Notes » et clique sur **Finish**.
5. Ouvre le menu **Démarrer**, tape `Git Bash` et clique sur **Git Bash**. Une fenêtre noire s'ouvre : c'est ton
   terminal.

**🍎 macOS : ouvrir le Terminal, puis installer Git**

1. Appuie sur **Cmd + Espace** (la loupe Spotlight s'ouvre), tape `Terminal`, puis **Entrée**. Une fenêtre s'ouvre :
   c'est ton terminal.
2. Tape la commande suivante, puis **Entrée** :

   ```bash
   xcode-select --install
   ```

3. Une fenêtre propose d'installer les « outils de ligne de commande » : clique sur **Installer**, puis accepte la
   licence. Compte 5 à 15 minutes. Si le terminal répond `command line tools are already installed`, c'est
   qu'ils sont déjà là : parfait, rien à faire.

**🐧 Linux (Ubuntu / Debian) : ouvrir le Terminal, puis installer Git et curl**

1. Appuie sur **Ctrl + Alt + T** (ou cherche « Terminal » dans les applications).
2. Tape la commande suivante, puis **Entrée** :

   ```bash
   sudo apt update && sudo apt install -y git curl
   ```

   Ce sont deux commandes sur une ligne : `&&` veut dire « puis, si ça a marché ». `sudo` (« fais-le en
   administrateur ») demande ton mot de passe de session. **Pendant que tu le tapes, rien ne s'affiche** (pas même des
   étoiles) : c'est normal. Tape-le puis **Entrée**.

✅ **Vérification** (tous les systèmes) : tape

```bash
git --version
```

Le terminal répond par exemple `git version 2.47.1`. Le numéro exact n'a pas d'importance. **Git** est un outil
qui garde l'historique des versions de tes fichiers ; on s'en servira plus tard dans la formation. Pour
l'instant, il nous sert surtout à avoir **Git Bash** sur Windows.

### 1.2 Lire le terminal

Quand le terminal est prêt, il affiche une ligne qui ressemble à ceci :

```
sandrine@PC-SANDRINE MINGW64 ~
$
```

- Ce début de ligne s'appelle le **prompt** (l'invite). Il s'affiche tout seul : **tu ne le tapes jamais**.
- Le `~` indique **où tu es** : ici, dans ton dossier personnel.
- Le `$` veut dire « à toi ». Tu tapes ta commande **après** le `$`, puis tu appuies sur **Entrée**.

Dans ce guide, quand un bloc commence par `$`, le `$` représente le prompt : ne le recopie pas.

Le terminal est **pointilleux** : une lettre de travers, une majuscule à la place d'une minuscule ou un espace
oublié, et la commande échoue. Ce n'est pas grave : relis, corrige, recommence.

### 1.3 Copier et coller dans le terminal

Recopier les commandes à la main fait des fautes. Copie-les plutôt depuis ce guide.

| Système | Coller dans le terminal |
|---|---|
| 🪟 Git Bash | **Maj + Inser**, ou **clic droit → Paste**. ⚠️ `Ctrl + V` ne marche pas toujours dans Git Bash. |
| 🍎 macOS | **Cmd + V** |
| 🐧 Linux | **Ctrl + Maj + V** (avec la touche Maj !) |

Pour **copier** du texte affiché dans Git Bash : sélectionne-le à la souris, il est copié automatiquement.

> ⚠️ Dans le terminal, **Ctrl + C ne copie pas** : il **interrompt** la commande en cours. C'est utile quand une
> commande ne s'arrête pas, mais ce n'est pas un copier.

Autres touches utiles :

- **Flèche du haut** : rappelle la commande précédente (pratique pour la corriger sans tout retaper).
- **Tab** : complète un nom de dossier ou de fichier. Tape `cd met` puis **Tab** : le terminal écrit
  `cd meteolocale/` tout seul (si le dossier existe).

### 1.4 Tes quatre premières commandes : `pwd`, `ls`, `cd`, `mkdir`

Essaie chacune dans ton terminal.

**`pwd` : où suis-je ?** (*print working directory* : affiche le dossier de travail)

```bash
pwd
```

Réponse : un chemin, par exemple `/c/Users/sandrine` (Windows), `/Users/sandrine` (macOS) ou
`/home/sandrine` (Linux). C'est ton dossier personnel.

**`ls` : qu'y a-t-il ici ?** (*list* : liste le contenu du dossier)

```bash
ls
```

Réponse : les noms des dossiers et fichiers présents (Documents, Desktop…).

**`mkdir` : créer un dossier** (*make directory*)

```bash
mkdir essai
```

Rien ne s'affiche : **pas de nouvelle, bonne nouvelle**. En informatique, une commande qui réussit est souvent
silencieuse. Vérifie avec `ls` : `essai` apparaît dans la liste.

**`cd` : entrer dans un dossier** (*change directory*)

```bash
cd essai
pwd
```

`pwd` répond maintenant `…/essai` : tu es entré dans le dossier. Le prompt affiche aussi `~/essai`.

Pour **remonter** d'un cran (sortir du dossier) :

```bash
cd ..
```

`..` (deux points) veut dire « le dossier juste au-dessus ». Et pour revenir chez toi d'où que tu sois :

```bash
cd ~
```

✅ **Vérification** : `pwd` affiche ton dossier personnel, et `ls` montre le dossier `essai`. Tu peux le laisser,
il ne gêne pas.

---

## 2. Installer VS Code et ses extensions

**VS Code** (Visual Studio Code) est un **éditeur de code** : un traitement de texte spécialisé pour écrire des
programmes. C'est dans VS Code que tu ouvriras les notebooks du parcours.

### 2.1 Installer VS Code

**🪟 Windows**

1. Va sur **https://code.visualstudio.com** et clique sur **Download for Windows**.
2. Lance le fichier téléchargé. Accepte la licence, puis **garde les options par défaut**. Vérifie que la case
   **« Ajouter à PATH »** (*Add to PATH*) est **cochée** (elle l'est par défaut). Elle permet d'ouvrir VS Code
   depuis le terminal avec la commande `code`.
3. Termine l'installation. **Ferme Git Bash et rouvre-le** (une installation n'est visible que dans les
   terminaux ouverts **après** elle).

**🍎 macOS**

1. Va sur **https://code.visualstudio.com** et clique sur **Download for Mac**.
2. Ouvre le fichier `.zip` téléchargé : il contient l'application **Visual Studio Code**. Fais-la glisser dans le
   dossier **Applications** (dans le Finder).
3. Lance VS Code depuis Applications.
4. Pour pouvoir l'ouvrir depuis le terminal : dans VS Code, appuie sur **Cmd + Maj + P**, tape
   `shell command`, et choisis **Shell Command: Install 'code' command in PATH**. Puis ferme et rouvre le
   Terminal.

**🐧 Linux (Ubuntu / Debian)**

1. Va sur **https://code.visualstudio.com** et télécharge le fichier **.deb**.
2. Dans le terminal, va dans le dossier des téléchargements et installe-le (remplace le nom par celui de ton
   fichier, la touche **Tab** le complète pour toi) :

   ```bash
   cd ~/Téléchargements
   sudo apt install ./code_*.deb
   ```

   (Si ton système est en anglais, le dossier s'appelle `~/Downloads`.)

### 2.2 Installer les extensions Python et Jupyter

Une **extension** est un module qu'on ajoute à VS Code pour lui apprendre un nouveau métier.

1. Dans VS Code, clique sur l'icône **Extensions** dans la barre de gauche (quatre petits carrés), ou appuie sur
   **Ctrl + Maj + X** (macOS : **Cmd + Maj + X**).
2. Dans la barre de recherche, tape `Python`. Choisis l'extension **Python** dont l'éditeur est **Microsoft**
   (badge bleu de vérification) et clique sur **Install**.
3. Recherche ensuite `Jupyter` et installe l'extension **Jupyter**, de **Microsoft** elle aussi.

> ⚠️ Plusieurs extensions portent des noms proches. Vérifie bien que l'éditeur affiché sous le nom est
> **Microsoft**.

### 2.3 🪟 Windows seulement : Git Bash comme terminal de VS Code

VS Code a un terminal intégré (en bas de la fenêtre). Sur Windows, il ouvre PowerShell par défaut. On veut
**Git Bash**, pour taper les mêmes commandes partout :

1. Dans VS Code, appuie sur **Ctrl + Maj + P**, tape `default profile` et choisis
   **Terminal: Select Default Profile**.
   (VS Code en français : tape `profil par défaut` et choisis **Terminal : Sélectionner le profil par défaut**.)
2. Choisis **Git Bash**.

✅ **Vérification** : dans le terminal (Git Bash, ou Terminal sur macOS/Linux), tape

```bash
code --version
```

Il affiche trois lignes, dont un numéro de version (par exemple `1.95.3`). Si le terminal répond
`command not found`, ferme-le et rouvre-le, puis réessaie (voir [« Ça ne marche pas »](#9-ça-ne-marche-pas)).

---

## 3. Installer uv

**uv** est l'outil qui va **installer Python** pour toi et **gérer les environnements virtuels**. Une seule
commande pour chaque besoin, la même sur Windows, macOS et Linux.

**🪟 Windows** : cette commande-là se tape **une seule fois**, et **dans PowerShell** (pas dans Git Bash).

1. Ouvre le menu **Démarrer**, tape `PowerShell` et clique sur **Windows PowerShell** (une fenêtre bleue ou
   noire).
2. Copie-colle cette ligne (clic droit pour coller dans PowerShell), puis **Entrée** :

   ```powershell
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

3. Attends la ligne `everything's installed!`. Ferme PowerShell : tu n'en auras plus besoin.
4. **Ferme toutes les fenêtres Git Bash et rouvre Git Bash.** C'est indispensable : Git Bash ne voit uv qu'après
   avoir été rouvert.

**🍎 macOS et 🐧 Linux** : dans le Terminal, copie-colle cette ligne, puis **Entrée** :

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

(`curl` télécharge le programme d'installation, `sh` l'exécute.) Attends `everything's installed!`, puis **ferme
le terminal et rouvre-le**.

✅ **Vérification** (tous les systèmes, dans un terminal **rouvert**) :

```bash
uv --version
```

Réponse attendue : `uv 0.x.y` (un numéro de version). Si tu lis `uv: command not found`, c'est presque toujours
que le terminal n'a pas été rouvert : ferme-le **complètement** et rouvre-le.

---

## 4. Installer Python avec uv

Le parcours utilise **Python 3.13**. uv l'installe pour toi :

```bash
uv python install 3.13
```

Le téléchargement prend une à deux minutes. Puis vérifie :

✅ **Vérification** :

```bash
uv python list
```

Une des lignes contient `cpython-3.13` suivi d'un chemin (et non `<download available>`) : Python 3.13 est
installé.

> **Et si j'avais déjà un autre Python ?** Ce n'est pas grave : uv installe le sien à côté, sans toucher à
> l'autre. Et grâce à l'environnement virtuel (étape suivante), le projet saura toujours lequel utiliser.

---

## 5. Créer l'environnement virtuel du projet

> ⭐ **L'étape la plus importante du guide.** On la fait **avant d'écrire la moindre ligne de Python**. La
> plupart des « ça ne marche pas » des débutants viennent d'un environnement virtuel oublié ou mal choisi.

### 5.1 Pourquoi un environnement virtuel ?

À l'école, tu avais une trousse par matière : la trousse de dessin avec ses feutres, celle de géométrie avec son
compas. Rien ne se mélange, et si tu perds la trousse de dessin, la géométrie continue.

Un **environnement virtuel**, c'est la trousse d'**un** projet : un dossier nommé `.venv` qui contient **sa propre
copie de Python** et **ses propres paquets**, dans des versions choisies pour ce projet. Deux projets peuvent
ainsi utiliser deux versions différentes de pandas sans se gêner, et si un environnement est abîmé, on le
supprime et on le recrée en une commande, sans risque pour le reste de l'ordinateur.

Règle du parcours : **un projet = un dossier = un `.venv` dedans.**

### 5.2 Créer le dossier du projet

Notre projet s'appelle `meteolocale`. On le crée dans ton dossier personnel, puis on entre dedans :

```bash
mkdir -p ~/meteolocale
cd ~/meteolocale
```

`-p` est une **option** (un réglage de la commande, écrit après un tiret) : elle dit à `mkdir` de ne pas
protester si le dossier existe déjà, et de créer au passage les dossiers intermédiaires s'il en manque.

✅ `pwd` doit afficher un chemin qui finit par `/meteolocale`.

### 5.3 Créer l'environnement virtuel

Toujours dans `~/meteolocale` :

```bash
uv venv --python 3.13
```

uv répond quelque chose comme :

```
Using CPython 3.13.x
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
```

> 🪟 **Windows** : uv écrit peut-être `Activate with: source .venv/bin/activate` ou `.venv\Scripts\activate`.
> **Dans Git Bash sous Windows, le dossier s'appelle toujours `Scripts`** : la bonne commande sera
> `source .venv/Scripts/activate` (étape 5.4). Ne recopie pas le `bin` affiché.

Le dossier `.venv` vient d'être créé. Son nom commence par un point : c'est un **dossier caché**, `ls` ne le
montre pas. Pour voir aussi les éléments cachés, ajoute l'option `-a` (*all*, tout) :

```bash
ls -a
```

✅ Tu vois `.venv` dans la liste.

### 5.4 Activer l'environnement virtuel

**Activer** l'environnement, c'est dire au terminal : « à partir de maintenant, quand je dis `python`, utilise
celui de la trousse `.venv` ». C'est **ici** que Windows est différent :

**🪟 Windows (Git Bash)** :

```bash
source .venv/Scripts/activate
```

**🍎 macOS et 🐧 Linux** :

```bash
source .venv/bin/activate
```

(`source` lit un fichier de réglages et l'applique au terminal. Sur Windows le dossier s'appelle `Scripts`, ailleurs
`bin` : c'est la seule différence.)

Le prompt change : il commence maintenant par **`(meteolocale)`** (ou `(.venv)` selon la version de uv).

```
(meteolocale) sandrine@PC-SANDRINE MINGW64 ~/meteolocale
$
```

**Ce petit mot entre parenthèses est ton témoin** : tant qu'il est là, l'environnement est actif.

✅ **Vérification** : demande au terminal quel Python il utilise. `which` (« lequel ? ») affiche le chemin d'une
commande :

```bash
which python
```

Le chemin affiché doit **contenir `meteolocale/.venv`**, par exemple :

- 🪟 `/c/Users/sandrine/meteolocale/.venv/Scripts/python`
- 🍎 `/Users/sandrine/meteolocale/.venv/bin/python`
- 🐧 `/home/sandrine/meteolocale/.venv/bin/python`

Puis :

```bash
python --version
```

Réponse attendue : `Python 3.13.x`.

### 5.5 Désactiver, puis réactiver

Pour quitter l'environnement (rendre la trousse) :

```bash
deactivate
```

`(meteolocale)` disparaît du prompt. Réactive-le tout de suite avec la commande `source` de l'étape 5.4 : on en a
besoin pour la suite.

> 🔁 **À chaque nouvelle séance** : ouvre le terminal, puis
>
> ```bash
> cd ~/meteolocale
> source .venv/Scripts/activate      # 🪟 Windows
> source .venv/bin/activate          # 🍎 macOS / 🐧 Linux
> ```
>
> Un terminal neuf n'a **jamais** l'environnement actif : il faut le réactiver à chaque fois.

---

## 6. Récupérer le parcours et installer les paquets

### 6.1 Mettre le parcours dans le projet

Ton formateur te donne un lien vers un fichier **`00-Parcours-Progressif.zip`**. Un `.zip` est une **archive** :
un dossier compressé en un seul fichier, qu'il faut **extraire** (décompresser) pour s'en servir. Il contient les
modules, les données et un fichier `requirements.txt`. (Pas de lien ? Demande-le à ton formateur avant de continuer :
la suite en a besoin.)

**But** : obtenir **exactement** ce rangement, avec `00-Parcours-Progressif` directement dans `meteolocale` :

```
meteolocale/
├── .venv/
└── 00-Parcours-Progressif/
    ├── 00-prerequis-installation/
    ├── 01-premiers-pas/
    ├── …
    ├── donnees/
    └── requirements.txt
```

**🪟 Windows**

1. Clique sur le lien : le fichier `00-Parcours-Progressif.zip` arrive dans ton dossier **Téléchargements**.
2. Ouvre l'**Explorateur de fichiers** (icône de dossier jaune dans la barre des tâches), va dans
   **Téléchargements**, fais un **clic droit** sur `00-Parcours-Progressif.zip` → **Extraire tout…**
3. Une fenêtre demande où extraire. Dans la case du chemin, **efface tout** et écris :
   `C:\Users\<ton nom>\meteolocale` (remplace `<ton nom>` par ton nom de session, celui que tu vois dans
   `pwd` : `/c/Users/sandrine` → `C:\Users\sandrine\meteolocale`). Clique sur **Extraire**.

**🍎 macOS**

1. Clique sur le lien : le fichier arrive dans **Téléchargements**. Safari l'extrait souvent tout seul ; sinon,
   double-clique dessus dans le Finder. Un dossier `00-Parcours-Progressif` apparaît dans Téléchargements.
2. Ouvre une **deuxième** fenêtre du Finder (**Cmd + N**), menu **Aller → Départ**, puis ouvre `meteolocale`.
3. Fais **glisser** le dossier `00-Parcours-Progressif` de Téléchargements vers la fenêtre `meteolocale`.

**🐧 Linux**

1. Clique sur le lien : le fichier arrive dans `~/Téléchargements` (ou `~/Downloads`).
2. Dans le gestionnaire de fichiers, clic droit sur le `.zip` → **Extraire ici**, puis fais glisser le dossier
   `00-Parcours-Progressif` obtenu dans `meteolocale` (dans ton dossier personnel).

✅ **Vérification** (tous les systèmes) : dans le terminal, tape

```bash
ls ~/meteolocale/00-Parcours-Progressif
```

**Résultat attendu** (l'ordre peut varier un peu) :

```
00-prerequis-installation  02-chaines     04-boucles  …  README.md  donnees  requirements.txt
01-premiers-pas            03-conditions  05-listes   …
```

Tu vois `requirements.txt` et `donnees` : c'est bon, passe à l'étape 6.2.

> ⚠️ **Le piège du dossier dans le dossier.** Si la commande affiche **seulement** `00-Parcours-Progressif`, l'extraction
> a créé deux niveaux : `meteolocale/00-Parcours-Progressif/00-Parcours-Progressif/…`. Pour remonter le bon dossier
> d'un cran, copie-colle ces quatre lignes, une par une (`mv` = *move*, déplacer ; `rmdir` supprime un dossier vide) :
>
> ```bash
> cd ~/meteolocale
> mv 00-Parcours-Progressif emballage
> mv emballage/00-Parcours-Progressif .
> rmdir emballage
> ```
>
> Puis refais la vérification. (Si `rmdir` répond `Directory not empty`, ce n'est pas grave : supprime le dossier
> `emballage` à la souris.)
>
> Si la commande répond `No such file or directory`, le dossier n'est pas dans `meteolocale` ou porte un autre nom
> (par exemple `00-Parcours-Progressif (1)`). Tape `ls ~/meteolocale` pour voir ce qu'il y a, puis, avec
> l'explorateur, renomme le dossier qui contient `requirements.txt` en `00-Parcours-Progressif` (exactement) et
> range-le dans `meteolocale`.

### 6.2 Installer les paquets dans l'environnement virtuel

Le fichier `requirements.txt` est une **liste de courses** : un nom de paquet par ligne (jupyterlab, ipykernel,
pandas, matplotlib, requests). uv lit la liste et installe tout **dans le `.venv`** du projet.

Vérifie d'abord que `(meteolocale)` est bien au début du prompt (sinon, réactive : étape 5.4), puis :

```bash
uv pip install -r 00-Parcours-Progressif/requirements.txt
```

(`-r` veut dire « lis la liste dans ce fichier ».) Astuce : tape `uv pip install -r 00` puis **Tab** pour
compléter le nom du dossier.

L'installation prend une à trois minutes et finit par une liste de lignes qui commencent par `+`.

✅ **Vérification** :

```bash
uv pip list
```

La liste contient (entre autres) `ipykernel`, `jupyterlab`, `matplotlib`, `pandas` et `requests`.

> À quoi servent-ils ? **jupyterlab** et **ipykernel** font fonctionner les notebooks ; **pandas** manipule des
> tableaux ; **matplotlib** dessine des graphiques ; **requests** télécharge des données sur Internet. Tu les
> découvriras un par un au fil des modules.

---

## 7. Ouvrir le projet dans VS Code et exécuter une cellule

### 7.1 Ouvrir le dossier du projet

Depuis `~/meteolocale` :

```bash
code .
```

Le point `.` veut dire « le dossier où je suis ». VS Code s'ouvre sur `meteolocale`. S'il demande
« Do you trust the authors of the files in this folder? », clique sur **Yes, I trust the authors** : c'est ton
propre dossier.

Dans la colonne de gauche (l'**explorateur**), tu vois `.venv` et `00-Parcours-Progressif`.

### 7.2 Ouvrir un notebook

Un **notebook** est un document qui mélange du texte et des morceaux de code qu'on peut exécuter. Son nom finit par
`.ipynb`.

Dans l'explorateur, déplie `00-Parcours-Progressif` → `00-prerequis-installation` et clique sur
**`01-cours.ipynb`**.

### 7.3 Choisir le kernel `.venv` (à ne pas rater)

Le **kernel** (le « noyau ») est le moteur qui exécute le code du notebook. Il faut dire à VS Code d'utiliser
**le Python de ton environnement virtuel**.

1. En haut à droite du notebook, clique sur **Select Kernel** (ou sur le nom d'un kernel déjà affiché).
2. Choisis **Python Environments…**
3. Choisis la ligne qui contient **`.venv`** et le chemin **`meteolocale/.venv`** (souvent marquée
   *Recommended*).

En haut à droite, tu lis maintenant **`.venv (Python 3.13.x)`**.

> Si `.venv` n'apparaît pas : vérifie que tu as bien ouvert le dossier `meteolocale` avec `code .` (et pas
> seulement le fichier), puis ferme et rouvre VS Code. Voir aussi [« Ça ne marche pas »](#9-ça-ne-marche-pas).

### 7.4 Exécuter ta première cellule

Dans le notebook, clique dans la première cellule de code (un cadre gris), puis appuie sur **Maj + Entrée**
(*Shift + Enter*). Le résultat s'affiche juste en dessous. 🎉

✅ **Vérification finale** : le cours `01-cours.ipynb` contient une cellule « Vérifier le kernel ». Exécute-la : le
chemin affiché doit contenir `meteolocale/.venv`.

**Bravo : ton poste est prêt.** Retourne au [README du module](README.md) pour la suite.

---

## 8. Plan B : installer sans uv

À utiliser **seulement** si l'étape 3 (uv) est impossible sur ton ordinateur (poste d'entreprise verrouillé, par
exemple). On remplace uv par l'installateur officiel de Python.

1. **Installer Python 3.13** depuis **https://www.python.org/downloads/**.
   - 🪟 Windows : lance l'installateur et, **sur le tout premier écran, coche la case
     « Add python.exe to PATH »** en bas de la fenêtre, **avant** de cliquer sur **Install Now**. Si tu l'as oubliée,
     relance l'installateur et choisis **Modify**. Puis rouvre Git Bash.
   - 🍎 macOS : lance le fichier `.pkg` et suis les écrans. La commande s'appelle alors `python3`.
   - 🐧 Linux : `sudo apt install -y python3 python3-venv python3-pip`. La commande s'appelle `python3`.
2. **Créer l'environnement virtuel** :

   ```bash
   mkdir -p ~/meteolocale
   cd ~/meteolocale
   python -m venv .venv          # 🪟 Windows
   python3 -m venv .venv         # 🍎 macOS / 🐧 Linux
   ```

3. **L'activer** exactement comme à l'étape 5.4 (`source .venv/Scripts/activate` ou `source .venv/bin/activate`).
   Une fois activé, la commande s'appelle `python` partout.
4. **Installer les paquets** (après avoir placé le parcours, étape 6.1) :

   ```bash
   pip install -r 00-Parcours-Progressif/requirements.txt
   ```

5. Reprends à l'étape 7.

Dans la suite du parcours, quand tu lis `uv pip install …`, tape simplement `pip install …` (environnement activé).

---

## 9. Ça ne marche pas

Lis d'abord **la dernière ligne** du message d'erreur : c'est presque toujours elle qui dit l'essentiel.

| Symptôme | Cause probable | Solution |
|---|---|---|
| `bash: uv: command not found` juste après l'installation de uv | Le terminal était ouvert **avant** l'installation : il ne connaît pas encore uv. | Ferme **toutes** les fenêtres du terminal (et VS Code), rouvre, retape `uv --version`. |
| `bash: code: command not found` | 🪟 La case « Add to PATH » de VS Code était décochée, ou Git Bash n'a pas été rouvert. 🍎 La commande `code` n'a pas été installée. | 🪟 Rouvre Git Bash ; sinon réinstalle VS Code en cochant la case. 🍎 Étape 2.1, point 4. En attendant : ouvre VS Code et fais **File → Open Folder** sur `meteolocale`. |
| `bash: <nom>: command not found` sur une autre commande | Faute de frappe (majuscule, lettre oubliée, espace en trop). | Relis la commande lettre par lettre. Utilise la flèche du haut pour la corriger. |
| `No such file or directory` | Tu n'es pas dans le bon dossier, ou le nom est mal écrit. | `pwd` pour voir où tu es, `ls` pour voir ce qu'il y a. Puis `cd ~/meteolocale`. |
| `source .venv/bin/activate` → `No such file or directory` sur Windows | Sur Windows, le dossier s'appelle `Scripts`, pas `bin`. | `source .venv/Scripts/activate` |
| Pas de `(meteolocale)` au début du prompt | L'environnement n'est pas activé (terminal neuf, ou `source` oublié). | `cd ~/meteolocale` puis la commande `source` de l'étape 5.4. |
| `which python` n'affiche pas `meteolocale/.venv` | Même cause : environnement non activé. | Active-le, puis réessaie. |
| 🪟 Taper `python` ouvre le **Microsoft Store** | Windows a un faux raccourci « python » qui redirige vers le Store. | Menu Démarrer → **Paramètres** → **Applications** → **Paramètres avancés des applications** → **Alias d'exécution d'application** : désactive les lignes **python.exe** et **python3.exe**. Rouvre Git Bash. Avec l'environnement activé, `python` marchera. |
| `uv pip install` répond `No virtual environment found` | Tu n'es pas dans `~/meteolocale` (là où se trouve `.venv`). | `cd ~/meteolocale`, active l'environnement, recommence. |
| `File not found: …requirements.txt` | Le chemin du fichier est faux, ou le parcours n'est pas dans `meteolocale`. | `ls 00-Parcours-Progressif` doit montrer `requirements.txt`. Sinon, refais l'étape 6.1. |
| Dans le notebook : `ModuleNotFoundError: No module named 'pandas'` | Le notebook utilise **le mauvais kernel** (un autre Python, sans les paquets). | En haut à droite du notebook, clique sur le kernel et choisis `.venv` de `meteolocale` (étape 7.3). |
| VS Code demande d'installer `ipykernel` | Les paquets n'ont pas été installés dans le `.venv`, ou le mauvais kernel est choisi. | Refais l'étape 6.2 (environnement activé), puis rechoisis le kernel `.venv`. |
| `.venv` n'apparaît pas dans la liste des kernels | VS Code a été ouvert sur un autre dossier. | Ferme VS Code. Dans le terminal : `cd ~/meteolocale` puis `code .`. |
| Erreurs bizarres avec un chemin qui contient des espaces (`Mes Documents`, `Jean Dupont`) | Le terminal coupe les mots aux espaces. | Mets le chemin entre guillemets : `cd "Mes Documents"`. Le projet est dans `~/meteolocale`, sans espace : garde-le là. |
| 🪟 Le dossier est dans **OneDrive** et les fichiers disparaissent ou se bloquent | OneDrive synchronise le dossier pendant que Python y écrit. | Garde le projet dans `~/meteolocale` (`C:\Users\<ton nom>\meteolocale`), **pas** dans Documents ni dans OneDrive. |
| uv signale qu'un environnement `.venv` existe déjà | Tu l'as déjà créé. | Rien à faire : active-le. Pour repartir de zéro, supprime le dossier `.venv` dans l'explorateur de fichiers, puis relance `uv venv --python 3.13`. |
| Le terminal ne répond plus (pas de prompt) | Une commande attend ou tourne encore. | Appuie sur **Ctrl + C** pour l'interrompre. |

Toujours bloqué ? Note **la commande tapée** et **le message complet** (copie-le ou fais une capture d'écran), et
envoie-les à ton formateur : avec ces deux informations, on trouve en quelques minutes.

---

## 10. Aide-mémoire

| Je veux… | Je tape |
|---|---|
| Savoir où je suis | `pwd` |
| Voir ce qu'il y a ici (y compris le caché) | `ls` (`ls -a`) |
| Entrer dans un dossier / remonter / rentrer chez moi | `cd nom` / `cd ..` / `cd ~` |
| Créer un dossier (et ses parents) | `mkdir nom` (`mkdir -p a/b/c`) |
| Aller dans le projet | `cd ~/meteolocale` |
| Créer l'environnement virtuel | `uv venv --python 3.13` |
| Activer l'environnement | 🪟 `source .venv/Scripts/activate` · 🍎🐧 `source .venv/bin/activate` |
| Vérifier quel Python est utilisé | `which python` puis `python --version` |
| Désactiver l'environnement | `deactivate` |
| Installer les paquets du parcours | `uv pip install -r 00-Parcours-Progressif/requirements.txt` |
| Voir les paquets installés | `uv pip list` |
| Ouvrir le projet dans VS Code | `code .` |
| Interrompre une commande | **Ctrl + C** |
