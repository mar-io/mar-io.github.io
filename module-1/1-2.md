# Lesson 1.2: Time and Space Complexity Analysis

## Description
Time and space complexity analysis is a crucial part of understanding how efficient an algorithm is. Time complexity represents the amount of time an algorithm takes to complete as the input size increases, while space complexity represents the amount of memory consumed by the algorithm as the input size increases. Analyzing these complexities helps developers select the most suitable data structures and algorithms for a particular problem, ensuring optimal performance and resource usage.

## Generic Code Example

Here's an example of a simple algorithm in Java that calculates the sum of all elements in an array. We will analyze its time and space complexity.

```java
public class ArraySum {

    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        System.out.println("Sum: " + calculateSum(numbers));
    }

    public static int calculateSum(int[] arr) {
        int sum = 0;
        for (int value : arr) {
            sum += value;
        }
        return sum;
    }
}
```

**Explanation**: In this example, the `calculateSum` method iterates through each element of the input array once, so its time complexity is O(n), where n is the number of elements in the array. The space complexity is O(1) because the method uses a constant amount of additional memory (an integer variable `sum`) regardless of the input size.

## Real World Code Example

Consider a scenario where we need to find the common elements between two integer arrays. The following code demonstrates this concept:

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashSet;

public class CommonElements {

    public static void main(String[] args) {
        int[] array1 = {1, 2, 3, 4, 5};
        int[] array2 = {4, 5, 6, 7, 8};
        System.out.println("Common elements: " + findCommonElements(array1, array2));
    }

    public static ArrayList<Integer> findCommonElements(int[] arr1, int[] arr2) {
        HashSet<Integer> set1 = new HashSet<>(Arrays.asList(Arrays.stream(arr1).boxed().toArray(Integer[]::new)));
        ArrayList<Integer> commonElements = new ArrayList<>();

        for (int value : arr2) {
            if (set1.contains(value)) {
                commonElements.add(value);
            }
        }

        return commonElements;
    }
}
```

**Explanation**: In this real-world example, we use a HashSet to store the elements of the first array, taking advantage of its fast O(1) lookup time. We then iterate through the second array, checking if each element exists in the HashSet. If it does, we add it to the ArrayList of common elements. The time complexity of this algorithm is O(n + m), where n and m are the sizes of the input arrays. The space complexity is O(n) because we use a HashSet to store the elements of the first array.
