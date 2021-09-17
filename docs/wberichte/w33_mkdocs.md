*Wochenbericht KW33*

## Homebrew

Installation von Homebrew:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Miniconda

Installation von miniconda mittels Homebrew:

```bash
brew install --cask miniconda
```

Standardmässig keine Umgebung aktivieren:

```bash
conda config --set auto_activate_base false
```

## Python Environments

Für MkDocs eine Python-Umgebung erstellen, z.B. mit Python Version 3.9:

```bash
conda create --name env_name python=3.9
```

Aktivierung der Umgebung:

```bash
conda activate env_name
```

Umgebungen auflisten lassen (die aktive Umgebung wird immer mit einem * angezeigt):

```bash
conda info --envs
```

Aktive Python version überprüfen:

```bash
python --version
```

Python-Umgebung deaktivieren:

```bash
conda deactivate
```

### mkdocs

Installation Mkdocs (mkdocs-material installiert auch mkdocs und alle anderen Abhängiigkeiten mit):

```bash
pip install mkdocs-material
```

!!! warning ""
    pip sollte beim python packet mit installiert worden sein. Falls der obige Befehl nicht funktioniert zuerst einer der unteren Befehle ausführen und danach nochmals mkdocs installieren.

    Upgrade, wenn pip schon vorhanden ist:

    ```bash
    python install --upgrade pip
    ```

    Installation von pip:

    ```bash
    python get-pip.py
    ```

### Initialisierung

Ein Projektverzeichnis erstellen und in das Verzeichnis gehen:

```bash
mkdir /path/to/myproject
cd /path/to/myproject/
```

Das Projektverzeichnis versionieren und ein neues MkDocs-Projekt starten:

```bash
git init
echo "site/" > .gitignore
mkdocs new .
git add .
git ci -m "Initial empty mkdocs project"
```

