#Arbeitsheft

## Inhaltsverzeichnis

- [Multiboot-USB-Stick](#YUMI)

- [Firmware Update](#FirmUp)

- [Gerät bei Autopilot hinzufügen](#Autopilot)

    * [Autopilot Script Anpassung](#AutoPilotScript)

- [Bootcamp](#)

- [PIN Deaktivierung in Intune](#)

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

<a name="FirmUp"></a>
## Firmware Update bei hp Drucker

1. Drucker suchen

    Unter **Print Management** nach dem Drucker suchen und Doppel klick auf den Druckernamen.

    ![Drucker liste](../../img/w/w12/1.png)

2. Produktname suchen

    Unter **General** wurde der Produktname bei dem Kommentar hinterlegt.

    ![Produktname](../../img/w/w12/2.png)

3. Nach Software und Treiber von Produkt suchen

    Auf der hp Seite den Produktnamen angeben. Wie auf dem Bild zu sehen reicht der markierter teil. [hp Link](https://support.hp.com/ch-de/drivers/printers)

    ![hp seite](../../img/w/w12/6.png)

4. Nach Firmware suchen

    Auf der neu erschienenen Seite nach Firmware suchen. Es kann kein oder mehrere Updates vorhanden sein. Bei einem passenden update auf **Herunterladen** klicken.

    ![hp seite](../../img/w/w12/8.png)

5. exe Datei starten

    Nach einigen Sekunden muss man unten **Run** anwählen.

    ![exe datei](../../img/w/w12/9.png)

6. Drucker suche

    Bei diesem Schritt des Prozesses sucht es nach Druckern, die zu dem heruntergeladenen Update passt.

    ![printer suche](../../img/w/w12/10.png)

7. Drucker Auswahl

    Da auf meiner Drucker liste, mehrere Drucker wahren, die dem gleichen Model entsprachen, bekam ich eine grössere Auswahl als nur der von mir gesuchte Drucker. 

    ![printer suche](../../img/w/w12/11.png)

8. Password Eingabe

    Nach dem Anwählen von dem Drucker, bei dem ich das Update machen möchte, muss ich noch ein Password eingeben.

    ![printer pwd](../../img/w/w12/12.png)

9. Update starten

    Nun kann man unten **Update** anwählen. Nach der Installierung kann man alle Fenster schliessen.

    ![Installierung](../../img/w/w12/13.png)

---
<a name="Autopilot"></a>
## Gerät bei Autopilot hinzufügen

Bevor man in Intune das Gerät importieren kann. Muss ein Script auf dem jeweiligen Gerät ausgeführt werden.

### Auf dem Gerät

1. Wie auf [THE LAZY ADMINISTRATOR](https://www.thelazyadministrator.com/2020/01/27/get-a-new-computers-auto-pilot-hash-without-going-through-the-out-of-box-experience-oobe/) das Script herunterladen und am besten auf einem USB-Stick speichern, für weiteren gebrauch.

2. Nach dem Download fehlte bei mir noch ein CMD feil welches ich kopiert habe.

3. Nun kann das Get-WindowsAutoPilotInfo.ps1 ausgeführt werden. *Als Admin ausführen!*

4. Nun sollte eine compHas.csv erstanden sein, welche man für den Intune schritt braucht.

![hash datei](../../img/w/w7/w7_7.png)


### In Intune

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
### Autopilot Script Anpassung

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
