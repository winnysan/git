# Git

vytvoriť zložku projektu `git`

$ sudo mkdir git

nastaviť oprávnenia pre užívateľa `marek`

```
$ sudo chown -R marek git
```

kontrola opravnení

```
$ ll
```

prejsť do zložky a otvoriť v nej `VS Code`, ortodoxný linuxový uctievač použije `Vim` pretože si nič jednoduchšie nezaslúži

```
$ cd git
$ code .
```

vytvoriť nový súbor `readme.md`

inicializovať git

```
$ git init
# Initialized empty Git repository in /var/www/git/.git/
```

zobrazenie skrytých súborov

```
$ ls -la
```

overenie stavu projektu

```
$ git status

# On branch master

# No commits yet

# Untracked files:
#  (use "git add <file>..." to include in what will be committed)
#        readme.md

# nothing added to commit but untracked files present (use "git add" to track)
```

evidovanie súboru `readme.md`

```
$ git add readme.md

$ git status

# On branch master

# No commits yet

# Changes to be committed:
#  (use "git rm --cached <file>..." to unstage)
#        new file:   readme.md
```

commitnutie súboru, parameter `-m` pridá komentár

```
$ git commit -m "prvý commit readme.md"

# [master (root-commit) 73ca806] prvý commit readme.md
#  1 file changed, 53 insertions(+)
#  create mode 100644 readme.md
```

rekaputulácia: po zmene súboru `readme.md` s komentárom `zmena`

```
$ git status
$ git add readme.md
$ git commit -m "zmena"
```

história zmien projektu

```
$ git log

# commit 73ca806b654fc2bdb590faa1d9b88cdd63728b23
# Author: winnysan <maarvinko@gmail.com>
# Date:   Mon Apr 18 10:22:08 2022 +0200

#    prvý commit readme.md
```

vytvorené súbory `index.html` a `app.js`

pridanie a commitnutie nových súborov, parameter `.` vyberie všetky súbory v adresári, paremeter `*.png` vyberie všetky súbory s príponou png, atď...

```
$ git add .
$ git commit -m "pridané nové súbory"
```

ak po úprave a označení súboru `git add` nechceme poslať zmenu do novej verzie, môžeme to zrušiť príkazom `git restore --staged`

```
$ git restore --staged readme.md
```

preskočenie `git add` pridaním parametra `a` do commitu, nefunguje pre nové súbory, tie treba pridať cez `git add`

```
$ git commit -am "preskočenie príkazu git add pridaním parametra a do commitu"
```

po vymazaní súboru `app.js` označenie a commitnutie

```
$ git add app.js
$ git commit -m "vymazaný súbor app.js"
```

upravenie logu parametrami, z logu sa vychádza klávesou `q`

```
$ git log --graph --decorate --abbrev-commit --all --pretty=oneline
```

kontrola zmeny v súbore príkazom `git diff`

```
$ git diff

# +
# +kontrola zmeny v súbore príkazom `git diff`
# +
# +```
# +$ git diff
# +```
```

vrátenie na poslednú verziu súboru príkazom `git checkout`

```
$ git checkout -- readme.md
```

pre vrátenie sa staršej verzii programu v `git log` si nájdeme commit k verzii, ktorý pridáme do príkazu `git checkout`

```
$ git checkout 85ea366b6224f0c71be512a75da1a39cdbc86328
```

vrátenie na master vetvu zadaním príkazu `git checkout master`

```
$ git checkout master
```

pri commite bez komentáru sa môže otvoriť Vim, upravovať sa dá v insert móde stlačením `i`, do prvého riadku napísať komentár, stlačením `ESC` sa vráti do command módu, uložiť a zavrieť sa dá príkazom `:wq`

```
$ git add .
$ git commit
i
# napísať komentár
:wq
```

na githube vytvoríme nový repozitár `git`, github ponúkne možnosti ak je ak ešte nieje alebo už je vytvorený repozitár, príkaz `git remote add origin` vytvorí spojenie s githubom

```
# nový repozitár
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git branch -M main          # master
$ git remote add origin git@github.com:winnysan/git.git
# git remote add origin https://github.com/winnysan/git.git
$ git push -u origin main     # master

```

```
# existujúci repozitár
$ git remote add origin git@github.com:winnysan/git.git
# git remote add origin https://github.com/winnysan/git.git
$ git branch -M main          # master
$ git push -u origin main     # master
```

