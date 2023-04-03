### 2.1.2: Common Array Operations

In this section, we will discuss some common operations performed on arrays:

1. **Traversing an array**: Iterating through each element of the array, usually using a loop.
2. **Inserting an element**: Adding an element at a specified index in the array.
3. **Deleting an element**: Removing an element from the array.
4. **Updating an element**: Modifying the value of an element in the array.
5. **Searching for an element**: Finding an element in the array based on a specific condition.

Here's a code example demonstrating these common array operations in Java:

```java
public class ArrayOperations {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};

        // 1. Traversing an array using a for loop
        System.out.println("Traversing the array:");
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }

        // 2. Inserting an element at index 2
        // Note: In Java, we must create a new array of the desired size and copy elements accordingly.
        int[] newArray = new int[numbers.length + 1];
        int insertIndex = 2;
        int insertValue = 25;

        for (int i = 0; i < newArray.length; i++) {
            if (i < insertIndex) {
                newArray[i] = numbers[i];
            } else if (i == insertIndex) {
                newArray[i] = insertValue;
            } else {
                newArray[i] = numbers[i - 1];
            }
        }
        numbers = newArray;
        System.out.println("Array after insertion: " + java.util.Arrays.toString(numbers));

        // 3. Deleting an element at index 4
        newArray = new int[numbers.length - 1];
        int deleteIndex = 4;

        for (int i = 0, j = 0; i < numbers.length; i++) {
            if (i != deleteIndex) {
                newArray[j++] = numbers[i];
            }
        }
        numbers = newArray;
        System.out.println("Array after deletion: " + java.util.Arrays.toString(numbers));

        // 4. Updating an element at index 0
        numbers[0] = 5;
        System.out.println("Array after updating: " + java.util.Arrays.toString(numbers));

        // 5. Searching for an element (Linear search)
        int searchValue = 30;
        int searchIndex = -1;

        for (int i = 0; i < numbers.length; i++) {
            if (numbers[i] == searchValue) {
                searchIndex = i;
                break;
            }
        }
        if (searchIndex != -1) {
            System.out.println("Element found at index " + searchIndex);
        } else {
            System.out.println("Element not found");
        }
    }
}
```
In this example, we first traverse the array using a for loop, printing each element along with its index. Next, we insert an element at a specified index by creating a new array and copying the elements accordingly. We also demonstrate how to delete an element from the array using a similar approach. After that, we update the value of an element at a given index. Finally, we search for an element in the array using a linear search.

Keep in mind that since arrays have a fixed size in Java, we need to create a new array and copy elements to perform insertion and deletion operations. This can be a limitation in certain scenarios. Other data structures like ArrayList can be used to overcome this limitation.

Remember that these are basic array operations, and there are many other algorithms and techniques to manipulate arrays more efficiently. As you progress through this e-book, you will learn more advanced techniques to work with arrays and other data structures.
