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