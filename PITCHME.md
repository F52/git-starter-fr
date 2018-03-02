<span class="menu-title" style="display: none;">Débuter avec Git et Git-flow</span>

## Débuter avec git<br/>et git-flow

![Image](./assets/logo-sm.png)<br/>
Cédric Foellmi – F52 Technologies<br/>cedric@f52.tech – http://f52.tech

<img src="./assets/green-flash.png" class="bottom-img">

---?image=http://f52.tech/_nuxt/img/f52_welcome.2393ff7.jpg&size=cover

## Table des matières

* Les principes de git
* Les commandes de base pour commencer tout de suite
* Le git-flow
* Les <span class="code">remotes</span> et les plateformes (GitHub...)
* Collaborer
* Les dépôts du F52 pour vous exercer !
* Quelques exemples de clients
* Un fork sur GitHub


---

<span class="menu-title" style="display: none">Historique 1</span>

Git a débuté en 2005 après que Linus Torvald, le créateur de Linux, a dû
renoncé à son système de contrôle de version, devenu payant.

"git" veut dire "personne désagréable" en anglais argotique.

> I'm an egotistical bastard, and I name all my projects after myself. First 'Linux', now 'git'.

-- Linus Torvald

---

<span class="menu-title" style="display: none">Historique 2</span>

* le développement commença le **3 avril 2005**,
* il fut annoncé **le 6**,
* est devenu son propre contrôleur de version **le 7**,
* le premier *merge* eut lieu **le 18**,
* **le 29**, les objectifs de performance sont atteints
* **le 16 juin**, git gère la release du kernel Linux 2.6.12
* **le 26 juillet**, la maintenance est transferrée à Junio Hamano...
* la v1.0 sort le **21 décembre**.

<center>![gif](https://media.giphy.com/media/26ufdipQqU2lhNA4g/giphy.gif)</center>
<small>Source: Wikipedia</small>

---

## Les Principes

---

<span class="menu-title" style="display: none">Les principes I</span>

### git un système de contrôle de version *distribué*.

Avantages:

* Pas besoin de serveur central, de "single point of failure"
* Permet de continuer à travailler même sans réseau (dans l'avion...)
* Cloner un dépôt signifie obtenir l'entierté du projet, historique compris.
* **(Presque) tout se passe "localement"**

---

<span class="menu-title" style="display: none">Les principes II</span>

### git fonctionne comme un mini "file system".

* Ce sont les fichiers eux-mêmes qui sont conservés au moment du `commit`, pas seulement des différences
* Git fonctionne très bien pour le code, et le texte. Très mal pour tous les binaires (images, PDFs...)

Diff | Git
--- | ---
![Image](https://git-scm.com/book/en/v2/images/deltas.png) | ![Image](https://git-scm.com/book/en/v2/images/snapshots.png)


---

<span class="menu-title" style="display: none">Les principes III</span>

### git assure une entière intégrité des données

* Git "checksum" tout avant de commiter.
* Git généralement ajoute des données. Il est très difficile de retirer (ou de perdre) quelque chose, une fois commité.

---

<span class="menu-title" style="display: none">Les principes IV</span>

### git fonctionne avec 3 états (ou 3 niveaux)

* "commité": le fichier est enregistré dans l'historique.
* "staged" ou mis à l'index: le fichier est marqué pour partir avec le prochain wagon/commit.
* "modifié": le fichier est modifié par rapport à sa précédente copie.

Logiquement, tout fichier nouveau, renommé, déplacé ou effacé est considéré comme "modifié".

![Image](https://git-scm.com/book/en/v2/images/areas.png)

---

<span class="menu-title" style="display: none">Les principes V</span>

### Les différents états pour les fichiers

![Image](https://git-scm.com/book/en/v2/images/lifecycle.png)

---

## Des questions sur Les Principes ?

---

## Ok, les bases

---

<span class="menu-title" style="display: none">Un (tout petit) peu de config</span>

### Un (tout petit) peu de config

Pas obligatoire mais évite des soucis par la suite.

* Le fichier `.gitignore` permet de lister tous les fichiers ou "patterns de fichiers" à ignorer.
* Un super site pour les .gitignore de vos projets: https://www.gitignore.io

* Tapez une fois, les 2 commandes:<br/>
`git config --global user.name "John Doe"`<br/>
`git config --global user.email johndoe@example.com`


---

<span class="menu-title" style="display: none">Les commandes vraiment de base</span>

### La base de la base: `init`, `add`, `commit`

Aussi: `ignore`, et `status`, et aussi... `rm` et `mv` et `log`

---

<span class="menu-title" style="display: none">Les commandes de base +</span>

### La base: `branch`, `checkout`, `merge`


---

<span class="menu-title" style="display: none">clone</span>

### Le clonage: `clone` (et une remarque sur les dépôts locaux)

---

<span class="menu-title" style="display: none">Défaire</span>

## Défaire

---

## Des questions sur Les Bases ?

---

## Ok, le git-flow

<span class="menu-title" style="display: none">git-flow</span>

### Le git-flow est une "bonne pratique" courante.

Pas une obligation, mais quand autant de monde s'y convertit...

Plusieurs versions, plus ou moins complexes, trouvez la votre !

tags
