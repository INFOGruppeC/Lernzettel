# Bäume

Dynamische, nichtlineare Datenstruktur, bei der jeder Knoten 0 bis 2 Nachfolger hat
(Binärbaum wegen zwei Nachfolgern).<br><br>

## Rekursive Definition:
Ein Baum ist entweder leer oder ein Knoten mit einem Inhalt und zwei Teilbäumen. Die Teilbäume sind wiederum Bäume. Die Wurzel eines Baums ist der Knoten ohne Vorgänger. Ein Blatt ist ein Knoten ohne Nachfolger. Ein Innenknoten ist ein Knoten mit Vorgänger und Nachfolger. 
Durch die rekursive Definition kann ein Baum beliebig tief sein und bei der Suche wird immer nur ein Teilbaum betrachtet, da die anderen Teilbäume nicht mehr in Frage kommen.

Der Inhalt eines Knotens sollte einzigartig sein.

## Unterschied Suchbaum und Binärbaum:
Ein Suchbaum ist sortiert, dies geschieht durch eine insert Methode die bei der Wurzel aufgerufen wird. Diese Methode sortiert den Inhalt automatisch an die Korrekte Stelle im Baum. Beim Binärbaum muss per setContent bzw. setLeftTree und setRightTree von Hand der Inhalt eingefügt werden.
Ebenfalls übernimmt der BinarySearchTree das löschen, da er die richtige Stelle im Baum suchen kann und den nachfolgenden Teilbaum an die richtige Stelle verschiebt. Beim Binärbaum muss erneut per setContent bzw. setLeftTree und setRightTree von Hand der Inhalt auf null gesetzt werden und der Teilbaum muss manuell an die richtige Stelle verschoben werden.

## Laufzeit
Die Laufzeit von `Suchen`, `Einfügen` und `Entfernen` ist identisch.

| Case | Laufzeit |
|------|----------|
| Best | $O(1)$   |
| Worst | $O(log(n))$  |
| Average | $O(log(n))$|

## Bezeichnungen

| Knoten | Vorgänger | Nachfolger |
|--------|-----------|------------|
| Wurzel | Keine     | Ja         |
| Blatt  | Ja        | Keine      |
| Innenknoten | Ja   | Ja         |

## Eigenschaften:

| Bezeichnung | Definition |
|-------------|------------|
| Tiefe | Anzahl der gerichteten Kanten bis zur Wurzel (Striche bzw. Anzahl Knoten - 1) |
| Höhe | Tiefe des tiefsten Knotens im Baum |
| Grad | Anzahl der Nachfolger des Knotens (0 bis 2) |
| Vollständiger Baum | Alle Blätter sind auf der gleichen Tiefe |
| Gleichgewichteter Baum | Die Höhen der Teilbäume unterscheiden sich nicht mehr als um 1 |
| Suchbaum | Ein Baum, in dem die Knoten nach einem bestimmten Kriterium sortiert sind (z.B. nach dem Inhalt) und durchsucht werden kann. |


## Implementation BinaryTree:

### Erstellung:
```java
BinaryTree<String> baum = new BinaryTree<String>(Content pContent, BinaryTree
pLeftTree, BinaryTree pRightTree);
```
Enthält den Inhalt des Baums und die Teilbäume

```java
BinaryTree<String> baum = new BinaryTree<String>(Content pContent);
```
Enthält nur den Inhalt des Baums und keine Teilbäume

```java
BinaryTree<String> baum = new BinaryTree<String>();
```
Enthält keinen Inhalt und keine Teilbäume

### Methoden BinarySearchTree:
| Methode | Beschreibung |
|---------|--------------|
| `insert(Content pContent)` | Fügt einen neuen Knoten mit dem Inhalt pContent in den Baum ein |
| `remove(Content pContent)` | Entfernt den Knoten mit dem Inhalt pContent aus dem Baum |
| `search(Content pContent)` | Sucht den Knoten mit dem Inhalt pContent im Baum|
| `getLeftTree()` | Gibt den linken Teilbaum zurück |
| `getRightTree()` | Gibt den rechten Teilbaum zurück |
| `getContent()` | Gibt den Inhalt des Knotens zurück |
| `isEmpty()` | Gibt zurück, ob der Baum leer ist |

