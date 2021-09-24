# GitHub Workflow

*Wochenbericht KW36*

### 1. Ticket auf GitHub

Ein Ticket auf GitHub erstellen. Unter "Issues" > "New Issue"

![Screenshot github issue](../img/Erstellung_Ticket.png)

Bei der Erstellung passenden Titel wählen, Assignees und Labels setzen. Die Beschreibung aussagekräftig gestalten, so dass klar, wo das Problem liegt oder was zu machen ist - auch Tage später noch.

![Screenshot github Ticket](../img/Erstellung_Ticket2.png)

### 2. Branch pro Ticket

Für das Ticket eienn Branch erstellen und auch direkt aud den neu erstellten Branch wechseln:

```bash
git checkout -b Issue_number
```

!!! info
    Die Ticketnummer im Branch-Namen zu verwenden ist optional, aber bietet den Vorteil, dass man bei mehreren Branches den Überblick nicht verliert.


### 3. Änderungen ausführen

Bearbeitung starten. Die unten aufgelistete Befehe und die Shortcuts können bei der Bearbeitung hilfreich sein.

=== "Befehl"

    _Datei mit vim öffnen, um die angegebene Datei zu bearbeiten:_

    ```bash
    vim datei_name
    ```

=== "Shortcuts"

    * a: Bearbeiten direkt nach dem Cursor / A: Bearbeiten am Ende der Zeile
    * :wq Abspeichern und Datei schliessen
    * :w Abspeichern


### 4. Commit(s) erstellen

Nach der Bearbeitung adden und commiten.

=== "add"

    Alle Änderungen in den Staging-Bereich übernehmen:

    ```bash
    git add .
    ```

    Nur ausgwählte Änderunge in den Staging-Bereich übernehmen:

    ```bash
    git add datei1 datei2
    ```

=== "commit"

    Änderungen im Staging-Bereich als neuen Commit in das Repository übernehmen:

    ```bash
    git commit -m "beschreibung"
    ```

### 5. Branch nach GitHub pushen

Mit dem untenstehenden Befehl nach Remote pushen:

```bash
git push origin branch_name
```

### 6. Pull Request (PR) erstellen

Mit dem beim Push angezeigten Link kann nun im Browser eingegeben Pull Request erstellt werden.

![Screenshot request](../img/link.png)


Im Formular des Pull Request beschreiben, welche Änderungen man vorgenommen hat. Allesnfalls offene Fragestellunge,
Entschediungn, die man bei der Implemnetation angetroffen hat, sowie besondere Schwierigkeiten oder abzusehende
Probleme erwähnen.

!!! warning Bezug zu Ticket
    Falls der Pull Request ein aktuelles Ticket löst, spätestens im Text des Pull Request das Schlüsselwort "Fixes"
    gefolgt von der Ticketnummer ergänzen, damit ein Bezug hergestellt wird und das Ticket automtisch geschlossen wird, also z.B.:

        Fixes #13



### 7. Pull Request anehmen.

![Anahme pull request](../img/anahme.png)

![Bestätigung](../img/successful_merge.png)


### 8. Workspace und Remote aufräumen

Folgende Abfolge von Befehlen sollte grundsätzlich nach jedem erfolgreichen Merge eines Branches durchgeführt werden:

```bash
# auf branch main wechseln
git checkout main
# die neusten Änderungen von remote holen
git pull --ff-only
# den lokalen feature branch, der jetzt gemerged ist, löschen
git branch -d branch_name
# den feature branch auch remote löschen
git push origin :branch_name
```

### 9. Ticket auf GitHub schliessen.

Falls ein Ticket vorliegt und dieses nicht schon mittels "Fixes #x" geschlossen wurde, dieses manuell schliessen:

![Screenshot github Ticket schliessung](../img/Schliessung_Ticket.png)
