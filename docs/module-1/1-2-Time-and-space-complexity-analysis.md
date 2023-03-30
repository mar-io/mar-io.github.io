**Module 1, Lesson 1.2: Time and Space Complexity Analysis**

In computer science, time complexity and space complexity are two important measures of the efficiency of an algorithm. Time complexity is the amount of time it takes an algorithm to run, as a function of the size of the input. Space complexity is the amount of memory an algorithm uses, as a function of the size of the input.

## Time Complexity

There are three main types of time complexity:

* **O(1)**: The algorithm takes a constant amount of time to run, regardless of the size of the input.
* **O(n)**: The algorithm takes time proportional to the size of the input. For example, an algorithm that sorts a list of n numbers takes time proportional to n, or O(n).
* **O(n2)**: The algorithm takes time proportional to the square of the size of the input. For example, an algorithm that searches for a number in a list of n numbers takes time proportional to n2, or O(n2).

## Space Complexity

There are two main types of space complexity:

* **O(1)**: The algorithm uses a constant amount of space, regardless of the size of the input.
* **O(n)**: The algorithm uses space proportional to the size of the input. For example, an algorithm that stores a list of n numbers in memory uses space proportional to n, or O(n).

## Generic Code Example

The following code snippet shows an example of a function that takes a list of numbers as input and returns the sum of the numbers in the list. The function is implemented in Java and uses a for loop to iterate over the list of numbers. The time complexity of the function is O(n), where n is the number of numbers in the list. The space complexity of the function is O(1), since the function only uses a constant amount of space to store the list of numbers and the sum of the numbers.

```java
public int sum(List<Integer> numbers) {
  int sum = 0;
  for (int number : numbers) {
    sum += number;
  }
  return sum;
}
```

## Real World Code Example

The following code snippet shows an example of a function that implements a bubble sort algorithm. The function is implemented in Java and uses a for loop to iterate over the list of numbers. The function compares each pair of adjacent numbers in the list and swaps them if they are in the wrong order. The time complexity of the function is O(n2), where n is the number of numbers in the list. The space complexity of the function is O(1), since the function only uses a constant amount of space to store the list of numbers.

```java
public void bubbleSort(List<Integer> numbers) {
  for (int i = 0; i < numbers.size() - 1; i++) {
    for (int j = 0; j < numbers.size() - i - 1; j++) {
      if (numbers.get(j) > numbers.get(j + 1)) {
        int temp = numbers.get(j);
        numbers.set(j, numbers.get(j + 1));
        numbers.set(j + 1, temp);
      }
    }
  }
}
```

## Explanation

The time complexity of an algorithm is the amount of time it takes the algorithm to run, as a function of the size of the input. The space complexity of an algorithm is the amount of memory the algorithm uses, as a function of the size of the input.

The time complexity of the sum function is O(n), where n is the number of numbers in the list. This is because the function iterates over the list of numbers once for each number in the list. The space complexity of the sum function is O(1), since the function only uses a constant amount of space to store the list of numbers and the sum of the numbers.

The time complexity of the bubble sort algorithm is O(n2), where n is the number of numbers in the list. This is because the algorithm compares each pair of adjacent numbers in the list, and there are n such pairs. The space complexity of the bubble sort algorithm is O(1), since the algorithm only uses a constant amount of space to store the list of numbers.
