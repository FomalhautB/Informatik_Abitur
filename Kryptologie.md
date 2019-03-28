## Kryptologie

<img src="https://programmingwiki.de/images/8/8e/Kryptouebersicht.JPG" width=50% />

#### Caesar-Verfahren
* **Verfahren**
    * Bei der Caesar-Verschlüsselung wird jeder Buchstabe der Nachricht um eine bestimmte Zahl im Alphabet weitergeschoben. Diese Zahl ist der geheime Schlüssel.
* **Kryptoanalyse**
    * Ausprobieren aller 25 möglichen Schlüssel

<img src="https://upload.wikimedia.org/wikipedia/commons/2/2b/Caesar3.svg" width=50% />

#### Ersetzungsverfahren
* **Verfahren**
    * Die Buchstaben des Geheimtextalphabetes werden in beliebiger Reihenfolge zugeordnet
* **Kryptoanalyse**
    * Häufigkeitsanalyse

#### Polyalphabetische Verfahren
* Ein polyalphabetisches Chiffrierverfahren ist ein Verfahren, bei dem ein Buchstabe in der Regel mit verschiedenen Buchstaben chiffriert wird.

#### Vigenère-Verschlüsselung
* **Verfahren**
    * Ähnlich wie bei der Caesar-Verschlüsselung werden die einzelnen Buchstaben des Klartexts im Alphabet zyklisch weitergeschoben. Die entscheidende neue Idee war jedoch, nicht jeden Buchstaben um den selben Wert nach hinten zu verschieben, sondern stattdessen ein Codewort als Schlüssel zu verwenden und den 1. Buchstaben des Textes mit dem 1. Buchstaben des Schlüssels, den 2. mit dem 2. des Schlüssels, usw. Ist man am Ende des Schlüssels angelangt beginnt man wieder mit dem 1. Buchstaben.
* **Kryptoanalyse
    * Kasiski-Test

<img src="https://assets.serlo.org/legacy/56361f7130cc2_48e4b7591620e60cc59e318f77ba4d6ae5def264.svg" width=50% />

#### One-Time-Pad
* Beim One-Time-Pad (deutsch: Verfahren mit Einmalschlüssel) benutzt man ein polyalphabetisches Ersetzungsverfahren (wie z.B. das Vigenère-Verfahren), bei dem der Schlüssel (mindestens) so lang ist wie der Klartext.
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
