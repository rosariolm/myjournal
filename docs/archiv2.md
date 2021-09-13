## W34 git Befehle

### Remote-Repositorys

Instaliert ein lokales Repository:

```bash 
git init
```

Zeigt der Name an, den das lokale repository für das CodeCommit repository verwendet:

```bash
git remote
```

zeigt den Namen und die URL an, die das lokale repository für Abrufe und Push- vorgänge verwendet:

```bash
git remote -v
```

Kann vverwendet werden, um eine Vebbindung zwischen dem lokalen und einem remote-Repository herzustellen:

```bash
git remote add remote-name remote-url
```

Erstelt Kopie:

```bash
git clone remote-url local-subfolder-name
```

Überträgt die finael Commits:

```bash
git push remote-name branch-name
```

Pulld das angegebene Repository auf das lokale Repository:

```bash
git pull remote-name branch-name
```

Trennt das lokale Repository anhand des angegebenen Namens:

```bash
git remote rm remote-name
```


###Commmits:

Zeigt der status an, sprich zeiggt an welche Commits lokal hinzugefügt wurden oder auch nicht:

```bash
git status
```

Zeigt Änderungen zwischen dem schwebenden Commit und dem neusten Commit (Lokal):

```bash
git diff HEAD
```

Fügt alle änderungen im angegebenen File hinzu:

```bash
git add file-name
```

Fügt alle neuen änderungen und löschunggen hinzu:

```bash
git add
```

Commitet mit der eingegebenen commit massage:

```bash
git commit -m "Miteillung"
```

Listet die letzten Commits im lokalen Repo auf:

```bash
git log
```

Listet die Letzten Commits in einem Diagrammformat auf:

```bash
git log --graph
```

###Branches

Erstellt den Branchh wenn dieser noch nicht existier und wechselt auf Ihn:

```bash
git checkout -b branch-name
```

Löscht angegebender Branch lokal ausser wenn dieser nicht übernommene Änderungen enthält.

```bash
git branch -d branch-name
```

Löscht den Branch ohne rücksicht zu nehmen auf noch nicht übernommene änderungen:

```bash
git branch -D branch-name
```

Lösct den Branchh auf dem CodeCommit -Repository (Online):

```bash
git push remote-name :branch-name
```

Führt Änderungen vom angegebenen branch im lokalen ein:

```bash
git merge branch-name
```

Führt Änderungen hinten an:

```bash
git --rebase
```


