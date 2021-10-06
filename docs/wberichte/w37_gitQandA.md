*Wochenbericht KW37*

## Cherry Picking Commits

!!! failure "Problem"
    Ein Commit befindet sich auf dem falschen Branch und man will den Commit auf den richtigen Branch bringen.

!!! success "Lössungsweg"
    `git cherry-pick` wäre eine mögliche Lösung. Der Befehl ermöglicht es, beliebige git-Commits anhand einer Referenz auszuwählen und an den aktuellen Arbeits-Head anzuhängen.

1. Zuerst muss man sich auf dem Branch befinden, wo der falsche Commit ist.

2. Mittels `git log` nachschauen, welche Referenz der falsch platzierte Commit hat.

3. Nun auf den Branch wechseln, wo der Commit ursprünglich sein sollte resp. wo man den Commit hinhaben möchte.

4. Jetzt den Befehl für den cherry-pick durchführen:

```bash
git cherry-pick referenz
```

5. Nach dem cherry-pick Befehl kann man den Commit auf dem falschen branch löschen.

commit löschen:
```bash
git reset --hard HEAD~1
```

!!! warning
    Mit diesem Befehl wird nicht nur der letzte Commit aus dem Repo gelöscht, sondern es gehen auch alle aktuellen
    Änderungen im Workspace sowie im Staging-Bereich verloren. Daher sind diese erst mittels `git stash` zurückzustellen.
