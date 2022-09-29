# Zertifikat

*Wochenbericht NETSEC 2022*

## Was ist ein Zertifikat?

Digitale Zertifikate sorgen für mehr Sicherheit in der digitalen Welt. Man könnte sie mit einem Badge oder einer ID vergleichen. Dieser elektronische Echtheitsnachweis prüft beziehungsweise bestätigt die Identität einer Person oder eines Objekts, anhand einem mathematischen Verschlüsselungsverfahren.
Ausgestellt werden sie von vertrauenswürdigen Institutionen (Anbieterinnen von anerkannten Zeritifizierungsdiensten auch Zertifizierungsstellen genannt). Diese sind Staatlich anerkannt und werden regelmässig überprüft.

## Wozu dient ein Zertifikat?

Ein Zertifikat hat mehrere Verwendungszwecke, aber meistens wird es dort angewendet, wo die Identität einer Person (z. B. Organisation, Webseite oder Unternehmen) festgestellt werden muss.
Ein häufig verwendetes Beispiel wäre die digitale Signatur. Bei der digitalen Signatur dient das Zertifikat der Authentifizierung der Person, die unterschreiben hat (bestätigt also die Identität des Signieren).

## Was ein Zertifikat verhindert!

Mit einem Zertifikat kann eine Attacke mit der Angriffsform "Man in the Middle" verhindert werden. Somit kann man verhindern, dass ein Angriff er die Daten abfängt, abändert oder sogar fälscht. Dies weil die Zertifizierungsstellen die Identität der Zertifikatsinhaber vorher prüfen und mit einer Signatur bestätigt.

## Einsatzbereich

Da ein Zertifikat wie ein Identitätsnachweis ist und Auskunft über die Identität gibt, hat es verschiedene Bereiche, in dem er gebraucht wird.

**Beispiel:**

- **Digitale Signatur:** Das Zertifikat identifiziert die unterzeichnende Person oder das unterzeichnende Unternehmen.
- **E-Mail-Signatur:** Das Zertifikat bestätigt die Echtheit des E-Mails sowie deren Sender und zusätzlich garantiert es die sichere Übertragung an den Empfänger. 
- **Webseiten (SSL/TLS):** Das Zertifikat garantiert, dass der Inhalt wirklich von der Web-Adresse stammt, die man sieht (HTTPS).

## Inhalt und Standards

Ein Zertifikat stellt verschiedene Informationen zur Verfügung wie Identität der Person, Informationen eines Unternehmens oder Objekt.

**Inhalt eines Zertifikats:**

- Name des Zertifikatinhabers
- Zertifizierungsstelle
- Gültigkeitsdauer
- Seriennummer
- Öffentlicher Schlüssel des Inhabers, zur Überprüfung der Echtheit des Schlüssels
- Digitale Signatur der Zertifizierungsstelle, zur Überprüfung der Echtheit des Zertifikats. 

X.509 wird als ITU-T-Standard für eine public-Key-infrastruktur eingesetzt bei der Erstellung des Zertifikats. Dieser Standard definiert, wie das Zertifikat aufgebaut werden muss.
