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
// TODO
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
// TODO
```

</details>