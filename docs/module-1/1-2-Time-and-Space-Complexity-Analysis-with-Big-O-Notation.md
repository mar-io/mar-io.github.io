# Section 1.2: Time and Space Complexity Analysis with Big O Notation

In this section, we will discuss time and space complexity analysis using Big O notation. This is a fundamental concept in computer science and programming, which helps us to evaluate the performance of algorithms in terms of their resource utilization. By understanding time and space complexity, we can select the most efficient algorithms for our tasks and optimize our code accordingly. We will explore the concept of asymptotic analysis and learn about best, average, and worst-case complexities. Additionally, we will discuss time and space complexities and their real-world implications.

Below is an example of calculating the time complexity of a simple Java code snippet:

```java
public int sum(int[] arr) {
    int total = 0; // O(1)
    for (int i = 0; i < arr.length; i++) { // O(n)
        total += arr[i]; // O(1)
    }
    return total; // O(1)
}
```

In this example, the time complexity of the `sum` function is calculated as follows:

1. Initializing `total` takes constant time (O(1)).
2. The loop runs n times, where n is the length of the input array (O(n)).
3. Each addition operation inside the loop takes constant time (O(1)).
4. Returning the result takes constant time (O(1)).

Considering the loop as the dominant factor, the overall time complexity of this function is O(n).
