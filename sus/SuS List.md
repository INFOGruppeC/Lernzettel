# [SuS](## "Suchen und Sortieren ") List
Diese Liste ist sus :rat:

## Inhalt
 - Sortieren
   - [Insertion Sort](#insertion-sort)
   - [Selection Sort](#selection-sort)
   - [Bubble Sort](#bubble-sort)
   - [Quicksort](#quick-sort)
 - Suchen

## Insertion Sort

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

</details>

## Selection Sort


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

</details>

## Bubble Sort


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

</details>

## Quick Sort


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

</details>