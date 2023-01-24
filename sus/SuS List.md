# [SuS](## "Suchen und Sortieren ") List
Diese Liste ist sus :rat:

## Inhalt
 - [Insertion Sort](#insertion-sort)
 - [Selection Sort](#selection-sort)
 - [Bubble Sort](#bubble-sort)
 - [Quicksort](#quick-sort)

## Insertion Sort

### Default Java List
<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
public static void insertionSort(List<Integer> list) {
    for (int i = 1; i < list.size(); i++) {
        int j = i;
        while (j > 0 && list.get(j - 1) > list.get(j)) {
            Collections.swap(list, j, j - 1);
            j--;
        }
    }
}
```
</details>

### Abiturklasse List
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

### Default Java List
<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
public static void selectionSort(List<Integer> list) {
    for (int i = 0; i < list.size(); i++) {
        int min = i;
        for (int j = i + 1; j < list.size(); j++) {
            if (list.get(j) < list.get(min)) {
                min = j;
            }
        }
        Collections.swap(list, i, min);
    }
}
```

</details>

### Abiturklasse List
<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
// TODO
```

</details>

## Bubble Sort

### Default Java List
<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
public static void bubbleSort(List<Integer> list) {
    for (int i = 0; i < list.size(); i++) {
        for (int j = 0; j < list.size() - 1; j++) {
            if (list.get(j) > list.get(j + 1)) {
                Collections.swap(list, j, j + 1);
            }
        }
    }
}
```

</details>

### Abiturklasse List
<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
// TODO
```

</details>

## Quick Sort

### Default Java List
<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
public static void quickSort(List<Integer> list) {
    quickSort(list, 0, list.size() - 1);
}

private static void quickSort(List<Integer> list, int left, int right) {
    if (left < right) {
        int pivot = partition(list, left, right);
        quickSort(list, left, pivot - 1);
        quickSort(list, pivot + 1, right);
    }
}

private static int partition(List<Integer> list, int left, int right) {
    int pivot = list.get(right);
    int i = left - 1;
    for (int j = left; j < right; j++) {
        if (list.get(j) <= pivot) {
            i++;
            Collections.swap(list, i, j);
        }
    }
    Collections.swap(list, i + 1, right);
    return i + 1;
}
```

</details>

### Abiturklasse List
<details>
  <summary>Beispielimplementation anzeigen</summary>

```java
// TODO
```

</details>