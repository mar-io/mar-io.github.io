## 1.2.4: Space Complexity

Space complexity refers to the amount of memory an algorithm uses to solve a problem. It is important because it can impact the performance of the algorithm, especially when working with large datasets or limited memory resources.

The space complexity of an algorithm is usually expressed using Big O notation, similar to time complexity. The most common measure of space complexity is the amount of additional memory, or _auxiliary space_, the algorithm uses, excluding the memory used by the input.

For example, if an algorithm's space complexity is O(n), it means the amount of memory used by the algorithm is directly proportional to the size of the input.

### Space Complexity Example: Merge Sort in Java

```java
public class MergeSort {
    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};
        mergeSort(arr, 0, arr.length - 1);
        
        for (int value : arr) {
            System.out.print(value + " ");
        }
    }

    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int middle = (left + right) / 2;
            
            mergeSort(arr, left, middle);
            mergeSort(arr, middle + 1, right);
            
            merge(arr, left, middle, right);
        }
    }

    public static void merge(int[] arr, int left, int middle, int right) {
        int n1 = middle - left + 1;
        int n2 = right - middle;

        int[] leftArray = new int[n1];
        int[] rightArray = new int[n2];

        System.arraycopy(arr, left, leftArray, 0, n1);
        System.arraycopy(arr, middle + 1, rightArray, 0, n2);

        int i = 0, j = 0;
        int k = left;

        while (i < n1 && j < n2) {
            if (leftArray[i] <= rightArray[j]) {
                arr[k] = leftArray[i];
                i++;
            } else {
                arr[k] = rightArray[j];
                j++;
            }
            k++;
        }

        while (i < n1) {
            arr[k] = leftArray[i];
            i++;
            k++;
        }

        while (j < n2) {
            arr[k] = rightArray[j];
            j++;
            k++;
        }
    }
}
```

In the Merge Sort example above, the algorithm uses auxiliary space to store the two temporary arrays, `leftArray` and `rightArray`. Each array's length is proportional to the input size, so the space complexity of Merge Sort is O(n), where n is the size of the input array.

Understanding space complexity is crucial to developing efficient algorithms, as it can help you make trade-offs between time and space when optimizing your code.
