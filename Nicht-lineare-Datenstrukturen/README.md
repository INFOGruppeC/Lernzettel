# Nicht lineare Datenstrukturen

Der Quellcode der unbearbeiteten Abiturklassen, und wie auf dem [Lernzettel nichtlineare Datenstrukturen](../../Nicht%20lineare%20Datenstrukturen.md) beschrieben.

- [BinarySearchTree](../Abiturklassen/BinarySearchTree.java)
- [](../Abiturklassen/BinarySearchTree.java)
- [](../Abiturklassen/BinarySearchTree.java)

|Erklärung|Implementation|
|-|-|
Der Auftrag fügt den Knoten pVertex vom Typ Vertex in den Graphen ein, sofern es noch keinen Knoten mit demselben ID-Eintrag wie pVertex im Graphen gibt und pVertex eine ID ungleich null hat. Ansonsten passiert nichts | `addVertex(Vertex pVertex)`
|Der Auftrag fügt die Kante pEdge in den Graphen ein, sofern beide durch die Kante verbundenen Knoten im Graphen enthalten sind, nicht identisch sind und noch keine Kante zwischen den beiden Knoten existiert. Ansonsten passiert nichts.|`addEdge(Edge pEdge)`
Der Auftrag entfernt den Knoten pVertex aus dem Graphen und löscht alle Kanten, die mit ihm inzident sind. Ist der Knoten pVertex nicht im Graphen enthalten, passiert nichts. | `removeVertex(Vertex pVertex)`
||`removeEdge(Edge pEdge)`
||`getVertex(String pID) => Vertex`
||`getVertices() => List <Vertex>`
||`getNeighbours(Vertex pVertex) = List <Vertex>`
||
||
||
||