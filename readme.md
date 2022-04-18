vytvoriť zložku projektu `git`

sudo mkdir git

nastaviť oprávnenia pre užívateľa `marek`

```
sudo chown -R marek git
```

kontrola opravnení

```
ll
```

prejsť do zložky a otvoriť v nej `VS Code`

```
cd git
code .
```

vytvoriť nový súbor `readme.md`

inicializovať git

```
$ git init
# Initialized empty Git repository in /var/www/git/.git/
```

zobrazenie skrytých súborov

```
ls -la
```

overenie stavu projektu

```
$ git status

# On branch master

# No commits yet

# Untracked files:
  (use "git add <file>..." to include in what will be committed)
        readme.md

# nothing added to commit but untracked files present (use "git add" to track)
```