*Wochenbericht KW48*

**Arbeitsschritte um ein VLAN hinzuzufügen:**

=== "Ausgangslage"

    ![Ausgangslage 1](../img/w/w48/1.png)

    ![Switch 1](../img/w/w48/2.png)

=== "Sollzustand"

    ![Soll zustand 1](../img/w/w48/3.png)
    ![Soll zustand 1](../img/w/w48/4.png)

???+ example "Arbeitsschritte"
     *Verbinden über Tera Term bei Switch 1:*

     **enable =** Anmeldung

     **conf t =** Wechselt in den config Modus

     **vlan 300 name user_mobile =** Erstellt das vlan 300 mit dem Namen user_mobile

     **exit =** Verlässt den (config-vlan-300) und geht in den config Modus


     **vlan 200 =** Wechselt vom config Modus in den config-vlan-200

     **no untagged ethernet 1/1/25 to 1/1/47 =** Macht das untaggen von Port 25 bis 47 rückgängig und lässt somit Port 48 als einziger untagged

     **exit =** Verlässt den (config-vlan-200) und geht in den config Modus

???+ abstract "Zwischenzustand 1"
     ![](../img/w/w48/5.png)
     ![](../img/w/w48/6.png)

???+ example "Arbeitsschritte"
     **vlan 300 =** Wechselt vom config Modus in den config-vlan-300

     **untagged ethernet 1/1/25 to 1/1/47 =** untagged die Ports 25 bis 47

     **exit =** Verlässt den (config-vlan-300) und geht in den config Modus

     **show running-config =** Zeigt die momentanen Konfigurationen an

     **write me =** Speichert die momentanen Konfiguration

     **exit =** Verlässt den config Modus

???+ abstract "Zwischenzustand 1"
     ![](../img/w/w48/7.png)
     ![](../img/w/w48/8.png)

!!! warning ""
    *Nun die gleichen Konfigurationen bei Switch 2 vornehmen. Danach das Gerät mit der IP 192.168.100.15 an Switch 1, Port 48 anhängen und Gerät mit der Ip 192.168.100.16 an Switch 2, Port 48.*

???+ success "Test 1"
     **Stand:**

     ![](../img/w/w48/9.png)
     ![](../img/w/w48/10.png)

     **Soll:** Client 1 (IP 192.186.100.15) ist am Switch 1, VLAN 200, Port 48 angeschlossen und Pingt erfolgreich Client 2. Client 2 (IP 192.186.100.16) ist am Switch 2, VLAN 200, Port 48 angeschlossen und Pingt erfolgreich Client 1.

     **Ist:** Ping’s wurden erfolgreich übertragen.

     **Warum:**

???+ success "Test 2"
     *Vor dem Test muss Client 1 (IP 192.186.100.15) auf Switch 1, VLAN 300, Port 25 umgesteckt werden und Client 2 (IP 192.186.100.16) auf Switch 2, VLAN 300, Port 47.*

     **Stand:**

     ![](../img/w/w48/11.png)
     ![](../img/w/w48/12.png)

     **Soll:** Client 1 (IP 192.186.100.15) ist am Switch 1, VLAN 300, Port 25 angeschlossen und Pingt erfolgreich Client 2. Client 2 (IP 192.186.100.16) ist am Switch 2, VLAN 300, Port 47 angeschlossen und Pingt erfolgreich Client 1.

     **Ist:** Das Ping kann bei beiden nicht ausgeführt werden.

     **Warum:** Weil bei beiden Ports über die die zwei Switches verbunden sind keine tags gemacht wurden für das VLAN 300.

     **Muss:**

     ![](../img/w/w48/13.png)
 
**Arbeitsschritte um Fehler bei Test 4 zu beheben:**

???+ example "Arbeitsschritte"
     *Verbinden über Tera Term bei Switch 1:*

     **enable =** Anmeldung

     **conf t =** Wechselt in den config Modus

     **vlan 300 =** Wechselt vom config Modus in den config-vlan-300

     **tagged ethernet 1/2/1 =** Tagged am angegebenen Port

     **exit =** Verlässt den (config-vlan-300) und geht in den config Modus

     **show running-config =** Zeigt die momentanen Konfigurationen an

     **write me =** Speichert die momentanen Konfiguration

     **exit =** Verlässt den config Modus

     *Nun die gleichen Konfigurationen bei Switch 2 vornehmen.*

???+ abstract "Zwischenzustand 1"
     ![](../img/w/w48/14.png)


???+ success "Test 3"
     **Stand:**

     ![](../img/w/w48/15.png)
     ![](../img/w/w48/16.png)

     **Soll:** Client 1 (IP 192.186.100.15) ist am Switch 1, VLAN 300, Port 25 angeschlossen und Pingt erfolgreich Client 2. Client 2 (IP 192.186.100.16) ist am Switch 2, VLAN 300, Port 47 angeschlossen und Pingt erfolgreich Client 1.

     **Ist:** Ping’s wurden erfolgreich übertragen.

     **Warum:** Da Ich die zwei Port’s getaged haben.
