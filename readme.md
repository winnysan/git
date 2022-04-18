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

prejsť do zložky a otvoriť v nej `VS Code`

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

preskočenie `git add` pridaním parametra `a` do commitu

```
$ git commit -am "preskočenie príkazu git add pridaním parametra a do commitu"
```