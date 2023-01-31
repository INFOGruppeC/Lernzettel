# Suchen und Sortieren
Hier findest du die Lernzettel zum Thema Suchen und Sortieren

## Inhaltsverzeichnis
 - Datenstrukturen
   - [Array](./SuS%20Array.md)
   - [List](./SuS%20List.md)
 - Algorithmen
   - [Sortieren](#sortieren)
     - [Insertion Sort](#insertion-sort)
     - [Selection Sort](#selection-sort)
     - [Bubble Sort](#bubble-sort)
     - [Quicksort](#quick-sort)
   - [Suchen](#suchen)
     - [Lineare Suche](#lineare-suche)
     - [Binäre Suche](#binäre-suche)


## Suchen

### Lineare Suche

#### Funktionsweise:

<img src=".images/java_array.jpg" alt="Java Array Grafik" width="400"/>

Die lineare Suche sucht nach einem Element in einer Liste, indem es jedes Element der Liste mit dem gesuchten Element vergleicht. Wenn das gesuchte Element gefunden wurde, wird die Position des Elements zurückgegeben. Wenn das gesuchte Element nicht gefunden wurde, wird -1 zurückgegeben.

#### Vorteile:

- Einfache Implementation
- Code ist leicht zu verstehen
- Best Case: $O(1)$
- Average Case: $O(n)$
- Keine Sortierung der Liste notwendig -> Keine Auswirkung auf die Laufzeit

#### Nachteile:

- Worst Case: $O(n)$

### Binäre Suche

#### Funktionsweise:

Die binäre Suche sucht nach einem Element in einer Liste, indem es das Element in der Mitte der Liste mit dem gesuchten Element vergleicht. Wenn das gesuchte Element kleiner ist, wird die linke Hälfte der Liste betrachtet. Wenn das gesuchte Element größer ist, wird die rechte Hälfte der Liste betrachtet. Wenn das gesuchte Element gefunden wurde, wird die Position des Elements zurückgegeben. Wenn das gesuchte Element nicht gefunden wurde, wird -1 zurückgegeben.

#### Vorteile:

- Best Case: $O(1)$
- Average Case: $O(log(n))$
- Worst Case: $O(log(n))$

#### Nachteile:
- Komplizierte Implementation
- Wenn die Liste nicht sortiert ist, muss sie sortiert werden
- Weniger überblickbar als die lineare Suche

## Sortieren

### Insertion Sort


#### Funktionsweise:

In jedem Durchlauf wird ein Element aus dem Array genommen und an die richtige Stelle in der sortierten Liste eingefügt.
Dazu wird das Element mit dem letzten Element der sortierten Liste verglichen. Falls das Element grösser ist, wird es an die letzte Stelle der sortierten Liste gesetzt. Falls das Element kleiner ist, wird es an die Stelle gesetzt, an der das Element grösser ist als das Element, welches gerade verglichen wird.


#### Vorteile: 
- Leicht zu implementieren
- Best Case: $O(n)$ (wenn die Liste schon sortiert ist)
- Stabil
- Benötigt nur wenig Speicherplatz

#### Nachteile 
- Worst Case: $O(n^2)$

### Selection Sort

#### Funktionsweise:

In jedem Durchlauf wird das kleinste Element aus dem Array genommen und an die erste Stelle der sortierten Liste gesetzt. Dies wird so oft wiederholt, bis das Array leer ist.
Dazu wird das kleinste Element gesucht und mit dem ersten Element der sortierten Liste getauscht. Anschließend wird das zweitkleinste Element gesucht und mit dem zweiten Element der sortierten Liste getauscht. Dies wird so oft wiederholt, bis das Array leer ist.


#### Vorteile: 
-  Einfache Implementation
-  Stabil
-  Benötigt nur wenig Speicherplatz
-  Immer $O(n^2)$

#### Nachteile 

-  Kein Best Case
### Bubble Sort

#### Funktionsweise:

Jeden Durchlauf werden die benachbarten Werte verglichen und falls das Element hinter dem aktuellen grösser ist, als das aktuelle, werden diese Getauscht. 

#### Vorteile: 
- Bei fast richtig sortierten Datensätzen wird bestenfalls nur ein Durchlauf benötigt => guter best case
- Einfache Implementation 
- Einfaches Grundprinzip

#### Nachteile 

- Bei einem Datensatzt, der genau "falschrum" sortiert ist wird eine hohe anzahl an vergleichen benötigt => schlechter worstcase
- => schlecht Abschätzbar (geringe Stablilität)

### Quick Sort

#### Funktionsweise:
  Der Datensatzt wird in zwei Datensätze geteilt, je nachdem ob sie größer oder kleiner als der Referenzwert sind. Diese Listen werden dann rekursiv erneut geiteilt bis nur noch ein Wert vorliegt und man die nun sortierten Einzelwerte zusammenfügt


#### Vorteile: 
 - Schnell
 - Rekursiv
 - Average Case: $O(n*log(n))$
 - Best Case: $O(n*log(n))$
 - Geringer Speicherbedarf da in-place
  

#### Nachteile 
- Umständliche Implementation
- Nicht stabil
- Worst Case: $O(n^2)$
- Mehr Speicherbedarf durch Rekursion