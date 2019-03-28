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
