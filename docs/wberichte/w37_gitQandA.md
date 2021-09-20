*Wochenbericht KW37*

##Git Cherry-Pick

!!! failuer "Problem"
    Ein commit befindet sich auf dem falschen branch und man will den commit auf den richtigen branch bringen.

!!! success "Lössungsweg"
    git cherry-pick wäre einer der möglichen Lösungswege. Der Befehl ermöglicht beliebige git-commits anhand einer Referenz auszuwählen und an den aktuellen Arbeits-Head anzuhängen.

1.Zuesrt muss man sich auf dem branch befinden, wo der falsche commit ist.

2.Mit "git log" nachschauen gehen welche Referenz man angeben muss.

3.Nun auf den branch wechseln, wo der commit ursprünglich sein sollte.

4.Jetzt den Befehl für den cherry-pick durchführen:

```bash
git cherry-pick referenz
```

5.Nach dem cherry-pick befehl kann man den commit auf dem falschen branch löschen.

commit löschen:
```bash
git reset --hard HEAD~1
```

!!! warning
    Mit diesem Befehl wird nicht nur der letzte commit gelöscht sondern auch noch alle noch nicht commitete ànderungen.
