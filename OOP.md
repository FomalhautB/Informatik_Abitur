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
* Möglichkeit, Attribute (Instanzvariablen) zu initialisieren
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
