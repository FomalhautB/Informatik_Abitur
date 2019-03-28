## Algorithmus

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

![](https://upload.wikimedia.org/wikipedia/commons/thumb/a/aa/Binary_search_complexity.svg/440px-Binary_search_complexity.svg.png)

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

![](http://interactivepython.org/runestone/static/pythonds/_images/selectionsortnew.png)

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

![](http://interactivepython.org/courselib/static/pythonds/_images/insertionsort.png)

#### Quick Sort
* **Verfahren**
    * Wähle das erste Element aus der Menge von Daten aus. Diese Element nennt man auch das Pivot-Element
    * Teile die Menge der Daten in zwei Hälften: Die Daten in der einen Hälfte sind alle kleiner oder gleich dem ausgewählten Element. Die Daten in der anderen Hälfte sind alle größer oder gleich dem ausgewählten Element. Dieser Vorgang wird auch als Partitionierung bezeichnet.
* **Implementierung**
    ```
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
    ```
* **Analysis**
    * Worst-case: O(n^2)
    * Best-case: O(n log n)
    * Average: O(n log n)

![](http://interactivepython.org/courselib/static/pythonds/_images/partitionA.png)