### Methoden BinaryTree:
| Methode | Beschreibung |
|---------|--------------|
| `setLeftTree(BinaryTree pLeftTree)` | Setzt den linken Teilbaum auf pLeftTree |
| `setRightTree(BinaryTree pRightTree)` | Setzt den rechten Teilbaum auf pRightTree |
| `setContent(Content pContent)` | Setzt den Inhalt des Knotens auf pContent |
| `isEmpty()` | Gibt zurück, ob der Baum leer ist |
| `getLeftTree()` | Gibt den linken Teilbaum zurück |
| `getRightTree()` | Gibt den rechten Teilbaum zurück |
| `getContent()` | Gibt den Inhalt des Knotens zurück |


## Traversierung:
Die Traversierung ist die Reihenfolge, in der die Knoten des Baums besucht werden. Es gibt verschiedene Traversierungsarten, die sich in der Reihenfolge unterscheiden, in der die Knoten besucht werden.

### Verwendung:
Die Traversierung wird verwendet, um den Inhalt des Baums zu durchlaufen. Die Reihenfolge der Knoten ist dabei wichtig, da sie die Reihenfolge der Knoten im Baum widerspiegelt. Dies wird unter anderem für das Speichern und Laden von Bäumen in/aus linearer Form benötigt.

### Reihenfolgen:
| Traversierung | Reihenfolge |
|---------------|-------------|
| Preorder | Wurzel, linker Teilbaum, rechter Teilbaum |
| Inorder | Linker Teilbaum, Wurzel, rechter Teilbaum |
| Postorder | Linker Teilbaum, rechter Teilbaum, Wurzel |

### Implementation:

#### Preorder:
```java
public void preorder(BinaryTree pTree) {
    if (pTree != null) {
        System.out.println(pTree.getContent());
        preorder(pTree.getLeftTree());
        preorder(pTree.getRightTree());
    }
}
```

#### Inorder:
```java
public void inorder(BinaryTree pTree) {
    if (pTree != null) {
        inorder(pTree.getLeftTree());
        System.out.println(pTree.getContent());
        inorder(pTree.getRightTree());
    }
}
```

#### Postorder:
```java
public void postorder(BinaryTree pTree) {
    if (pTree != null) {
        postorder(pTree.getLeftTree());
        postorder(pTree.getRightTree());
        System.out.println(pTree.getContent());
    }
}
```

## Generieren eines optimalen Binary Search Trees:
Ein optimaler Binary Search Tree ist ein Baum, in dem die Summe der Tiefe aller Knoten minimal ist. Dies ist der Fall, wenn die Knoten nach dem Inhalt sortiert sind. Die Tiefe eines Knotens ist die Anzahl der gerichteten Kanten bis zur Wurzel. Die Summe der Tiefe aller Knoten ist die Summe der Tiefe aller Blätter.

### Beispiel:
![Beispiel Baum](https://upload.wikimedia.org/wikipedia/commons/thumb/6/67/Sorted_binary_tree.svg/300px-Sorted_binary_tree.svg.png)

Die Summe der Tiefe aller Knoten ist 1 + 2 + 3 + 4 + 5 = 15. Dies ist die kleinste Summe, die erreicht werden kann.

### Implementation:
```java
public BinaryTree<String> generateOptimalBST(String[] pContent) {
    return generateOptimalBST(pContent, 0, pContent.length - 1);
}

private BinaryTree<String> generateOptimalBST(String[] pContent, int pStart, int pEnd) {
    if (pStart > pEnd) {
        return null;
    }
    int middle = (pStart + pEnd) / 2;
    BinaryTree<String> tree = new BinaryTree<String>(pContent[middle]);
    tree.setLeftTree(generateOptimalBST(pContent, pStart, middle - 1));
    tree.setRightTree(generateOptimalBST(pContent, middle + 1, pEnd));
    return tree;
}
```
Erklärung:

Die Methode `generateOptimalBST` ruft sich selbst rekursiv auf, bis der Start- und Endindex gleich sind. Dann wird ein neuer Baum mit dem Inhalt des Arrays an der Stelle `middle` erstellt. Der linke Teilbaum wird mit dem Inhalt des Arrays von `pStart` bis `middle - 1` erstellt und der rechte Teilbaum mit dem Inhalt des Arrays von `middle + 1` bis `pEnd`. Dies wird solange wiederholt, bis der Start- und Endindex gleich sind. Dann wird der Baum zurückgegeben.