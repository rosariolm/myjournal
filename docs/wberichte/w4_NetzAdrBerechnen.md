*Wochenbericht KW4*

Die IP Adresse wie die Netzmaske müssen in Binär dargestellt werden. Die werden dann abgeglichen und die Einer (1) die sich bei beiden an der gleichen Stelle der Bitfolge befinden, werden bei der Netzadresse übernommen. Diese muss man zu Schluss nur noch in Dez umwandeln.

**Beispiel:**

172.17.196.0 /21 = 255.255.248.0

| IP Adresse      | 1010 1100     | 0001 0001     | 1100 0100     | 0000 0000	  |
|                 |               |               |               |               |
| **Netzmaske**   | **1111 1111** | **1111 1111** | **1111 1000** | **0000 0000** |
| **Netzadresse** | **1010 1100** | **0001 0001** | **1100 0000** | **0000 0000** |

**= 172.17.192.0** 
