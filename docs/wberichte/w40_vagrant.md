*Wochenbericht KW40*

###Box

???+ example "Befehle"

    ```bash
    vagrant box add ADDRESS
    ```

    Dadurch wird das Feld mit der angegebenen Adresse hinzugefügt. Die Adresse kann eines von drei Dingen sein:

    1. URL direkt zu einem box file.
    2. Dateipfad oder HTTP-URL zu einem Feld in einem Katalog.
    3. Ein Kurzname aus dem Katalog der verfügbaren Vagrant images.

    ```bash
    vagrant box list
    ```
    Dieser Befehl listet alle installierten Boxen auf.

    ```bash
    vagrant box outdated
    ```
    Der Befehl zeigt an, ob die Version der installierten Boxen veraltet ist oder nicht.

    ```bash
    vagrant box prune
    ```
    Dieser Befehl entfernt alte Versionen von installierten Boxen. Nach einer Bestätigung wird nur gebeten, wenn die Box in diesem Moment verwendet wird.

    ```bash
    vagrant box remove NAME
    ```
    Die angegebene Box wird lokal entfernt.

    ```bash
    vagrant box update
    ```
    Dieser Befehl aktualisiert die Box der aktuellen Umgebung, wenn Updates verfügbar sind. Der Befehl kann auch eine bestimmte Box ausserhalb einer aktiven Umgebung aktualisieren, indem das Flag `--box` angegeben wird.


###Umgebung

???+ example "Befehle"

    ```bash
    vagrant destroy [name|id]
    ```
    Dieser Befehl stoppt die laufende, virtuelle Maschine und löscht alle Ressourcen, die erstellt wurden.

    ```bash
    vagrant global-status
    ```
    Dieser Befehl listet den Status aller mittels Vagrant erstellten virtuellen Maschinen auf dem System des aktuellen Benutzers.

    ```bash
    vagrant halt [name|id]
    ```
    Mit diesem Befehl wird die laufende Maschine heruntergefahren.

    ```bash
    vagrant init [name[url]]
    ```
    Dieser Befehle ersellt im aktuellen Verzeichnis ein `Vagrantfile` mit der optional verlangten Basebox.

    ```bash
    vagrant login
    ```
    Der Login Befehl wird zur Authentifizierung beim Vagrant Cloud-Server verwendet. Die Anmeldung ist nur erforderlich, wenn man auf geschützte Boxen zugreifen oder Vagrant Share verwenden.

    ```bash
    vagrant rdp
    ```
    Dadurch wird ein RDP Client für eine Remote-Desktop-Sitzung mit dem Gast gestartet. Dies funktioniert nur für Vagrant Umgebungen, die Remote Desktop unterstützen, was überlicherweise nur bei Windows der Fall ist.

    ```bash
    vagrant reload [name|id]
    ```
    Dieser Befehl ist wie ein Neustart. Zuerst wird die Maschine angehalten und darauf folgt ein Start. Dieser Befehl ist normalerweise erforderlich, damit vorgenommene Änderungen an der Konfiguration der Maschine (RAM, CPU, ..) wirksam werden.

    ```bash
    vagrant share
    ```
    Der Share Befehl initialisiert eine Vagrant-Share-Sitzung, sodass die Vagrant Umgebung für alle freigeben werden kann.

    ```bash
    vagrant snapshot
    ```
    Dies ist der Befehl zum Verwalten von Snapshots mit dem Gastcomputer. Snapshots zeichnen einen Point-in-Time-Zustand eines Gastcomputers auf. So kann eine Umgebung schnell wiederhergestellt werden.

    ```bash
    vagrant ssh [name|id] [-- extra_ssh_args]
    ```
    Dadurch wird eine SSH Verbindung zu einer laufenden Vagrant Maschine hergestellt und man erhält Zugriff auf eine Shell.

    ```bash
    vagrant ssh-config [name|id]
    ```
    Durch diesen Befehl wird eine gültige Konfiguration für eine SSH Konfigurationsdatei an SSH in den laufenden Vagrant Rechner direkt ausgegeben (anstelle von vagrant ssh).

    ```bash
    vagrant status [name|id]
    ```
    Damit wird der Status der Machine ausgegeben.

    ```bash
    vagrant suspend [name|id]
    ```
    Dadurch wird die Gastmaschine pausiert, anstatt sie vollständig herunterzufahren oder zu zerstören.

    ```bash
    vagrant up [name|id]
    ```
    Dieser Befehl erstellt und konfiguriert Gastmaschinen entsprechend der Definitionen im `Vagrantfile`.

    ```bash
    vagrant upload source [destination] [name|id]
    ```
    Dieser Befehl lädt Dateien und Verzeichnisse vom Host auf den Gastcomputer hoch.

    ```bash
    vagrant version
    ```
    Dieser Befehl teilt Ihnen die Version von Vagrant mit, die Sie installiert haben, sowie die neueste Version von Vagrant, die derzeit verfügbar ist.
