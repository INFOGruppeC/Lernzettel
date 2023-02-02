# [SuS](## "Suchen und Sortieren ") Array


## Inhalt
- [SuS Array](#sus-array)
  - [Inhalt](#inhalt)
  - [Sortieren](#sortieren)
    - [Insertion Sort](#insertion-sort)
  - [sub-section](#sub-section)
    - [Selection Sort](#selection-sort)
    - [Bubble Sort](#bubble-sort)
    - [Quick Sort](#quick-sort)
  - [Suchen](#suchen)
    - [Lineare Suche](#lineare-suche)
    - [Binäre Suche](#binäre-suche)
  

## Sortieren

### Insertion Sort
```java
public static void insertionSort(int[] array) {
    for (int i = 1; i < array.length; i++) {
        int j = i;
        while (j > 0 && array[j] < array[j - 1]) {
            int temp = array[j];
            array[j] = array[j - 1];
            array[j - 1] = temp;
            j--;
        }
    }
}
```
[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/blob/main/Lineare-Datenstrukturen/sus/#insertion-sort)


### Selection Sort
```java
public static void selectionSort(int[] array) {
    for (int i = 0; i < array.length; i++) {
        int min = i;
        for (int j = i + 1; j < array.length; j++) {
            if (array[j] < array[min]) {
                min = j;
            }
        }
        int temp = array[i];
        array[i] = array[min];
        array[min] = temp;
    }
}
```
[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/Lineare-Datenstrukturen/blob/main/sus/README.md#selection-sort)

### Bubble Sort

```java
public static void bubbleSort(int[] array) {
    for (int i = 0; i < array.length; i++) {
        for (int j = 0; j < array.length - 1; j++) {
            if (array[j] > array[j + 1]) {
                int temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
            }
        }
    }
}
```
[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/Lineare-Datenstrukturen/blob/main/sus/README.md#bubble-sort)

### Quick Sort
```java
public static void quickSort(int[] array) {
    quickSort(array, 0, array.length - 1);
}

private static void quickSort(int[] array, int left, int right) {
    if (left < right) {
        int pivot = partition(array, left, right);
        quickSort(array, left, pivot - 1);
        quickSort(array, pivot + 1, right);
    }
}

private static int partition(int[] array, int left, int right) {
    int pivot = array[right];
    int i = left - 1;
    for (int j = left; j < right; j++) {
        if (array[j] <= pivot) {
            i++;
            int temp = array[i];
            array[i] = array[j];
            array[j] = temp;
        }
    }
    int temp = array[i + 1];
    array[i + 1] = array[right];
    array[right] = temp;
    return i + 1;
}
```
[Funktionsweise](https://github.com/INFOGruppeC/Lernzettel/blob/main/sus/README.md#quick-sort)

## Suchen

### Lineare Suche
```java
public static int linearSearch(int[] array, int value) {
    for (int i = 0; i < array.length; i++) {
        if (array[i] == value) {
            return i;
        }
    }
    return -1;
}
```

### Binäre Suche
```java
public static int binarySearch(int[] array, int value) {
    int left = 0;
    int right = array.length - 1;
    while (left <= right) {
        int middle = (left + right) / 2;
        if (array[middle] == value) {
            return middle;
        } else if (array[middle] < value) {
            left = middle + 1;
        } else {
            right = middle - 1;
        }
    }
    return -1;
}
```
