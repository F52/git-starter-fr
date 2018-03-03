---?image=http://f52.tech/_nuxt/img/f52_welcome.2393ff7.jpg&size=cover

<span class="menu-title" style="display: none;">Débuter avec Git et Git-flow</span>

## <span style="color: white;"> Débuter avec git<br/>et git-flow</span>

<span style="color: lightgray;">Cédric Foellmi – F52 Technologies<br/>cedric@f52.tech –</span> http://f52.tech

---

## Table des matières

* Les principes de git
* Les commandes de base
* Le git-flow
<hr>
* Les <span class="code">remotes</span> et les plateformes (GitHub...)
* Collaborer
<hr>
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
* le premier `merge` eut lieu **le 18**,
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

### git est un système de contrôle de version *distribué*.

Avantages:

* Pas besoin de serveur central, pas de "single point of failure"
* Permet de continuer à travailler hors-ligne
* Cloner un dépôt signifie obtenir l'entierté du projet, historique compris.
* **(Presque) tout se passe "localement"**

---

<span class="menu-title" style="display: none">Les principes II</span>

### git fonctionne comme un mini "système de fichiers".

* Les fichiers eux-mêmes sont conservés au moment du `commit`, pas seulement des différences
* Git est conçu pour le code, et le texte. Pas pour les binaires (images, PDFs...)

