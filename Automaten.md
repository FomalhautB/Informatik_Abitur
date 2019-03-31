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
    * Nichtterminale Symbole
    * Startsymbol
    * Produktionsregeln
* **EBNF-Darstellung**
    * {A}
        * Die geschweifte Klammer steht hier für beliebig viele Wiederholungen (auch
gar keine) des eingeklammerten Wortes.
    * [A]
        * Die eckige Klammer steht für optionale Teile.
    * A|B
        * A oder B.
    * (AB)
        * Symbol A und B (in dieser Reihenfolge).
* **Endliche Automat zu formale Sprache**
    * Aus einem vollständigen deterministischen endlichen Automaten (DEA) kann eine Grammatik konstruiert werden, die genau die Sprache erzeugt, die der Automat akzeptiert:
    * Verfahren
        1. die Menge der Zustände wird zur Menge der Nichtterminalzeichen
        2. das Eingabealphabet wird zur Menge der Terminalzeichen
        3. der Startzustand wird zur Startvariablen
        4. der Übergang f (Zi, zj, Zk) = Zk wird zur Produktionsregel Zi -> zj Zk jeder Endzustand Ze liefert die Produktionsregel Ze -> epsilon
        * Ohne Verwendung vonepsilon
        5. Für alle Endzustände Ze ersetzt man Zi -> zj Ze durch Zi -> zj

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


#### Chomsky-Hierarchie
* α, β, γ sind Symbolfolgen bestehend aus Terminalen und Variablen, A und B sind Variablen, a ist ein Terminal
* Typ 0
    * beliebig
    * allgemein
* Typ 1
    * αAβ -> αγβ
    * kontextsensitiv
* Typ 2
    * A -> α
    * kontextfrei
* Typ 3
    * A -> a | aB
    * regulär

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
