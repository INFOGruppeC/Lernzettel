# [SuS](## "Suchen und Sortieren ") Array


## Inhalt
 - [Insertion Sort](#insertion-sort)
 - [Selection Sort](#selection-sort)
 - [Bubble Sort](#bubble-sort)
 - [Quicksort](#quick-sort)

## Insertion Sort
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
## Selection Sort
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
## Bubble Sort

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
## Quick Sort
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