Diff | Git
---- | ---
![Image](https://git-scm.com/book/en/v2/images/deltas.png) | ![Image](https://git-scm.com/book/en/v2/images/snapshots.png)


---

<span class="menu-title" style="display: none">Les principes III</span>

### git assure une entière intégrité des données

* Git "checksum" tout avant de commiter.
* Git généralement ajoute des données. Il est très difficile de retirer (ou de perdre) quelque chose, une fois commité.

---

<span class="menu-title" style="display: none">Les principes IV</span>

### git fonctionne avec 3 niveaux

* **commité**: le fichier est enregistré dans la chaîne de commits.
* **staged** ou mis à l'index: le fichier est marqué pour partir avec le prochain wagon/commit.
* **modifié**: le fichier est différent de sa précédente copie.

<small>Logiquement, tout fichier nouveau, renommé, déplacé ou effacé est considéré comme "modifié".</small>

<small>Sauf s'il est **ignoré**...</small>

---
<span class="menu-title" style="display: none">Les principes IV (image)</span>

### git fonctionne avec 3 niveaux

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

<small>Pas obligatoire mais évite des soucis par la suite.</small>

* Le fichier **`.gitignore`** permet de lister tous les fichiers ou "motifs de fichiers" à ignorer.
* @fa[arrow-right] https://www.gitignore.io

* Tapez une fois, les 2 commandes:<br/>
**`git config --global user.name "John Doe"`**<br/>
**`git config --global user.email johndoe@example.com`**


---

<span class="menu-title" style="display: none">Les commandes vraiment de base</span>

### La base de la base:

<center>`git init`, &nbsp; &nbsp; &nbsp; `git add`, &nbsp; &nbsp; &nbsp;  `git commit`</center>

Boum.

<small>Mais aussi: `git ignore`, et `git status`.</small>

---

<span class="menu-title" style="display: none">Le coeur de git</span>

### Le coeur de git

* **`clone`**: Littéralement. A ne pas confondre avec `checkout` (ni le `checkout` de CVS) !
* **`branch`**: instantané, ne coûte rien, facile (juste un pointeur).
* **`checkout`** =  change de branche.
* **`merge`**: on merge toujours vers soi !

---

<span class="menu-title" style="display: none">Le coeur de git: exemple</span>

![Image](./assets/img/logo-sm.png) Dépôt d'exemple sur GitHub

![Image](https://git-scm.com/book/en/v2/images/advance-master.png)

---

## Des questions sur Les Bases ?

---

## Ok, le git-flow

---

<span class="menu-title" style="display: none">git-flow</span>

### Le git-flow est une "bonne pratique" courante.

<small>Pas une obligation, mais quand autant de monde s'y convertit...</small>

Plusieurs versions, plus ou moins complexes. A vous de trouvez la vôtre!

@fa[arrow-right] https://danielkummer.github.io/git-flow-cheatsheet/

**`git flow init`**

---

<span class="menu-title" style="display: none">git-flow - 1</span>

![Image](./assets/img/git-flow.001.png)

---

<span class="menu-title" style="display: none">git-flow - 2</span>

![Image](./assets/img/git-flow.002.png)

---

<span class="menu-title" style="display: none">git-flow - 3</span>

![Image](./assets/img/git-flow.003.png)

---

<span class="menu-title" style="display: none">git-flow - 4</span>

![Image](./assets/img/git-flow.004.png)

---

<span class="menu-title" style="display: none">git-flow - 5</span>

![Image](./assets/img/git-flow.005.png)

---

<span class="menu-title" style="display: none">git-flow - config</span>

### git-flow config

<table style="width: 100%">
<tr>
<th>Init</th><th>Config</th><th>Use</th>
</tr>
<tr>
<td width="20%"><img src="https://github.com/F52/git-starter-fr/raw/master/assets/img/git-flow-config-1.png"></td>
<td width="60%"><img src="https://github.com/F52/git-starter-fr/raw/master/assets/img/git-flow-config-2.png"></td>
<td width="20%"><img src="https://github.com/F52/git-starter-fr/raw/master/assets/img/git-flow-config-3.png"></td>
</tr>
</table>

---

<span class="menu-title" style="display: none">tags & hooks</span>

### Les Tags et les Hooks

* Des outils puissants.
* Les portes d'entrée vers l'intégration continue, et l'industrialisa
* semver, ça vous parle ? @fa[arrow-right] https://semver.org

---

## Des questions sur Le git-flow ?

---

## Ok, les remotes et la collaboration

---

<span class="menu-title" style="display: none">git remote</span>

### Oui, il peut y en avoir plusieurs

Exemple:

...

---

## Des questions sur les remotes et la collaboration ?

---

## Ok, les extras et le fork sur GitHub

---

<span class="menu-title" style="display: none">Quelques clients</span>

### Quelques clients

* GitKraken
* Tower
* SourceTree
* TortoiseGit

---

<span class="menu-title" style="display: none">github-fork - 1</span>

Ce framework a l'air intéressant. Clic pour faire un fork !

![Image](./assets/img/github-fork.1.png)

---

<span class="menu-title" style="display: none">github-fork - 2</span>

J'ai maintenant une copie entière du projet, avec ma propre adresse `.git`.
C'est sur ma copie que je fais des changements.

![Image](./assets/img/github-fork.2.png)

---

Une fois satisfait des changements, je soumets une "Pull Request".
Une discussion prend place.

<span class="menu-title" style="display: none">github-fork - 3</span>

![Image](./assets/img/github-fork.3.png)

---

Chaque ligne modifiée peut être (âprement) discutée.
Le projet source n'a subit strictement aucune altération.

<span class="menu-title" style="display: none">github-fork - 4</span>

![Image](./assets/img/github-fork.4.png)

---

Si je donne accès en écriture à ma PR, l'auteur peut participer aux changements,
par des commits.

<span class="menu-title" style="display: none">github-fork - 5</span>

![Image](./assets/img/github-fork.5.png)

---

Quand l'auteur décide que les changements sont prêts à être intégrés (en supposant
  que tous les outils d'intégration continue mis en place pour ce projet soient au vert...),
  la PR est "mergée"/"fusionnée" et apparaît dans l'historique du projet initial.

  Tout le monde peut maintenant profiter des changements que j'ai proposé.

<span class="menu-title" style="display: none">github-fork - 6</span>

![Image](./assets/img/github-fork.6.png)

---

## Merci !

#### Des questions finales ?
