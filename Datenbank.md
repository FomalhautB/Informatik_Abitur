
## Datenbanksystem

#### Kardinalität
* **1:1 Beziehung**
    * Jedem Datensatz einer Tabelle wird genau ein Datensatz einer anderen Tabelle zugeordnet und umgekehrt.
* **1:n Beziehung**
    * Jedem Datensatz einer Tabelle wird genau ein Datensatz einer anderen Tabelle zugeordnet; umgekehrt kann ein Datensatz aber beliebig vielen Datensätzen der anderen Tabelle zugeordnet sein.
* **n:m Beziehung**
    * Jedem Datensatz einer Tabelle werden beliebig viele Datensätze einer anderen Tabelle zugeordnet; umgekehrt werden einem Datensatz ebenfalls beliebig viele Datensätze der anderen Tabelle zugeordnet.

#### Drei-Ebenen-Architektur
* **Die externe Ebene**
    * Die bereitstellt den Benutzern und Anwendungen individuelle Benutzersichten .
* **Die konzeptionelle Ebene**
    * Die beschreibt, welche Daten in der Datenbank gespeichert sind, sowie deren Beziehungen zueinander.
* **Die interne Ebene**
    * Die physischen Speicherstrukturen und Zugriffsmechanismen einer Datenbank.

#### Entity-Relationship-Modell (ERM)
* **Entität (Entity)**
    * individuell identifizierbares Objekt der Wirklichkeit
* **Beziehung (Relationship)**
    * Verknüpfung / Zusammenhang zwischen zwei oder mehreren Entitäten
* **Eigenschaft (Attribute)**
    * Was über eine Entität von Interesse ist

#### Anomalien
* **Einfüge(Insert)-Anomalie**
    * Bei einem fehlerhaften oder inkorrekten Datenbankdesign kann es bei der Einfüge-Anomalie passieren, dass Daten gar nicht in die Datenbank übernommen werden, wenn zum Beispiel der Primärschlüssel keinen Wert erhalten hat, oder eine unvollständigen Eingabe von Daten zu Inkonsistenzen führt.
* **Änderungs(Update)-Anomalie**
    * Bei der Änderungs-Anomalie, auch Update-Anomalie genannt, werden gleiche Attribute eines Datensatzes in einer Transaktion nicht automatisch geändert. So entsteht eine Inkonsistenz der Daten.
* **Lösch(Delete)-Anomalie**
    * Bei einer Löschanomalie kann es passieren, dass ein Benutzer einer Datenbank aktiv Informationen löschen will und damit indirekt, aufgrund des fehlerhaften Datenbankdesigns, andere zusammenhängende Informationen parallel mitlöscht.

#### Normalisierung
* **1. Normalform**
    * Eine Relation befindet sich in der ersten Normalform, wenn alle Attribute nur einfache Attributwerte aufweisen
* **2. Normalform**
    * Eine Relation befindet sich in der zweiten Normalform, wenn
        1. sie in der ersten Normalform ist
        2. jedes Nicht-Schlüssel-Attribut vom Primärschlüssel voll funktional abhängig ist
    * Schrittfolge zur Herstellung der zweiten Normalform
        1. Primärschlüssel der gegebenen Relation festlegen, falls dieser nur aus einem Attribut besteht, so liegt bereits 2. NF vor.
        2. Untersuchung, ob aus Teilschlüsselattributen bereits weitere Attribute folgen. Falls nicht liegt bereits die 2. NF vor. Falls Abhängigkeiten gefunden werden, dann
        3. Neue Relation bilden, die das Teilschlüsselattribut und alle von diesem abhängigen Nichtschlüsselattribute anthalten. Das Teilschlüsselattribut wird in der neuen Relation der Primärschlüssel.
        4. Löschen der ausgelagerten Nichtschlüsselattribute in der Ausgangsrelation.
        5. Vorgang ab 2. wiederholen, bis alle Nichtschlüsselattribute vom gesamten Schlüssel funktional abhängig sind.
* **3. Normalform**
    * Eine Relation befindet sich in der dritten Normalform, wenn
        1. sie in der zweiten Normalform ist
        2. jedes Nichtschlüsselattribute nicht transitiv vom Primärschlüssel abhängig ist, d.h. aus keinem Nichtschlüsselattribut folgt ein anderes Nichtschlüsselattribut
    * Schrittfolge zur Herstellung der dritten Normalform
        1. Untersuchung, ob aus Nichtschlüsselattributen andere Nichtschlüsselattribute folgen. Falls nicht liegt bereits die 3. NF vor. Falls Abhängigkeiten gefunden werden, dann
        2. Neue Relation bilden, die das Nichtschlüsselattribut (wird nun Primärschlüssel der neuen Relation) und die von ihm abhängigen Attribute enthält.
        3. Löschen der ausgelagerten Nichtschlüsselattribute mit Ausnahme des Attributes, das in der neuen Relation Primärschlüssel ist.
        4. Vorgang ab 2. wiederholen, bis keine Abhängigkeiten mehr bestehen

#### Datenschutz
* **Zweck**
    * Der Zweck des Datenschutzgesetzes ist es, die persönlichen Daten zu schützen und vor Missbrauch zu bewahren.
* **Speicherung**
    * Unter dem Speichern von Daten versteht man, dass Daten auf Datenträgern aufgehoben werden.
* **Erhebung**
    * Unter der Datenerhebung versteht man, dass diese gespeicherten Daten sozusagen für die Nutzung dieser Daten beschafft werden.
* **Nutzung**
    * Unter der Datennutzung versteht man, dass diese Daten für irgendeinen Zweck benutzt werden, beispielsweise Statistiken.
* **Recht**
    * Die Speicherung, Erhebung und Nutzung von Daten ist erlaubt, solange sie nicht personenbezogen sind. Sind die Daten personenbezogen, so benötigt man eine schriftliche Einverständniserklärung.
* **Informationelle Selbstbestimmung**
    * Die informationelle Selbstbestimmung ist das Recht jeden einzelnen Bürgers über die Veröffentlichung und Verwendung seiner personenbezogenen Daten zu bestimmen.
* **Datenvermeidung und Datensparsamkeit**
    * §3a: "keine oder so wenig wie möglich personenbezogene Daten zu erheben"

#### SQL-Befehl
![](https://zeroturnaround.com/wp-content/uploads/2016/06/RebelLabs-SQL-cheat-sheet.png)