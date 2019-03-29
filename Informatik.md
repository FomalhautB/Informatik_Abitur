
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

## Java

#### Arrays
* **Eigenschaften**
    * nicht flexibel
    * schnell
    * feste Länge
* **Beispiel**
    ```
    // Initialisierung
    String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

    // Länge
    cars.length;

    //get mit Index
    cars[0];

    // for loop
    for (int i = 0; i < cars.length; i++) {
        System.out.println(cars[i]);
    }
    ```

#### ArrayList
* **Eigenschaften**
    * flexibel
    * Kein primitiver Datentyp
* **Beispiel**
    ```
    // Arraylist importieren
    import java.util.ArrayList;

    // Initialisierung
    ArrayList<String> cars = new ArrayList<String>();

    //Objekten hinzufügen
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");

    //get
    cars.get(0);

    //Index eines Objects
    cars.indexOf("BMW");

    //enthalten
    cars.contains("VW");

    //set
    cars.set(0, "Opel");

    //remove
    cars.remove(0)

    // Länge
    cars.size();

    //for loop
    for (int i = 0; i < cars.size(); i++) {
      System.out.println(cars.get(i));
    }
    ```
#### Java
![](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/10/java-cheatsheet.jpg)

#### OOP in Java
![](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/11/Java_OOP-Cheat_Sheet_Edureka.png)

## Objektorientierte Programmierung

#### Datenkapselung
* **Definition**
    * Verbergen von Daten oder Informationen vor dem Zugriff von außen
