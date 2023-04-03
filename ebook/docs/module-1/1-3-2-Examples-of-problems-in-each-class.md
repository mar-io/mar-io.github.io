### 1.3.2: Examples of problems in each class

In this section, we will discuss examples of problems that fall into each complexity class: P, NP, NP-Complete, and NP-Hard. We will provide brief descriptions and Java code examples for better understanding.

#### P (Polynomial) Class

P class problems are those that can be solved in polynomial time, meaning the time complexity is O(n^k), where n is the input size, and k is a constant.

Example: Finding the greatest common divisor (GCD) of two numbers using Euclidean Algorithm.

```java
public class GCDExample {
    public static void main(String[] args) {
        int num1 = 56;
        int num2 = 98;

        System.out.println("GCD of " + num1 + " and " + num2 + " is: " + gcd(num1, num2));
    }

    public static int gcd(int a, int b) {
        if (b == 0) {
            return a;
        }
        return gcd(b, a % b);
    }
}
```

The `gcd` function uses a recursive approach to find the GCD of two numbers. The time complexity of the algorithm is O(log(min(a, b))).

#### NP (Nondeterministic Polynomial) Class

NP class problems are those for which a solution can be verified in polynomial time, but finding a solution might not be possible in polynomial time.

Example: Traveling Salesman Problem (TSP) - verifying a solution

```java
import java.util.Arrays;
import java.util.List;

public class TSPExample {
    private static final int[][] distances = {
        {0, 10, 15, 20},
        {10, 0, 35, 25},
        {15, 35, 0, 30},
        {20, 25, 30, 0}
    };

    public static void main(String[] args) {
        List<Integer> tspSolution = Arrays.asList(0, 1, 3, 2, 0);
        int maxDistance = 100;

        System.out.println("Solution is valid: " + verifyTSPSolution(tspSolution, maxDistance));
    }

    private static boolean verifyTSPSolution(List<Integer> path, int maxDistance) {
        // Check if the path starts and ends at the same city
        if (path.get(0) != path.get(path.size() - 1)) {
            return false;
        }

        // Calculate the total distance of the solution
        int solutionDistance = 0;
        for (int i = 0; i < path.size() - 1; i++) {
            solutionDistance += distances[path.get(i)][path.get(i + 1)];
        }

        // Check if the total distance is within the max allowed distance
        return solutionDistance <= maxDistance;
    }
}
```

In this example, the `verifyTSPSolution` method demonstrates a problem in NP. Given a TSP solution, it verifies if the solution is valid by checking if it starts and ends at the same city and has a total distance within the max allowed distance (in this case, 100).

#### NP-Complete Class

NP-Complete problems are a subset of NP problems that are at least as hard as the hardest problems in NP. If a polynomial-time solution is found for any NP-Complete problem, all NP problems can be solved in polynomial time.

Example: Boolean satisfiability problem (SAT)

SAT is the problem of determining if a given Boolean formula can be satisfied by assigning truth values to its variables. SAT is an NP-Complete problem, and solving it
in polynomial time remains an open question.

Example: The Knapsack Problem

The Knapsack Problem is an optimization problem where, given a set of items with weights and values, we need to find the maximum total value of items that can be packed into a knapsack with a limited weight capacity.

```java
public class KnapsackExample {
    public static void main(String[] args) {
        int[] values = {60, 100, 120};
        int[] weights = {10, 20, 30};
        int weightCapacity = 50;

        System.out.println("Maximum value: " + knapsack(values, weights, weightCapacity));
    }

    public static int knapsack(int[] values, int[] weights, int weightCapacity) {
        int n = values.length;
        int[][] dp = new int[n + 1][weightCapacity + 1];

        for (int i = 1; i <= n; i++) {
            for (int w = 1; w <= weightCapacity; w++) {
                if (weights[i - 1] <= w) {
                    dp[i][w] = Math.max(dp[i - 1][w], dp[i - 1][w - weights[i - 1]] + values[i - 1]);
                } else {
                    dp[i][w] = dp[i - 1][w];
                }
            }
        }

        return dp[n][weightCapacity];
    }
}
```

This example uses a dynamic programming approach to solve the Knapsack Problem. The time complexity of this approach is O(n * weightCapacity), which is not polynomial.

#### NP-Hard Class

NP-Hard problems are problems that are at least as hard as the hardest problems in NP. They may or may not be in NP, but if any NP-Hard problem can be solved in polynomial time, all NP problems can be solved in polynomial time.

Example: The Traveling Salesman Problem (TSP) - finding a solution

Finding an optimal solution to TSP is an NP-Hard problem. There are many heuristics and approximation algorithms that can be used to find a solution, but none of them guarantees finding the optimal solution in polynomial time.

In summary, understanding the complexity classes of problems is essential in computer science and software development, as it helps to analyze the efficiency of algorithms and choose the appropriate approach based on the problem at hand. The Java code examples provided in this section should help you grasp the concepts and their practical implementation.

