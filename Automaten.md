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
