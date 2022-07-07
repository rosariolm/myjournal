#Arbeitsheft

## Inhaltsverzeichnis

- [Intune](#Intune)

    * [Configuration profiles](#conf)

        * [Wallpaper](#wpaper)

        * [Lockscreen](#Lscreen)

        * [Start menu layout and taskbar](#SandT)

    * [Add Apps](#Apps)

        * [Default file associations](#FileAssoc)

    * [Toast notification](#toast)

    * [IE Mode](#IE)

    * [Password policy](#pwd)

    * [PIN Deaktivierung](#PIN)

    * [Gerät bei Autopilot hinzufügen](#Autopilot)

        * [Autopilot Script Anpassung](#AutoPilotScript)

- [Softwarepaketierung](#SoftPack)

- [KFM](#KFM)

- [Multiboot-USB-Stick](#YUMI)

    * [Boot Probleme](#YUMIboot)

- [Firmware Update](#FirmUp)

- [Bootcamp](#BootC)

---
<a name="Intune"></a>
## Intune

<a name="conf"></a>
### Configuration profiles

<a name="wpaper"></a>
#### Wallpaper

---

<a name="Lscreen"></a>
#### Lockscreen

---

<a name="SandT"></a>
#### Start menu layout and taskbar

---

<a name="Apps"></a>
### Add Apps

---

<a name="FileAssoc"></a>
#### Default file associations

---

<a name="toast"></a>
### Toast notification

---

<a name="IE"></a>
### IE Mode

---

<a name="pwd"></a>
### Password policy

Um eine Password Policy zu setzten, navigiere zu **Start > Devices > Compliance policies**.

=== "Start"    

    ![Start](../../img/a/bi/start.png)

=== "Devices"

    ![Devices](../../img/a/bi/devices.png)

=== "Compliance policies"

    ![Compliance policies](../../img/a/bi/CPolicies.png)

Nun Create Policy anwählen.

![create policy](../../img/a/bi/createP.png)

!!! info
    Nun kann man damit beginnen die Password Policy zu erstellen, die kann man wie ich sie gemacht habe befolgen oder auch einige Dinge abändern.

**Konfigurationsschritte**

=== "Create a policy"    

    ![platform](../../img/a/bi/platform.png)

=== "Basics"

    ![basics](../../img/a/bi/basics.png)

    ![basics1](../../img/a/bi/basics1.png)

=== "Configuration settings"    

    ![configurationSettings](../../img/a/bi/configurationSettings.png)

    ![configurationSettings1](../../img/a/bi/configurationSettings1.png)

    ![configurationSettings2](../../img/a/bi/configurationSettings2.png)

    ![configurationSettings3](../../img/a/bi/configurationSettings3.png)

=== "Actons for noncompliance"

    ![ActonsForNoncompliance](../../img/a/bi/ActonsForNoncompliance.png)

=== "Assignments"

    ![Assignments](../../img/a/bi/Assignments.png)

    ![Assignments1](../../img/a/bi/Assignments1.png)

=== "Applicability Rules"

    ![ApplicabilityRules](../../img/a/bi/ApplicabilityRules.png)

=== "Review + create"

    ![R+C.](../../img/a/bi/R+C.png)



![pwsPolicieSchluss](../../img/a/bi/pwsPolicieSchluss.png)
---

<a name="PIN"></a>
### PIN Deaktivierung

![PIN Windows ](../../img/w/w5/w5_x.png){: style="height:450px"}

Nach diesem kurzen Schritt wird das "Windows Hello for Business" deaktiviert. Somit auch die Eingabe vom PIN, welche ich deaktivieren wollte.

**Arbeitsschritte**

1. Zuerst muss man vom Home aus zu **Devices > Windows > Windows enrollment** navigieren.

     ![Home Feld](../../img/w/w5/w5_1.png)

2. Unter **Windows enrollment** kann man nun **Windows Hello for Business** anklicken.

     ![Windows enrollment](../../img/w/w5/w5_3.png)

3. Auf dem neu erschienen Feld, muss man unter **Configure Windows Hello for Business** *Disabled* angeben.

     ![Windows enrollment 2](../../img/w/w5/w5_4.png)

4. Nun *Save* anwählen.

     ![Windows enrollment 3](../../img/w/w5/w5_5.png)

5. Nach der Speicherung wurde der PIN schon deaktiviert.

     ![Windows enrollment 4](../../img/w/w5/w5_6.png)

---
<a name="Autopilot"></a>
### Gerät bei Autopilot hinzufügen

Bevor man in Intune das Gerät importieren kann. Muss ein Script auf dem jeweiligen Gerät ausgeführt werden.

#### Auf dem Gerät

1. Wie auf [THE LAZY ADMINISTRATOR](https://www.thelazyadministrator.com/2020/01/27/get-a-new-computers-auto-pilot-hash-without-going-through-the-out-of-box-experience-oobe/) das Script herunterladen und am besten auf einem USB-Stick speichern, für weiteren gebrauch.

2. Nach dem Download fehlte bei mir noch ein CMD feil welches ich kopiert habe.

3. Nun kann das Get-WindowsAutoPilotInfo.ps1 ausgeführt werden. *Als Admin ausführen!*

4. Nun sollte eine compHas.csv erstanden sein, welche man für den Intune schritt braucht.

![hash datei](../../img/w/w7/w7_7.png)


#### In Intune

1. Zuerst muss man vom Home aus zu **Devices > Windows > Windows enrollment > Devices** navigieren.

     ![Home Feld](../../img/w/w7/w7_1.png)

2. Auf der **Windows Autopilot devices** Seite *Import* anwählen.

     ![Autopilot Seite](../../img/w/w7/w7_4.png)

3. Hier nun die erstellte compHash.csv angeben.

    === "Schritt 1"

        ![hash datei](../../img/w/w7/w7_8.png){: style="height:550px"}

    === "Schritt 2"

        ![hash datei](../../img/w/w7/w7_9.png)

    === "Schritt 3"

        ![hash datei](../../img/w/w7/w7_10.png){: style="height:550px"}

4. Nach einigen Minuten sollte das Gerät neu auf der Liste erscheinen.

     ![neues Gerät auf der Liste](../../img/w/w7/w7_5.png)

---

<a name="AutoPilotScript"></a>
#### Autopilot Script Anpassung

Damit das Gerät welches mit Autopilot aufgesetzt wird, auch den Group Tag erhält und Online die neuste Windows Version herunterlädt. Muss man nur drei kleine Änderungen am Script vornehmen, welches im KW7 Wochenbericht erstellt habe.

**Arbeitsschritte**

1. Zum Starten Windows PowerShell ISE öffnen.

    ![PowerShell](../../img/w/w8/w8_1.png)

2. Nun die Script Datei auf dem USB-Stick öffnen.

    === "Schritt 1"

        Von der Startseite aus zu **Datei > Öffnen...** navigieren. Oder mit dem shortcut Strg + O.

        ![Windows enrollment](../../img/w/w8/w8_2.png)

    === "Schritt 2"

        Jetzt zur ps1. Datei navigieren und diese öffnen.

        ![Windows enrollment 2](../../img/w/w8/w8_3.png)

3. Nun die drei Änderungen vornehmen.

    === "Unverändert"

        ![Windows enrollment](../../img/w/w8/w8_4.png)

    === "Group Tag"

        Da ich möchte, dass jedes Gerät den Group Tag Client automatisch zugeordnet kriegt. Gebe ich dies unter $GroupTag an.
        Auf dem Bild wäre dies in der Zeile 117 zusehen.

        ![Windows enrollment](../../img/w/w8/w8_5.png)

    === "Online"

        Jetzt noch $Online auf $true stellen.
        Auf dem Bild wäre dies in der Zeile 123 zusehen.

        ![Windows enrollment](../../img/w/w8/w8_6.png)

    === "Assign"

        Assign habe ich zusätzlich auch noch auf $true gestellt.
        Auf dem Bild wäre dies in der Zeile 129 zusehen.

        ![Windows enrollment](../../img/w/w8/w8_7.png)

---

<a name="SoftPack"></a>
## Softwarepaketierung

---

<a name="KFM"></a>
## KFM

---

<a name="YUMI"></a>
## Multiboot-USB-Stick mit YUMI erstellen


Mit dieser Anleitung kann man einen Multiboot-USB-Stick erstellen. Ich habe dafür YUMI („Your Universal Multiboot Installer“) verwendet und ein Windows 10, Windows 11 und Knoppix 9.1 gewählt.

### YUMI Download

1. Auf der [Pendrivelinux.com](https://www.pendrivelinux.com/yumi-multiboot-usb-creator/) findet man die drei YUMI Varianten, die man downloaden kann. Ich habe YUMI exFAT verwendet. Der direkte link für [YUMI exFAT](https://www.pendrivelinux.com/yumi-multiboot-usb-creator/#YUMI-exFAT).

    ![YUMI exFAT abschnit](../../img/w/w18/1.png)

2. Zum Downloaden, beim YUMI exFAT (BIOS and UEFI USB Boot) abschnitt bis nach unten scrollen und auf den Download Button klicken. Nach dem Download YUMI mit einem doppelklick starten.

![Download button](../../img/w/w18/2.png)


### Multiboot-USB-Stick erste schritte

1. Nach dem Starten von YUMI muss man zuerst die Bedingungen mit «**I Agree**» bestätigen.

     ![I Agree feld](../../img/w/w18/3.png)

2. Nun unter **Step 1: ...** der gewünschte USB-Stick anwählen.

     ![Stick wählen](../../img/w/w18/4.png)

3. Jetzt bei **Step 2: ... die** Liste öffnen, in dem man ins leere Feld klickt und danach das passende zu Ihrem iso wählen. (Da ich ein Windows 11 iso auf dem Stick haben wollte, habe ich in der Liste Windows Installer iso ausgewählt)

    ![Step 2:](../../img/w/w18/5.png)

4. Nun da der Explorer erschienen ist kann man zum iso File navigieren und dies anwählen. Wen man das richtige iso hat, **Öffnen** anwählen.

    ![](../../img/w/w18/6.png)

5. Jetzt kann man auf **Create** klicken.

    === "Create"    

        ![](../../img/w/w18/7.png)

    === "Kopierprozess"

        Der Kopierprozess dauert ca. 2 Minuten.

        ![kopie](../../img/w/w18/8.png)

    === "Hinzufügung"

        Nachdem es fertig geladen hat, kann man auch **Next >** klicken.

        ![adding](../../img/w/w18/9.png)

    === "Nächstes ISO"

        Nun wird man danach gefragt, ob man ein weiteres iso auf den Stick laden möchte. Da auf einen Multiboot-USB-Stick mehrere gehören, habe ich **ja** angewählt.

        ![next iso](../../img/w/w18/10.png)

### Weitere Images

Nach dem man Ja angewählt hat, erscheint das gleiche Feld wie zuvor. Jetzt kann man die gleichen Schritte wie zuvor durchspielen, bis man alle Images hat, die man möchte.

![next iso](../../img/w/w18/11.png)

**Beispiel Knoppix:**

Bei Knoppix habe ich das gleiche wie bei Windows gemacht, nur dass ich bei **Step 2: ...** Ubuntu ausgewählt habe.

![knoppix iso](../../img/w/w18/12.png)

### Hinweise

- Sollte man zweimal das gleiche iso anwählen, wird man darauf aufmerksam gemacht.

  ![hinweis](../../img/w/w18/hinweis.png)

- Bei mehreren ISOs erscheint ein **Step 4:...** welcher optional ist.

  ![iso grösse](../../img/w/w18/12.png)

- Bei wieder Verwendung von YUMI kann man unter **Reinstall or Update?** nachschauen welche die aktuellste Version ist und welche Version auf dem Gerät installiert ist.

  ![optional](../../img/w/w18/optional.png)

!!! warning
    Bei Hinzufügung von einem ISO auf einem USB-Stick kein Reinstall durchführen, sonst werden alle schon vorhandenen ISO's gelöscht.

---

<a name="YUMIboot"></a>
### Probleme beim Booten

Möchte man von einem USB-Stick aus booten, bekommt aber die Meldung "" kann man wie folgt vorgehen.

---

<a name="FirmUp"></a>
## Firmware Update bei hp Drucker

1. **Drucker suchen**

    Unter **Print Management** nach dem Drucker suchen und Doppel klick auf den Druckernamen.

    ![Drucker liste](../../img/w/w12/1.png)

2. **Produktname suchen**

    Unter **General** wurde der Produktname bei dem Kommentar hinterlegt.

    ![Produktname](../../img/w/w12/2.png)

3. **Nach Software und Treiber von Produkt suchen**

    Auf der hp Seite den Produktnamen angeben. Wie auf dem Bild zu sehen reicht der markierter teil. [hp Link](https://support.hp.com/ch-de/drivers/printers)

    ![hp seite](../../img/w/w12/6.png)

4. **Nach Firmware suchen**

    Auf der neu erschienenen Seite nach Firmware suchen. Es kann kein oder mehrere Updates vorhanden sein. Bei einem passenden update auf **Herunterladen** klicken.

    ![hp seite](../../img/w/w12/8.png)

5. **exe Datei starten**

    Nach einigen Sekunden muss man unten **Run** anwählen.

    ![exe datei](../../img/w/w12/9.png)

6. **Drucker suche**

    Bei diesem Schritt des Prozesses sucht es nach Druckern, die zu dem heruntergeladenen Update passt.

    ![printer suche](../../img/w/w12/10.png)

7. **Drucker Auswahl**

    Da auf meiner Drucker liste, mehrere Drucker wahren, die dem gleichen Model entsprachen, bekam ich eine grössere Auswahl als nur der von mir gesuchte Drucker. 

    ![printer suche](../../img/w/w12/11.png)

8. **Password Eingabe**

    Nach dem Anwählen von dem Drucker, bei dem ich das Update machen möchte, muss ich noch ein Password eingeben.

    ![printer pwd](../../img/w/w12/12.png)

9. **Update starten**

    Nun kann man unten **Update** anwählen. Nach der Installierung kann man alle Fenster schliessen.

    ![Installierung](../../img/w/w12/13.png)

---
<a name="BootC"></a>
## Windows 10 mit dem Boot Camp-Assistenten auf einem Mac installieren


### Voraussetzungen für die Installation von Windows 10 auf einem Mac

- MacBook von 2015 oder neuer
- MacBook Air von 2012 oder neuer
- MacBook Pro von 2012 oder neuer
- Mac mini von 2012 oder neuer

- iMac von 2012 oder neuer1
- iMac Pro (alle Modelle)
- Mac Pro von 2013 oder neuer

!!! warning Anforderung
    Mindestens 64 GB freien Speicherplatz auf dem Startvolume des Mac.

1. **Einstellung für "Sicheres Starten" prüfen**

    Vor der Installation von Windows sollte man die Einstellung auf "Volle Sicherheit" stellen. Nach der Installation von Windows kann man mit jeder Einstellung für "Sicheres Starten" von Windows aus starten.[Link zur Anleitung um sicheres Starten überprüfen.](https://support.apple.com/de-de/HT208198)

2. **Mit dem Boot Camp-Assistenten eine Windows-Partition erstellen**

    Vom Finder aus zu **Programme > Dienstprogramme > Boot Camp-Assistent** navigieren. Dort den Boot Camp-Assistent starten.

    ![Boot Camp-Assistent](../../img/w/w6/1.png)

    - Wenn der Boot Camp-Assistent dazu auffordert, die Größe der Windows-Partition festzulegen, muss man die oben genante mind. grösse berücksichtigen.

    !!! warning Anforderung
        Die Partitionsgrösse kann später nicht mehr geändert werden.

3. **Windows-Partition (BOOTCAMP) formatieren**

    Nach der Ausführung des Boot Camp-Assistenten wird der Mac neu gestartet und kehrt zum Installationsprogramm zurück. Wenn man nach dem Installationsprogramm gefragt wird, wo Windows installiert werden soll, muss man die BOOTCAMP-Partition an wählen, und dan auf "Formatieren" klicken.

    !!! info
        In den meisten Fällen wird die richtige BOOTCAMP-Partition vom Installationsprogramm automatisch ausgewählt und formatiert.

4. **Windows installieren**

    Nun am besten alle externen Geräte, die während der Installation nicht benötigt werden trennen. Dann auf "Weiter" klicken. Folgend den Anweisungen auf dem Bildschirm folgen, um Windows zu installieren.

5. **Boot Camp-Installationsprogramm unter Windows verwenden**

    Nach Abschluss der Windows-Installation wird der Mac unter Windows gestartet und das Fenster "Willkommen beim Boot Camp-Installationsprogramm" geöffnet. Nach dem beflogen der Anweisungen auf dem Bildschirm, werden die Boot Camp- und Windows-Support-Software (Treiber)installiert. Sobald dies fertig ist, wird man dazu aufgefordert, den Computer neu zu starten.

### Wechsel zwischen Mac und Windows

Um zwischen den beiden zu wechseln, muss man bei einem Neustart, die Wahltaste (oder die Alt-Taste) ⌥ während des Startvorgangs gedrückt halten. [Link zur kurz Anleitung von Apple.](https://support.apple.com/de-de/HT208123)
