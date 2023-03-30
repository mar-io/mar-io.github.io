# Lesson 1.3: Big O Notation

## Description
Big O notation is a mathematical notation used to describe the performance of an algorithm. It provides an upper bound on the growth rate of an algorithm's time or space complexity, allowing us to estimate its efficiency as the input size increases. Big O notation is expressed using the letter 'O' followed by a function that represents the growth rate, such as O(1), O(n), O(n^2), or O(log n).

## Generic Code Example

Here's an example of a simple algorithm in Java that demonstrates different Big O complexities.

\```java
public class BigONotation {

    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        // O(1)
        System.out.println("First element: " + numbers[0]);

        // O(n)
        for (int number : numbers) {
            System.out.println("Number: " + number);
        }

        // O(n^2)
        for (int i = 0; i < numbers.length; i++) {
            for (int j = 0; j < numbers.length; j++) {
                System.out.println("Pair: (" + numbers[i] + ", " + numbers[j] + ")");
            }
        }
    }
}
\```

**Explanation**: In this example, we have three code snippets demonstrating different Big O complexities. The first one retrieves the first element of the array, which takes constant time, O(1). The second one iterates through the array and prints each element, which takes linear time, O(n). The third one prints all possible pairs of elements in the array, which takes quadratic time, O(n^2).

## Real World Code Example

The following code demonstrates a binary search algorithm, which has a time complexity of O(log n):

\```java
public class BinarySearch {

    public static void main(String[] args) {
        int[] sortedArray = {1, 2, 3, 4, 5, 6, 7, 8, 9};
        int target = 6;
        int index = binarySearch(sortedArray, target);

        if (index != -1) {
            System.out.println("Element found at index: " + index);
        } else {
            System.out.println("Element not found");
        }
    }

    public static int binarySearch(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;

        while (left <= right) {
            int mid = (left + right) / 2;

            if (arr[mid] == target) {
                return mid;
            } else if (arr[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }

        return -1;
    }
}
\```

**Explanation**: In this real-world example, we use a binary search algorithm to find the index of a target element in a sorted array. The binary search algorithm repeatedly divides the search interval in half, effectively reducing the search space by a factor of two with each step. This results in a time complexity of O(log n). The space complexity is O(1) because we only use a few constant-size variables.
