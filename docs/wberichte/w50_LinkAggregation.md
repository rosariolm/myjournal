*Wochenbericht KW50*

=== "Ausgangslage"

    ![Ausgangslage 1](../img/w/w50/1.png)

=== "Sollzustand"

    ![Soll zustand 1](../img/w/w50/2.png)

???+ example "Arbeitsschritte"
     **enable =** Anmeldung

     **conf t =** Wechselt in den config Modus

     **lag switch_to_switch dynamic id 1 =** Erstellung eines LAG (namen switch_to_switch, dynamisch, id 1)

     **ports ethernet 1/2/1 to 1/2/2 =** Fügt die angegebenen Ports dem LAG hinzu

     **primary-port 1/2/1 =** Setzt den angegebenen Port als Primary Port

     **deploy =** Schaltet dies ein

     **write me =** Speichert die momentanen Konfiguration

     **exit =** Verlässt den (config-lag switch_to_switch dynamic id 1) und geht in den config Modus

     **show running-config =** Zeigt die momentanen Konfigurationen an


???+ abstract "Ausgabe"
     ![Stand 1](../img/w/w50/3.png)

!!! warning "Info"
    Nun muss man noch auf dem VLAN 100 den primary port taggen. Wichtig! Das taggen kann erst nach dem deploy machen ansonsten kommt beim deployen ein Error.

    Nun die gleichen Konfigurationen bei Switch 2 vornehmen.

???+ example "Arbeitsschritte"
     Jetzt bei beiden Switches noch den Primary Port taggen:

     **vlan 100 =** Wechselt vom config Modus in den config-vlan-100

     **tagged ethernet 1/2/1 =** Tagged am angegebenen Port

     **write me =** Speichert die momentanen Konfiguration

     **exit =** Verlässt den (config-vlan-100) und geht in den config Modus

     **show running-config =** Zeigt die momentanen Konfigurationen an

???+ abstract "Ausgabe"
     ![Stand 1](../img/w/w50/4.png)

???+ success "Test 1"
     **Stand:**

     ![](../img/w/w50/5.png)

     **Soll:** Client 1 (IP 192.186.100.15) ist am Switch 1, VLAN 100, Port 47 angeschlossen und Pingt erfolgreich Client 2. Client 2 (IP 192.186.100.16) ist am Switch 2, VLAN 100, Port 47 angeschlossen und Pingt erfolgreich Client 1. Beim ausstecken vom Kabel am Port 1/2/1 an Switch 1 wird das Ping erfolgreich weitergeführt.

     **Ist:** Pings wurden erfolgreich übertragen. Nach einem kurzen unter Bruch beim ausstecken des Kabels wurde das Ping wieder erfolgreich ausgeführt.

     **Warum:** Dank dem Link Aggregation lief das ping dann über den 1/2/2 Port.
