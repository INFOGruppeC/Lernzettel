# Bäume

Dynamische, nichtlineare Datenstruktur, bei der jeder Knoten 0 bis 2 Nachfolger hat
(Binärbaum wegen zwei Nachfolgern).<br/><br/>

## Rekursive Definition:
Ein Baum ist entweder leer oder ein Knoten mit einem Inhalt und zwei Teilbäumen. Die Teilbäume sind wiederum Bäume. Die Wurzel eines Baums ist der Knoten ohne Vorgänger. Ein Blatt ist ein Knoten ohne Nachfolger. Ein Innenknoten ist ein Knoten mit Vorgänger und Nachfolger. 
Durch die rekursive Definition kann ein Baum beliebig tief sein und bei der Suche wird immer nur ein Teilbaum betrachtet, da die anderen Teilbäume nicht mehr in Frage kommen.

Der Inhalt eines Knotens sollte einzigartig sein.

## Laufzeit
Die Laufzeit von `Suchen`, `Einfügen` und `Entfernen` ist identisch.

| Case | Laufzeit |
|------|----------|
| Best | $O(1)$   |
| Worst | $O(n)$  |
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

### Methoden:
| Methode | Beschreibung |
|---------|--------------|
| `insert(Content pContent)` | Fügt einen neuen Knoten mit dem Inhalt pContent in den Baum ein |
| `remove(Content pContent)` | Entfernt den Knoten mit dem Inhalt pContent aus dem Baum |
| `search(Content pContent)` | Sucht den Knoten mit dem Inhalt pContent im Baum (nur beim Suchbaum) |
| `getLeftTree()` | Gibt den linken Teilbaum zurück |
| `getRightTree()` | Gibt den rechten Teilbaum zurück |


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