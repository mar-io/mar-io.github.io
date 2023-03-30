# Lesson 2.1: Arrays

## Description
An array is a collection of elements, each identified by an index or a key. The elements in an array are stored in contiguous memory locations, and each element can be accessed directly using its index. Arrays can have one or more dimensions, with the most common being one-dimensional (also called a list or vector) and two-dimensional (also called a matrix or table).

## Generic Code Example

Here's an example of a simple one-dimensional array in Java:

```java
public class ArrayExample {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        // Accessing array elements using an index
        System.out.println("First element: " + numbers[0]);
        System.out.println("Third element: " + numbers[2]);

        // Modifying an element in the array
        numbers[0] = 10;
        System.out.println("Modified first element: " + numbers[0]);
    }
}
```

**Explanation**: In this example, we create a one-dimensional array of integers and initialize it with values. We access elements in the array using their index and modify the value of an element by assigning a new value using its index.

## Real World Code Example

Here's an example of a real-world use of a two-dimensional array in Java, representing a tic-tac-toe board:

```java
public class TicTacToe {
    public static void main(String[] args) {
        char[][] board = {
            {'X', 'O', 'X'},
            {'O', 'X', 'O'},
            {'X', 'O', 'X'}
        };

        printBoard(board);
    }

    public static void printBoard(char[][] board) {
        for (int i = 0; i < board.length; i++) {
            for (int j = 0; j < board[i].length; j++) {
                System.out.print(board[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

**Explanation**: In this real-world example, we create a two-dimensional array to represent a tic-tac-toe board. The `printBoard` method iterates through the rows and columns of the board and prints the contents of each cell. The two-dimensional array effectively models a grid-like structure, which is common in various real-world applications such as games, image processing, and simulations.
