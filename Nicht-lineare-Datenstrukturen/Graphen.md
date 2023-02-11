# Graphen

zusammenhängend, gerichtet, ungerichtet, gewichtet, ungewichtet

## Graph

## Edge
Eine Edge ist eine Verbindung zwischen zwei Knoten. Sie kann auch als Kante oder Verbindung bezeichnet werden.
In der Abiturimplemtation ist diese Verbindung ungerichtet, d.h. die Kante kann in beide Richtungen verlaufen.
Außerdem kann eine Kante markiert werden und hat eine Gewichtung.

### Implementation

```java
Edge edge = new Edge(vertex1, vertex2, 42 /* Gewichtung */);
edge.setMarked(false);
edge.isMarked();
edge.setWeight(42);
edge.getWeight();
edge.getVertices();
```

## Vertex
Ein Vertex ist ein Knoten eines Graphen. Er kann auch als Knotenpunkt oder Knoten bezeichnet werden.
Jeder Vertex hat eine eindeutige ID, die als Schlüssel für den Vertex dient.
Außerdem kann ein Vertex markiert werden.

### Implementation

```java
Vertex vertex = new Vertex("Id meiner Träume");
vertex.setMarked(false);
vertex.isMarked();
vertex.getId();
```

# Gerichtet vs ungerichtet

Adjazenzmatrix, Adjazenzliste
Tiefensuche, Breitensuche

# Backtracking

Eleminieren aller Möglichkeiten, die nicht zu dem gewünschten Ziel führen können, um so die Laufzeit zu verringern (Dijkstra: das ausschliessen von Wegen, zu einem Übergangsknoten, zu dem bereits ein kürzerer Weg führt)

# Dijkstra

Algorithmus zum ermitteln des kürzesten Weges von einem gegebenen Startknoten zu einem Endknoten. ACHTUNG auch wieder ein greedy-algorithmus, der nicht die global beste Lösung liefert.

# Hammiltonkreis

Ein geschlossener Weg, der jeden Knoten genau einmal enthält. Er benötigt mindestens 3 Knoten, da sonst ein Kreis nicht möglich ist.

## Java-Implementation

```java
public boolean isHamiltonnianCircle(Graph graph) {
    List<Vertex> vertices = graph.getVertices();
    vertices.toFirst();
    while (vertices.hasAccess()) {
        Vertex vertex = vertices.getContent();
        List<Vertex> neighbours = graph.getNeighbours(vertex);
        int count = 0;
        neighbours.toFirst();
        while (neighbours.hasAccess()) {
            count++;
            neighbours.next();
        }
        if (count != 2) {
            // No Hamiltonnian Circle
            return false;
        }
    }
    // Hamiltonnian Circle
    return true;
}
```

# Hammiltonweg

Ein Weg, der jeden Knoten genau einmal enthält. Er benötigt mindestens 2 Knoten, da sonst ein Weg nicht möglich ist.

## Java-Implementation

```java
public boolean isHamiltonnianPath(Graph graph) {
    List<Vertex> vertices = graph.getVertices();
    vertices.toFirst();
    while (vertices.hasAccess()) {
        Vertex vertex = vertices.getContent();
        List<Vertex> neighbours = graph.getNeighbours(vertex);
        int count = 0;
        neighbours.toFirst();
        while (neighbours.hasAccess()) {
            count++;
            neighbours.next();
        }
        if (count != 1 && count != 2) {
            // No Hamiltonnian Path
            return false;
        }
    }
    // Hamiltonnian Path
    return true;
}
```


# Eulerkreis

Ein Weg, der jede Kante genau einmal enthält und desses Starknoten auch der Endknoten ist.

Vorraussetzung:
Kein Knoten besitzt einen ungeraden Grad.

## Java-Implementation

```java
public boolean isEulerianCircle(Graph graph) {
    List<Vertex> vertices = graph.getVertices();
    vertices.toFirst();
    while (vertices.hasAccess()) {
        Vertex vertex = vertices.getContent();
        List<Vertex> neighbours = graph.getNeighbours(vertex);
        int count = 0;
        neighbours.toFirst();
        while (neighbours.hasAccess()) {
            count++;
            neighbours.next();
        }
        if (count % 2 != 0) {
            // No Eulerian Circle
            return false;
        }
    }
    // Eulerian Circle
    return true;
}
```

# Eulerweg

Ein Weg, der jede Kante genau einmal enthält.

Vorraussetzung:
Genau 2 Knoten besitzten einen ungeraden Grad.

## Java-Implementation

```java
public boolean isEulerianPath(Graph graph) {
    List<Vertex> vertices = graph.getVertices();
    vertices.toFirst();
    int count = 0;
    while (vertices.hasAccess()) {
        Vertex vertex = vertices.getContent();
        List<Vertex> neighbours = graph.getNeighbours(vertex);
        int countNeighbours = 0;
        neighbours.toFirst();
        while (neighbours.hasAccess()) {
            countNeighbours++;
            neighbours.next();
        }
        if (countNeighbours % 2 != 0) {
            count++;
        }
        vertices.next();
    }
    if (count == 2) {
        // Eulerian Path
        return true;
    }
    // No Eulerian Path
    return false;
}
```

## Minimaler Spannbaum **(sollen hier noch Laufzeiten rein?)**

Teilgraph eines Graphen, der mindestens nötig ist, um alle Knoten möglichst kostengünstig zu verbinden. Zur Berechnung eines minimalen Spannbaums eines zusammenhängenden, gewichteten Graphen gibt es zwei Algorithmen: Kruskal und Prim.<br>
**WICHTIG**: Die Algorithmen bestimmen nur die aktuell beste Möglichkeit, nicht aber die global beste Lösung ([Greedy-Algorithmen](#probleme-mit-greedy-algorithmen)).

### Kruskal

1. Kanten aufsteigend (nach Gewicht) sortieren
2. Kanten einem neuen Graphen schrittweise (beginnend mit der geringsten Gewichtung) hinzufügen
3. Entsteht durch das Einfügen ein Kreis, wird die Kante nicht hinzugefügt.
> Der Algorithmus kann theoretisch abbrechen, sobald alle Knoten mit mindestens einer Kante verbunden sind. Läuft er weiter, wird er aber keine Kanten mehr hinzufügen, da dadurch ein Kreis entstehen würde.

<img src="./.images/kruskal.gif" alt="Kruskal Algorithmus GIF Animation" width="600"/>

(MST: Minimal Spanning Tree | [Quelle](https://www.thealgorist.com/Algo/GraphTheory/Kruskal))

### Prim

1. Einen beliebigen Knoten auswählen
2. Alle Kanten des Knotens einer Liste hinzufügen
3. Der nächste, ausgewählte Knoten ist derjenige, der mit minimalsten Kosten zu erreichen ist
4. Auch die Kanten des neuen Knoten werden der Liste hinzugefügt und es wird wieder ein noch nicht verbundener Knoten mit minimalsten Kosten ausgewählt
5. Dies wird wiederholt, bis alle Knoten des Graphen Teil des neuen Graphen sind.

<img src="./.images/prim.gif" alt="Prim Algorithmus GIF Animation" width="800"/>

([Quelle](https://www.youtube.com/watch?v=T4crSlGNtLM))

## Probleme mit Greedy-Algorithmen

Dijkstra, Kruskal und Prim sind Algorithmen, die nicht in der Lage sind, die global beste Lösung zu finden (heuristische Lösung). Sie finden immer nur die aktuell beste Lösung. Ein Beispiel dafür ist das [Travelling Salesman Problem](https://de.wikipedia.org/wiki/Problem_des_Handlungsreisenden).
