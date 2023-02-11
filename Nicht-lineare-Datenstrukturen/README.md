# Nicht lineare Datenstrukturen

Nicht lineare Datenstrukturen ist ein Sammelbegriff, unter welchem sich alle Datenstrukturen fallen, welche nicht zu den linearen gehören. Nicht lineare Datenstrukturen sind meist hierarchische Strukturen (tree structures) oder geflechtartigen Strukturen (plex structures).

Der Quellcode der unbearbeiteten Abiturklassen, und wie auf dem [Lernzettel nichtlineare Datenstrukturen](../../Nicht%20lineare%20Datenstrukturen.md) beschrieben.


## Suchen und Sortieren

Nicht lineare Datenstruktren besitzen meistens einen Hauptfokus, weswegen sich nicht generalisieren lässt, ob sie gut oder schlchte zum Suchen und oder Sortieren geeignet sind. Im abiturrelvanten Rahmen der nicht linearen Datenstrukturen, in Form von Bäumen und graphen lässt sich sagen, dass sich bäume, insbesondere der Binary Search tree sehr gut zum suchen Eignen, wohingegen das suchen im Graphen nicht besonders effizient ist. 
Sortieren ist bei einem Binärbaum nur schwer zu realisieren, und bei einem BinarySearchTree redundant, da dieser bereits in einer Geordneten Form vorliegen muss, um sienen Zweck zu erfüllen. Auch Graphen eignen sich im Wesentlichen nicht dazu sortiert zu werden, da dies in den Kontexten, in dem ein Graph eine geeignete Datenstruktur ist meist nicht sinnvoll ist. 

- [BinarySearchTree](../Abiturklassen/BinarySearchTree.java)
- [](../Abiturklassen/BinarySearchTree.java)
- [](../Abiturklassen/BinarySearchTree.java)

## Graph

Ein Graph ist eine nicht lineare Datenstruktur,  nicht-hierarchische Datenstruktur. 
Ein Graph besteht grundlegend aus Knoten und Kanten. Besitzten alle Kanten des Graphen mindestens einen Wert oder auch fachsprachlich eine Gewichtung,so handelt es sich um einen gewichteten Graphen. Graphen werden meist genutzt um in der Realität bestehende Infrastrukturen, wie Verkehrs-, Strom-, oder Internnetzte darzustellen und  

### Weg 
Einen Weg in einem Graphen gibt man als Folge der dabei durchlaufenen Knoten an.Endet ein Weg an demselben Knoten, an dem er begonnen hat, so spricht man von einem Rundweg (Zyklus). Besitzt ein Graph mindestens einen Zyklus, so spricht man von einem zyklischen Graphen.

### Zusammenhängende Graphen 

Kann man von jedem Knoten aus jeden anderen Knoten über einen Weg erreichen,
so nennt man diesen Graph einen zusammenhängenden Graphen.

### Vollständigkeit 

Ein vollständiger Graph hat von jedem Knoten zu jedem anderen Knoten eine direkte Kante. Ist ein Graph fast vollständig, so bezeichnet man ihn als dichten Graph. Ist ein Graph weit davon entfernt, vollständig zu sein, so bezeichnet man ihn als dünnen Graph.



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