### 2.1.4: Real-world example: Image processing using multidimensional arrays

Multidimensional arrays, particularly two-dimensional arrays, have many practical applications. One of the most common uses is in image processing. Images are usually represented as grids of pixels, and each pixel has a color value. In this scenario, a two-dimensional array can be used to store and manipulate the pixel data.

#### Easy-to-understand description

Think of an image as a grid of pixels, where each pixel has a specific color. In image processing, we often need to manipulate these pixels in various ways, such as modifying the colors, resizing the image, or applying filters. A two-dimensional array is a natural choice for representing the image as a grid, where each element of the array corresponds to a pixel in the image. The row and column indices of the array represent the pixel's position in the image.

#### Practical Java code example

Let's create a simple Java example that demonstrates how to create a two-dimensional array representing a grayscale image and invert the pixel values. In this example, we will represent the grayscale values as integers ranging from 0 (black) to 255 (white).

```java
public class ImageProcessingExample {
    public static void main(String[] args) {
        // Declare and initialize a 3x3 grayscale image
        int[][] image = {
            {0, 128, 255},
            {64, 192, 32},
            {240, 16, 128}
        };

        // Invert the pixel values in the image
        for (int row = 0; row < image.length; row++) {
            for (int col = 0; col < image[row].length; col++) {
                image[row][col] = 255 - image[row][col];
            }
        }

        // Print the inverted image
        for (int row = 0; row < image.length; row++) {
            for (int col = 0; col < image[row].length; col++) {
                System.out.print(image[row][col] + " ");
            }
            System.out.println(); // Print a newline after each row
        }
    }
}
```

In this example, we declare and initialize a 3x3 grayscale image using a two-dimensional array called `image`. Each element of the array represents the grayscale value of a pixel. We then iterate through the `image` array using nested loops and invert the pixel values by subtracting them from 255. Finally, we print the inverted image.

When you run this code, the output will be:

```
255 127 0
191 63 223
15 239 127
```

This is a simple example of using multidimensional arrays for image processing in Java. In more advanced image processing applications, you would typically work with larger arrays and more complex operations.
