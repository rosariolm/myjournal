*Wochenbericht NETSEC 2022*

## Ablauf

![Kerberos Tabelle](../img/KerberosTabelle.png)

![Kerberos Ablauf](../img/KerberosAblauf.png)

## Lgende Schlüssel

| Abkürzung      | Bedeutung                                   |
| -------------- | ------------------------------------------- |
| K~A~           | private Key Client                          |
| K~KDC~         | private Key KDC = Langzeitschüssel des TGS  |
| TGS_S~A,KDC~   | TGS_Session Key (Authentisierung)           |
| K~B~           | Langzeitschlüssel des Servers/ Service      |
| Service_K~A,B~ | Service-Session-Key                         |
