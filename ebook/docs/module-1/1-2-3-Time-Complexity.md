### 1.2.3: Time Complexity

Time complexity is a measure of the amount of time an algorithm takes to run as a function of the input size. It helps us understand how the performance of the algorithm scales with the increase in the size of the input data.

In this section, we'll explore a simple example of calculating the time complexity of an algorithm to find the sum of all numbers in an array.

Consider the following Java code:

```java
public int findSum(int[] arr) {
    int sum = 0;
    for (int i = 0; i < arr.length; i++) {
        sum += arr[i];
    }
    return sum;
}
```

This method accepts an integer array `arr` as its input and calculates the sum of its elements. The method uses a `for` loop to iterate through each element in the array. For each element, it adds the value to the variable `sum`. After iterating through all the elements, it returns the sum.

To calculate the time complexity, let's analyze how many times each operation is executed:

1. The initialization of `sum` (int sum = 0;) is executed only once.
2. The `for` loop iterates `n` times, where `n` is the length of the array.
3. Inside the loop, the addition operation (sum += arr[i];) is executed `n` times.

Since the loop is the dominant factor in the execution time, the time complexity is proportional to the number of times the loop is executed, which is `n`. Therefore, the time complexity of this algorithm is O(n), where n is the length of the input array.

In summary, the time complexity of the `findSum` method is O(n), as the execution time increases linearly with the size of the input array.
