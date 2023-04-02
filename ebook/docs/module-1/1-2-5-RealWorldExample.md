### 1.2.5: Real-world example: Comparing performance of different algorithms for the same problem and analyzing time complexity of various searching and sorting algorithms

In this section, we will compare the performance of different searching and sorting algorithms by analyzing their time complexity using Big O notation. This is important to understand when to choose one algorithm over another based on the problem's constraints and the size of the input data.

#### Linear Search vs. Binary Search

Two popular searching algorithms are Linear Search and Binary Search. Linear Search has a time complexity of O(n), where n is the number of elements in the list, while Binary Search has a time complexity of O(log n) but requires a sorted list.

```java
public class SearchComparison {
    public static void main(String[] args) {
        int[] array = {10, 20, 30, 40, 50, 60, 70, 80, 90, 100};
        int target = 90;

        int linearSearchIndex = linearSearch(array, target);
        int binarySearchIndex = binarySearch(array, target);

        System.out.println("Linear Search found the target at index: " + linearSearchIndex);
        System.out.println("Binary Search found the target at index: " + binarySearchIndex);
    }

    public static int linearSearch(int[] array, int target) {
        for (int i = 0; i < array.length; i++) {
            if (array[i] == target) {
                return i;
            }
        }
        return -1;
    }

    public static int binarySearch(int[] array, int target) {
        int left = 0;
        int right = array.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (array[mid] == target) {
                return mid;
            }

            if (array[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }

        return -1;
    }
}
```

In this example, we can see that for smaller input sizes, the difference in performance may not be significant. However, as the input size grows, Binary Search will significantly outperform Linear Search, especially when the list is already sorted.

#### Bubble Sort vs. Quick Sort

Bubble Sort and Quick Sort are two popular sorting algorithms. Bubble Sort has a time complexity of O(n^2) in the worst and average cases, while Quick Sort has an average time complexity of O(n log n) and a worst-case time complexity of O(n^2). However, Quick Sort is generally faster in practice due to its smaller constant factors and better cache performance.

```java
public class SortComparison {
    public static void main(String[] args) {
        int[] array1 = {64, 34, 25, 12, 22, 11, 90};
        int[] array2 = {64, 34, 25, 12, 22, 11, 90};

        bubbleSort(array1);
        quickSort(array2, 0, array2.length - 1);

        System.out.print("Bubble Sort: ");
        for (int value : array1) {
            System.out.print(value + " ");
        }

        System.out.println();

        System.out.print("Quick Sort: ");
        for (int value : array2) {
            System.out.print(value + " ");
        }
    }

    public static void bubbleSort(int[] array) {
        int n = array.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (array[j] > array[j + 1]) {
                    int temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                }
            }
        }
    }

    public static void quickSort(int[] array, int low, int high) {
        if (low < high) {
            int partitionIndex = partition(array, low, high);

            quickSort(array, low, partitionIndex - 1);
            quickSort(array, partitionIndex + 1, high);
        }
    }

    private static int partition(int[] array, int low, int high) {
        int pivot = array[high];
        int i = (low - 1);

        for (int j = low; j <= high - 1; j++) {
            if (array[j] < pivot) {
                i++;
                int temp = array[i];
                array[i] = array[j];
                array[j] = temp;
            }
        }

        int temp = array[i + 1];
        array[i + 1] = array[high];
        array[high] = temp;

        return (i + 1);
    }
}
```

In this example, we can see that Quick Sort performs better than Bubble Sort for larger input sizes. However, it's important to note that for small input sizes or nearly sorted data, Bubble Sort may be faster due to its simplicity and lower overhead.

Understanding the time complexity of different algorithms helps developers choose the most appropriate algorithm for a specific problem, leading to more efficient software solutions.
