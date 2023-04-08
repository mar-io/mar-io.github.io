### 2.1.3: Multidimensional Arrays

Multidimensional arrays are arrays of arrays, which means that each element of a multidimensional array is itself an array. In Java, the most commonly used multidimensional array is a two-dimensional (2D) array, which can be thought of as a table with rows and columns.

A two-dimensional array is like a matrix or a grid, where you have rows and columns to store data. It can be visualized as a table or a spreadsheet with a specific number of rows and columns. Each cell in the table stores a value, and you can access the value by specifying the row and column index.

#### Practical Java code example

Let's create a simple example of a 2D array in Java to store the values of a 3x3 grid (3 rows and 3 columns). We will then iterate through the array to print its values.

```java
public class MultidimensionalArrayExample {
    public static void main(String[] args) {
        // Declare and initialize a 3x3 2D array
        int[][] grid = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        // Iterate through the 2D array using nested loops
        for (int row = 0; row < grid.length; row++) {
            for (int col = 0; col < grid[row].length; col++) {
                System.out.print(grid[row][col] + " ");
            }
            System.out.println(); // Print a newline after each row
        }
    }
}
```

In this example, we first declare and initialize a 3x3 2D array called `grid`. Each element of the `grid` array is an array with three elements. We use nested loops to iterate through the 2D array. The outer loop iterates through the rows, and the inner loop iterates through the columns of each row. We access each element in the 2D array using the indices `[row][col]` and print its value.

When you run this code, the output will be:

```
1 2 3
4 5 6
7 8 9
```

This is a simple example of a 2D array in Java. You can create multidimensional arrays with more dimensions, like 3D arrays or even higher, but the concept remains the same - an array of arrays.