* **Verwendete Zugriffsarten**
    * public (+)
        * Zugreifbar für alle Objekte (auch die anderer Klassen)
    * private (-)
        * Nur für Objekte der eigenen Klasse zugreifbar
    * protected (#)
        * Nur für Objekte der eigenen Klasse und von Spezialisierungen derselben zugreifbar

#### Konstruktoren
* Methode zum Erzeugen des Objekts
* Attribute (Instanzvariablen) zu initialisieren
* Klassenbeziehungen können realisiert werden
* kein Rückgabewert
* Name ist Klassenname
* mehrere Konstruktoren sind möglich

#### Vererbung
* Attribute und Methoden der Oberklasse werden übernommen
* weitere A. und M. können hinzugefügt werden (Erweiterung)
* Attribute der Oberklasse werden in der Unterklasse im Konstruktor mit super an die Oberklasse weitergegeben
* Schlüsselwort extends

#### Polymorphie
* Vielgestalt
* Objekte könne zur Laufzeit ihren Typ ändern,
* Dieses Prinzip wird Ersetzbarkeit genannt. Objekte von Subtypen(Untertypen) können an allen Stellen verwendet werden, an denen ein Supertyp (Obertyp) erwartet wird. Wenn zum Beispiel jemand nach einem Stift (Oberklasse) fragt, kann man ihm problemlos einen Bleistift oder einen Kugelschreiber (Unterklasse)anbieten.
* es wird zur Laufzeit entschieden, welche Methode aufgerufen wird

#### Assoziation und Aggregation
* **Assoziation**
    * Kennt-Beziehung
    * wird in Java durch Parameterübergabe realisiert
* **Aggregation**
    * Hat-Beziehung
    * wird in Java durch Erzeugen eines Objekts realisiert

![](https://i.stack.imgur.com/bfBSY.png)

## Algorithmen

#### Binäre Suche
* **Verfahren**
    * Beginn der Suche in der Mitte der Liste
    * Fallunterscheidung für betrachteten Eintrag:
        * Falls Schlüssel kleiner als Suchschlüssel: rechts weitersuchen
        * Sonst: in linker Hälfte der Liste weitersuchen
    * Für linke oder rechte Hälfte wieder mittleren Eintrag betrachten
        * Halbierung fortsetzen, bis Suchschlüssel gefunden
* **Implementierung**
    ```
    // A recursive binary search function. It returns
    // location of x in given array arr[l..r] is present,
    // otherwise -1
    int binarySearch(int arr[], int l, int r, int x)
    {
        if (r >= l) {
            int mid = l + (r - l) / 2;

            // If the element is present at the middle
            // itself
            if (arr[mid] == x)
                return mid;

            // If element is smaller than mid, then
            // it can only be present in left subarray
            if (arr[mid] > x)
                return binarySearch(arr, l, mid - 1, x);

            // Else the element can only be present
            // in right subarray
            return binarySearch(arr, mid + 1, r, x);
        }

        // We reach here when element is not
        // present in array
        return -1;
    }
    ```
* **Analysis**
    * Worst-case: O(log n)
    * Best-case: O(1)
    * Average: O(log n)

#### Sortieren durch Auswählen (Selection Sort)
* **Verfahren**
    * Suche das kleinste Element im Array. Tausche es gegen das erste Element aus.
    * Suche das zweitkleinste Element im Array. Tausche es gegen das zweite Element aus.
    * Suche das drittkleinste Element im Array. Tausche es gegen das dritte Element aus.
    * ...
    * Suche das (n-1)kleinste Element im Array. Tausche es gegen das (n-1)ste Element aus.
* **Implementierung**
    ```
    void selectionSort(int arr[])
    {
        int n = arr.length;

        // One by one move boundary of unsorted subarray
        for (int i = 0; i < n-1; i++)
        {
            // Find the minimum element in unsorted array
            int min_idx = i;
            for (int j = i+1; j < n; j++)
                if (arr[j] < arr[min_idx])
                    min_idx = j;

            // Swap the found minimum element with the first
            // element
            int temp = arr[min_idx];
            arr[min_idx] = arr[i];
            arr[i] = temp;
        }
    }
    ```
* **Analysis**
    * Worst-case: О(n^2)
    * Best-case:О(n^2)
    * Average: О(n^2)

#### Sortieren durch Einfügen (Insertion Sort)
* **Verfahren**
    * Die Elemente werden ab Index 1 der Reihe nach von links nach rechts betrachtet.
    * Merke dir das Element bei Index i.
    * Suche links von Index i den so genannten Einfügeindex des Elementes. Die Suche starte dabei bei Index i-1 und läuft von rechts nach links. Es wird jeweils verglichen, ob das Element am Suchindex kleiner oder gleich dem gemerkten Element ist. Ist das nicht der Fall, wird das Element des Suchindex um eine Position nach rechts verschoben. Wird ein solches Element bei Index j gefunden, lautet der Einfügeindex j+1. Wird überhaupt kein solches Element gefunden, lautet der Einfügeindex 0.
    * Füge das gemerkte Element beim Einfügeindex in das Array ein.
* **Implementierung**
    ```
    void insertionSort(int arr[])
    {
        int n = arr.length;
        for (int i = 1; i < n; ++i) {
            int key = arr[i];
            int j = i - 1;

            /* Move elements of arr[0..i-1], that are
               greater than key, to one position ahead
               of their current position */
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key;
        }
    }
    ```
* **Analysis**
    * Worst-case: О(n^2)
    * Best-case: O(n)
    * Average: О(n^2)

#### Quick Sort
* **Verfahren**
    * Wähle das erste Element aus der Menge von Daten aus. Diese Element nennt man auch das Pivot-Element
    * Teile die Menge der Daten in zwei Hälften: Die Daten in der einen Hälfte sind alle kleiner oder gleich dem ausgewählten Element. Die Daten in der anderen Hälfte sind alle größer oder gleich dem ausgewählten Element. Dieser Vorgang wird auch als Partitionierung bezeichnet.
* **Implementierung**
    ~~~
    /* This function takes last element as pivot,
    places the pivot element at its correct
    position in sorted array, and places all
    smaller (smaller than pivot) to left of
    pivot and all greater elements to right
    of pivot */
    int partition(int arr[], int low, int high)
    {
        int pivot = arr[high];  
        int i = (low-1); // index of smaller element
        for (int j=low; j<high; j++)
        {
            // If current element is smaller than or
            // equal to pivot
            if (arr[j] <= pivot)
            {
                i++;

                // swap arr[i] and arr[j]
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }

        // swap arr[i+1] and arr[high] (or pivot)
        int temp = arr[i+1];
        arr[i+1] = arr[high];
        arr[high] = temp;

        return i+1;
    }

    /* The main function that implements QuickSort()
      arr[] --> Array to be sorted,
      low  --> Starting index,
      high  --> Ending index */
    void sort(int arr[], int low, int high)
    {
        if (low < high)
        {
            /* pi is partitioning index, arr[pi] is  
              now at right place */
            int pi = partition(arr, low, high);

            // Recursively sort elements before
            // partition and after partition
            sort(arr, low, pi-1);
            sort(arr, pi+1, high);
        }
    }
    ~~~
* **Analysis**
    * Worst-case: O(n^2)
    * Best-case: O(n log n)
    * Average: O(n log n)

    ## Kryptologie

    <img src="https://programmingwiki.de/images/8/8e/Kryptouebersicht.JPG" width="100%" />

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

    ## Automaten

    #### Endliche Automaten
    * Endliche Automaten sind Modelle, die das Verhalten von Systemen beschreiben
    * Akzeptoren (erkennende Automaten)
    * Transduktoren (schreibende Automaten)

    #### Transduktor
    * Ein Transduktor erzeugt zu jeder gelesenen Eingabe eine Ausgabe
    * **Formale Darstellung (7-Tupel)**
        * Eingabealphabet
        * Ausgabealphabet
        * Zustandsmenge
        * Anfangszustand
        * Menge der Endzustände
        * Übergangsfunktion
        * Ausgabefunktion

    #### Akzeptor
    * Ein Akzeptor liest Eingaben und prüft sie auf eine bestimmte Bedingung
    * **Formale Darstellung (5-Tupel)**
        * Eingabealphabet
        * Zustandsmenge
        * Anfangszustand
        * Menge der akzeptierenden Endzustände
        * Übergangsfunktion

    #### Formale Sprachen
    * **Formale Darstellung (4-Tupel)**
        * Terminalsymbole
        * Nichtterminale Symbole N
        * Startsymbol
        * Produktionsregeln

    #### Kellerautomat
    * Der Kellerautomat ist ein endlicher Automat, der um einen Kellerspeicher erweitert wurde.
    * **Formale Darstellung (7-Tupel)**
        * Zustandsmenge
        * Eingabealphabet
        * Kelleralphabet
        * Zustandsübergangsfunktion
        * Anfangszustand
        * Anfangssymbol im Keller
        * Menge der Endzustände

    #### Turingmachine
    * Die Turing­maschine hat ein Steuerwerk, in dem sich das Programm befindet. Die Turing­maschine kann mit einem Schreib-Lese-kopf auf ein Arbeitsband zugreifen, sie kann dabei Zeichen auf dem Arbeitsband lesen und Zeichen auf das Arbeitsband schreiben. Ferner kann sie den Schreib-Lese-kopf nach links oder rechts bewegen.
    * **Formale Darstellung (7-Tupel)**
        * Zustandsmenge
        * Eingabealphabet
        * Bandalphabet
        * Überführungsfunktion
            * Die Übergangsfunktion prüft dabei, in welchem Zustand sich die Turing-Machine gerade befindet und welches Zeichen auf dem Band durch den Schreib-Lese-Kopf eingelesen wird
        * Anfangszustand
        * leere Feld (Blank)
        * akzeptierenden Endzustände
