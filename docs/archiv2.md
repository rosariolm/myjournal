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


##W33 Mkdocs gebrauchen

###Homebrew

Installation von Homebrew:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### miniconda

Installetion von mini conda mit Homebrew:

```bash
brew install --cask miniconda
```

### python environment

Phyton Umgebung erstellen:

```bash
conda creat --name env_name python=python_version
```

Aktivierung der Umgebung:

```bash
conda activate env_name
```

Umgebungen auflisten lassen (die Aktive Umgebung wird immer mit einem * angezeigt):

```bash
conda info --envs
```

Aktive python version überprüfen:

```bash
python --version
```

Zurück zur Base kehren:

```bash
conda activate
```

### mkdocs

Installation Mkdocs:

```bash
pip install mkdocs-material
```

!pip sollte beim python packet mit installiert worden sein. Falls der Befehl nicht Funktioniert zu erst einer der  unteren Befehle ausführen und dannach noch mals mkdocs installieren.


Upgrade wenn pip schon vorhanden ist:

```bash
python install --upgrad pip
```

Installation von pip:

```bash
python get-pip.py
```

### Initialisierung

Zu dem Verzeichnis des projekts wechseln:

```bash
cd /name/name...
```

Im verzeichnis unterer befehl ausführen:

```bash
git init
```

