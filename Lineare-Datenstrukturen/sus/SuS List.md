# [SuS](## "Suchen und Sortieren ") List

Diese Liste ist sus :rat:

## Inhalt

- [SuS List](#sus-list)
  - [Inhalt](#inhalt)
  - [Sortieren](#sortieren)
    - [Insertion Sort](#insertion-sort)
    - [Selection Sort](#selection-sort)
    - [Bubble Sort](#bubble-sort)
    - [Quick Sort](#quick-sort)
  - [Suchen](#suchen)
    - [Lineare Suche](#lineare-suche)
    - [Binäre Suche](#binäre-suche)

## Sortieren

### Insertion Sort

<details>
  <summary>Beispielimplementation anzeigen</summary>


```java
private List<Integer> insertionSort(List<Integer> list) {
    List<Integer> helperList = new List<>();
    while (!list.isEmpty())
    {
        list.toFirst();
        helperList.toFirst();

        if (helperList.isEmpty()) {
            helperList.insert(list.getContent());
            list.remove();
            continue;
        }
        boolean hasInserted = false;
        while (helperList.hasAccess()) {
            if (helperList.getContent() < list.getContent()) {
                helperList.insert(list.getContent());
                hasInserted = true;
                break;
            }
            helperList.next();
        }

        if (!hasInserted) {
            helperList.append(list.getContent());
        }

        list.remove();
    }
    return helperList;
}
```

[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/Lineare-Datenstrukturen/blob/main/sus#insertion-sort)

</details>

### Selection Sort

<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
public int findBest(List<Integer> list) {
    list.toFirst();
    int best = list.getContent();
    while (list.hasAccess()) {
        if (list.getContent() > best) {
            best = list.getContent();
        }
        list.next();
    }
    return best;
}

private List<Integer> selectionSort(List<Integer> list) {
    List<Integer> helperList = new List<>();
    while (!list.isEmpty())
    {
        // Beste Karte heraussuchen
        int best = findBest(list);
        list.toFirst();
        while (list.getContent() != best)
        {
            list.next();
        }

        helperList.append(best);
        list.remove();
    }
    return helperList;
}
```

[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/Lineare-Datenstrukturen/blob/main/sus#selection-sort)

</details>

### Bubble Sort

<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
private List<Integer> bubblesort(List<Integer> list) {
    boolean swapped;
    int first, second;
    do
    {
        swapped = false;
        list.toFirst();
        first = list.getContent();
        list.remove();
        while (list.hasAccess())
        {
            second = list.getContent();
            if (first >= second)
            {
                list.insert(first);
                first = second;
                list.remove();
            }
            else
            {
                swapped = true;
                list.next();
            }
        }
        list.append(first);
    }
    while (swapped);
    return list;
}
```

[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/Lineare-Datenstrukturen/blob/main/sus#bubble-sort)

</details>

### Quick Sort

<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
public List<Integer> quicksort(List<Integer> list) {
    if (list.isEmpty()) {
        return list;
    }
    List<Integer> left = new List<>();
    List<Integer> right = new List<>();
    List<Integer> equal = new List<>();
    list.toFirst();
    int pivot = list.getContent();
    while (list.hasAccess()) {
        if (list.getContent() < pivot) {
            left.append(list.getContent());
        } else if (list.getContent() > pivot) {
            right.append(list.getContent());
        } else {
            equal.append(list.getContent());
        }
        list.next();
    }
    left = quicksort(left);
    right = quicksort(right);
    left.concat(equal);
    left.concat(right);
    return left;
}
```

[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/blob/main/sus#quick-sort)

</details>

## Suchen

### Lineare Suche

```java
public int linearSearch(List<Integer> list, int search) {
    list.toFirst();
    int i = 0;
    while (list.hasAccess()) {
        i++;
        if (list.getContent() == search) {
            return i;
        }
        list.next();
    }
    return -1;
}
```

[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/blob/main/sus#lineare-suche)

### Binäre Suche

```java
public int binarySearch(List<Integer> list, int search) {
    int left = 0;
    int right = getSize(list) - 1;
    list.toFirst();
    while (left <= right) {
        int middle = (left + right) / 2;
        list.toFirst();
        int i = 0;
        for (i = 0; i < middle; i++) {
            list.next();
        }
        if (list.getContent() == search) {
            return i;
        } else if (list.getContent() < search) {
            left = middle + 1;
        } else {
            right = middle - 1;
        }
    }
    return -1;
}
```

```java
private int getSize(List<Integer> list) {
    int size = 0;
    list.toFirst();
    while (list.hasAccess()) {
        size++;
        list.next();
    }
    return size;
}
```

[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/blob/main/sus#binäre-suche)
