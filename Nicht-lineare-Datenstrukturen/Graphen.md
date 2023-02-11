# Graphen

zusammenhängend, gerichtet, ungerichtet, gewichtet, ungewichtet

## Graph

## Edge

## Vertex

# Gerichtet vs ungerichtet

Adjazenzmatrix, Adjazenzliste
Tiefensuche, Breitensuche

# Backtracking

Eleminieren aller Möglichkeiten, die nicht zu dem gewünschten Ziel führen können, um so die Laufzeit zu verringern (Dijkstra: das ausschliessen von Wegen, zu einem Übergangsknoten, zu dem bereits ein kürzerer Weg führt)

# Dijkstra

Algorithmus zum ermitteln des kürzesten Weges von einem gegebenen Startknoten zu einem Endknoten. ACHTUNG auch wieder ein greedy-algorithmus, der nicht die global beste Lösung liefert.

# Hammiltonkreis

# Hammiltonweg

# Eulerkreis

Ein Weg, der jede Kante genau einmal enthält und desses Starknoten auch der Endknoten ist.

Vorraussetzung:
Kein Knoten besitzt einen ungeraden Grad.

# Eulerweg

Ein Weg, der jede Kante genau einmal enthält.

Vorraussetzung:
Genau 2 Knoten besitzten einen ungeraden Grad.

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
