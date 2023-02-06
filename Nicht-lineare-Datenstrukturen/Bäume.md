# Bäume

Dynamische, nichtlineare Datenstruktur, bei der jeder Knoten 0/1/2 Nachfolger hat
(Binärbaum wegen zwei Nachfolgern)<br/>
Baum ist eine Menge von Knoten. Ohne Vorgänger ist dieser ein Knoten, ohne Nachfolger<br/>
ein Blatt und wenn beides existiert handelt es sich um einen inneren Knoten<br/>
Algorithmen zur Verarbeitung der Binärbäume sind oft rekursiv, daher gilt folgende, rekursive Definition: <br/>
Ein Binärbaum ist entweder leer oder er besteht aus einer Wurzel mit einem linken und
einem rechten Binärbaum.<br/>
Ist ein Baum leer gilt das als Abbruchbedingung für die rekursive Definition<br/>
Die Wurzel (und folgende, innere Knoten) haben also einen linken und rechten Teilbaum
(wobei diese auch leer sein können)<br/>
Gegenüber einer zB Liste muss die gesamte Datenstruktur nicht durchiteriert werden da
durch Ausschluss bei jeder Entscheidung große Teile unwichtiger Daten aussortiert
werden können <br/>
Laufzeit: log(n)



## Implementation:
BinaryTree<String> baum = new BinaryTree<String>(Content pContent, BinaryTree
pLeftTree, BinaryTree pRightTree);
Entweder sind die Funktionsklammern leer, ein Inhalt ist vorhanden oder Inhalt + zwei
Bäume
## Traversierung:
Prozess des Übertragens eines Baums in eine Liste

preorder (Knoten-Links-Rechts)
inorder (Links-Knoten-Rechts)
postorder (Links-Rechts-Knoten)
Funktion: nach der Prüfung ob übergebener Knoten leer ist wird entweder der Knoten
einem String hinzugefügt oder die Funktion erneut mit dem linken/rechten Teilbaum
aufgerufen (je nach Traversierungsverfahren)
Kenngrößen:
Grad eines Knotens: Anzahl der Nachfolger des Knotens (0/1/2)
Inhalt: Wert/Objekt des Knotens
Teilbaum: Unterbaum eines Baums (rekursiv)
Tiefe: Anzahl der gerichteten Kanten bis zur Wurzel (Striche bzw. Anzahl Knoten - 1)
Höhe: Tiefe des tiefsten Knotens im Baum