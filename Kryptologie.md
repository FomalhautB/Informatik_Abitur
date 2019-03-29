## Kryptologie

![](https://programmingwiki.de/images/8/8e/Kryptouebersicht.JPG)

#### Caesar-Verfahren
* **Verfahren**
    * Bei der Caesar-Verschlüsselung wird jeder Buchstabe der Nachricht um eine bestimmte Zahl im Alphabet weitergeschoben. Diese Zahl ist der geheime Schlüssel.
* **Kryptoanalyse**
    * Ausprobieren aller 25 möglichen Schlüssel

#### Ersetzungsverfahren
* **Verfahren**
    * Die Buchstaben des Geheimtextalphabetes werden in beliebiger Reihenfolge zugeordnet
* **Kryptoanalyse**
    * Häufigkeitsanalyse

#### Polyalphabetische Verfahren
* Ein polyalphabetisches Chiffrierverfahren ist ein Verfahren, bei dem ein Buchstabe in der Regel mit verschiedenen Buchstaben chiffriert wird.

#### Vigenère-Verschlüsselung
* **Verfahren**
    * Die Idee ist, nicht jeden Buchstaben um den selben Wert nach hinten zu verschieben, sondern stattdessen ein Codewort als Schlüssel zu verwenden und den 1. Buchstaben des Textes mit dem 1. Buchstaben des Schlüssels, den 2. mit dem 2. des Schlüssels, usw. Ist man am Ende des Schlüssels angelangt beginnt man wieder mit dem 1. Buchstaben.
* **Kryptoanalyse**
    * Kasiski-Test

#### One-Time-Pad
* Beim One-Time-Pad benutzt man ein polyalphabetisches Ersetzungsverfahren (wie z.B. das Vigenère-Verfahren), bei dem der Schlüssel mindestens so lang ist wie der Klartext.
* Wenn der Schlüssel keine statistischen Auffälligkeiten aufweist, kann ein Angreifer, der nur den Geheimtext kennt, den Schlüssel und den Klartext nicht rekonstruieren.

#### RSA
* **Verfahren**
    * p, q: ausgewählte Primzahlen
    * N = p*q
    * phi = (p-1)(q-1)
    * Bestimme d und e so, dass gilt: (d*e) mod phi = 1
    * d: geheimer Schlüssel
    * (e, N): öffentlicher Schlüssel
    * m: Klartext (m<N)
    * c: Geheimtext
* **Verschlüsselung**
    * c = m^e mod N
* **Entschlüsselung**
    * cd mod N =  m

#### Schutzziele
* **Vertraulichkeit**
    * keine unautorisierte Informationsgewinnung ist möglich
* **Integrität**
    * die Korrektheit der Daten
* **Authentizität**
    * der Identitätsnachweis und die Authentizität der eigentlichen Daten

#### Hash-Funktion
* **Eigenschaften**
    * **Einwegfunktion**
        * Aus dem Hashwert darf nicht der originale Inhalt erzeugt werden können.
    * **Kollisionssicherheit**
        * Den unterschiedlichen Texten darf nicht derselbe Hashwert zugeordnet sein.
    *** Schnelligkeit**
        * Das Verfahren zu Berechnung des Hashwertes muss schnell sein.
* **MD5**
    * Der Message-Digest Algorithm 5 (MD5) ist eine typische kryptographische Hashfunktion, die aus einer beliebigen Nachricht einen 128-Bit-Hashwert erzeugt.
* **Kryptoanalyse**
    * **Urbildangriff**
        * Bei einem Urbildangriff verfolgt der Angreifer das Ziel, zu einem gegebenen Hashwert einer unbekannten Nachricht (Erster Urbildangriff) oder zu einer gegebenen Nachricht selbst (Zweiter Urbildangriff) eine weitere Nachricht zu konstruieren, die denselben Hashwert besitzt.
    * **Kollisionsangriff**
        * Bei einem Kollisionsangriff verfolgt der Angreifer das Ziel, zwei verschiedene Dokumente zu konstruieren, die beide denselben Hashwert besitzen.

#### Digitale Signatur
* Digitale Signaturen sichern die Integrität bzw. die Authentizität eines Dokuments
* **Verfahren**
    * Der Sender verschlüsselt den Hashwert des Klartextes mit seinem privaten Schlüssel und erzeugt damit seine Signatur.
    * Dokument und Signatur werden dann gemeinsam mit dem öffentlichen Schlüssel des Empfängers verschlüsselt und über den Kanal geschickt.
    * Der Empfänger entschlüsselt dann die erhaltenen Daten mit seinem privaten Schlüssel und erhält den Klartext und die Signatur in entschlüsselter Form.
    * Jetzt wendet der Empfänger noch den öffentlichen Schlüssel des Senders auf die Signatur an und erhält den Klartext der Unterschrift.
* **Signaturzertifikat**
    * Zur Erstellung einer digitalen Signatur benötigen Sie ein Signaturzertifikat, das Ihre Identität nachweist. Wenn Sie ein digital signiertes Dokument senden, übertragen Sie gleichzeitig Ihr Zertifikat und einen öffentlichen Schlüssel.
* **Zertifizierungsstelle (CA)**
    * Sie stellt digitale Zertifikate aus, signiert Zertifikate als Beweis ihrer Gültigkeit und verfolgt, welche Zertifikate widerrufen wurden oder abgelaufen sind.

#### PGP
![](https://upload.wikimedia.org/wikipedia/commons/4/4d/PGP_diagram.svg)
