## Module 1: Introduction to Data Structures and Algorithms

### Lesson 1.2: Time and Space Complexity Analysis

In computer science, **time complexity** is the amount of time it takes for an algorithm to run, as a function of the size of the input. **Space complexity** is the amount of memory it takes for an algorithm to run, as a function of the size of the input.

Time and space complexity are important considerations in algorithm design. An algorithm with a high time complexity may not be practical to use for large inputs, while an algorithm with a high space complexity may not be practical to use for large inputs or for devices with limited memory.

There are a number of different ways to analyze the time and space complexity of an algorithm. One common approach is to use **Big O notation**. Big O notation is a way of expressing the asymptotic behavior of an algorithm. In other words, it tells you how the running time or space usage of an algorithm grows as the input size gets larger.

For example, an algorithm that runs in constant time has a time complexity of O(1). This means that the running time of the algorithm does not depend on the size of the input. An algorithm that runs in linear time has a time complexity of O(n), where n is the size of the input. This means that the running time of the algorithm is proportional to the size of the input.

There are a number of different algorithms that have different time and space complexities. Some algorithms are designed to be fast, while others are designed to be space-efficient. The choice of algorithm depends on the specific problem being solved and the resources available.

### Generic Code Example

The following code shows a simple algorithm that takes a list of numbers as input and prints the sum of the numbers:

```java
public class SumOfNumbers {

  public static void main(String[] args) {
    int[] numbers = {1, 2, 3, 4, 5};
    int sum = 0;
    for (int number : numbers) {
      sum += number;
    }
    System.out.println(sum);
  }
}
```

The time complexity of this algorithm is O(n), where n is the number of numbers in the list. This is because the algorithm has to iterate through the list of numbers once for each number in the list.

The space complexity of this algorithm is O(1), because it only requires a constant amount of memory to store the sum of the numbers.

### Real World Code Example

The following code shows a real-world example of an algorithm that is used to sort a list of numbers:

```java
public class QuickSort {

  public static void sort(int[] numbers) {
    if (numbers.length <= 1) {
      return;
    }

    int pivot = numbers[numbers.length / 2];
    int left = 0;
    int right = numbers.length - 1;

    while (left <= right) {
      while (numbers[left] < pivot) {
        left++;
      }
      while (numbers[right] > pivot) {
        right--;
      }

      if (left <= right) {
        int temp = numbers[left];
        numbers[left] = numbers[right];
        numbers[right] = temp;

        left++;
        right--;
      }
    }

    quickSort(numbers, 0, left - 1);
    quickSort(numbers, right + 1, numbers.length - 1);
  }
}
```

The time complexity of this algorithm is O(n log n), where n is the number of numbers in the list. This is because the algorithm has to divide the list in half and then recursively sort the two halves.

The space complexity of this algorithm is O(log n), because it requires a constant amount of memory to store the pivot and the two halves of the list.
