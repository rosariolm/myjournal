## 5. Layer 3 Vermittlung (Network)

Die Layer 3 im ISO/OSI-Schichtenmodell ist für die Vermittlung der Daten über die einzelnen Verbindungsabschnitte zuständig. Sie kümmert sich um die Adressierung und das Finden des schnellsten Wegs zum Ziel. Andere Bezeichnungen für die Layer 3 sind Vermittlungsschicht, Netzwerkschicht oder Network Layer.
Im TCP/IP nennt sich die Wegfindung durch das IP-Netz, Routing. Das Routing kann statisch wie auch dynamisch definiert sein.
In den einzelnen Routern zwischen der Quelle und dem Ziel werden die Informationen der Layer 3 wie beispielsweise das Ziel und die Absende Adresse ausgewertet und für das Routing verwendet. Hierfür stellt die Network Layer ein eindeutiges Adresskonzept zur Verfügung.

### 5.1 IPv4-Adressierung

Die wichtigste Aufgabe von IP (Internet Protocol) ist, dass jeder Host in einem dezentralen TCP/IP-Netzwerk gefunden werden kann. Dazu wird jedem Hardware-Interface (Netzwerkkarte oder -adapter) eine logische IPv4-Adresse zugeteilt.
Die IPv4-Adresse ist mit den Angaben zu Straße, Hausnummer und Ort vergleichbar.

#### 5.1.1 Aufbau einer IPv4-Adressierung

Damit die IPv4-Adresse von Hardware und Software einfach verarbeitet werden kann, besteht sie aus einer Bitfolge aus Einsen (1) und Nullen (0). Sie ist somit maschinenlesbar. Die Bitfolge hat 32 Stellen (4 Byte (32 Bit) groß).

![IPv4 Schreibweise](../img/a/inf/Tabelle13.png)

32 Bit werden in einer IPv4-Adresse in jeweils 8 Bit (1 Byte) aufgeteilt und durch einen Punkt voneinander getrennt. Dabei kann jedes Byte durch die achtstellige 1er- und 0er-Folge einen dezimalen Wert von 0 bis 255 annehmen. Somit ergibt die binäre IPv4-Adresse 01111111.00000000.00000000.00000001 die IPv4-Adresse 127.0.0.1.
Neben der üblichen Binär und Dezimal Schreibweise können die Ipv4-Adressen auch mit Oktal zahlen und hexadezimal Zahlen angegeben werden.

#### 5.1.2 Struktur im IPv4-Adressraum

Der IPv4-Adressraum umfasst 32 Bit und geht von 0.0.0.0 bis 255.255.255.255. Das entspricht über 4 Milliarden Adressen. Als man den Adressraum definierte, entsprach das damals ungefähr der Weltbevölkerung. Damals war es undenkbar, dass jeder Mensch irgendwann mal eine IPv4-Adresse brauchen, und schon gar nicht, dass jemand ein persönliches Endgerät (Smartphone) mit einer IPv4-Adresse besitzen würde.

Man sich eine Art Verzeichnis überlegt, wo drinsteht, wo sich eine IPv4-Adresse im Netzwerk befindet. Bei Telefonnummern kennen wir die Aufteilung in Ländervorwahl und Ortsvorwahl. So eine Struktur hatte man sich auch bei IPv4-Adressen vorgestellt. Damit IP-Router möglichst effizient arbeiten können, wurden IPv4-Adressen anfangs hierarchisch zugeteilt. Das hat aber nicht sehr lange funktioniert. Wegen einem zu geringen Adressraum gilt die regionale Zuteilung, wie bei Telefonnummer, nicht mehr.

![IPv4 Struktur](../img/a/inf/Tabelle14.png)

### 5.2 Spezielle und private Adress-Bereiche

**Privat:**

Die IPv4 Adressen sind begrenzt und müssen deswegen beantragt werden. Deshalb kann man nicht jede beliebige Adresse verwenden. Aber es gibt spezielle Adressräume für private und nicht öffentliche Nutzung.
Wenn man nun ein privates lokales Netzwerk aufbauen möchte, verwendet man solche privaten IPv4-Adressen, wenn man zu wenige oder keine öffentlichen IPv4-Adressen hat. Die privaten IPv4-Adressen haben aber den Nachteil, dass sie nur im jeweiligen lokalen Netzwerk gültig sind und nicht in öffentliches Netz geroutet werden. Datenpakete mit privaten IPv4-Adressen verbleiben in den lokalen Netzwerken. Umgekehrt heißt das auch, dass Hosts, die nur eine private IPv4-Adresse haben, nicht direkt aus dem Internet erreichbar sind.

![Privat Adressen](../img/a/inf/Tabelle14.png)

**Spezielle:**

127.0.0.0 - 127.255.255.255 Spezielle Adressen für den eigenen Rechner (localhost).
Diese Adressen kann man im Normalfall nicht verwenden. 127.0.0.1 ist im Normalfall die eigene Loopback-Adresse
0.0.0.0 Spezielle Adresse, wird im Normalfall genutzt für die Defaultroute


### 5.3 Reservierte und nicht verfügbare IPv4-Adressen/Subnetze

Im Adressbereich von 0.0.0.0 bis 255.255.255.255 sind bestimmte Adressen und Subnetze für reserviert oder gesperrt. Dies ist gut zu wissen, um eine fehlerhafte IPv4-Konfiguration zu vermeiden oder zu erkennen.

**Die erste und letzte IPv4-Adresse eines Subnetzes sind reserviert**

- Die erste IPv4-Adresse eines Subnetzes adressiert das Netz und ist somit die Netz-Adresse.

- Die letzte IPv4-Adresse eines Subnetzes adressiert alle Teilnehmer in dem Netzwerk und ist somit die Broadcast-Adresse.

**Nicht routbare IPv4-Adressen**

- 0.0.0.0/8 (0.0.0.0 bis 0.255.255.255): Standard- bzw. Default-Route im Subnetz (Current Network).

- 127.0.0.0/8 (127.0.0.0 bis 127.255.255.255): Reserviert für den Local Loop bzw.Loopback.

**Private IPv4-Adressen**

-	10.0.0.0/8 (10.0.0.0 bis 10.255.255.255)

-	172.16.0.0/12 (172.16.0.0 bis 172.31.255.255)

-	192.168.0.0/16 (192.168.0.0 bis 192.168.255.255)

-	169.254.0.0/16 (169.254.0.0 bis 169.254.255.255)

**Class D (Multicast)**

-	224.0.0.0 bis 239.255.255.255: Nicht im Internet, sondern nur lokal in den eigenen Netzen routbar.

**Class E (reservierte Adressen)**

-	240.0.0.0 bis 255.255.255.255: Alte IPv4-Stacks, die nur mit Netzklassen arbeiten, kommen damit nicht klar.
 
### 5.4 Umrechnung

### 5.5 Übersicht Standards

### 5.6 Subnetting

#### 5.6.1 Subnetzmaske

#### 5.6.2 Netzwerkadresse berechnen
