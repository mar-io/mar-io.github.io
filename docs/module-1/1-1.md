# Lesson 1.1: Importance of Data Structures and Algorithms

## Description
Data structures and algorithms are essential building blocks in computer science and software development. They allow us to store, organize, and manipulate data efficiently. Data structures are ways of organizing and storing data, while algorithms are step-by-step procedures for performing a specific task or solving a particular problem. Choosing the right data structure and algorithm can have a significant impact on the performance and efficiency of a program.

## Generic Code Example

Here's an example of a simple algorithm in Java to find the maximum value in an array.

```java
public class MaxValue {

    public static void main(String[] args) {
        int[] numbers = {4, 8, 2, 15, 7};
        System.out.println("Maximum value: " + findMax(numbers));
    }

    public static int findMax(int[] arr) {
        int max = arr[0];

        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }

        return max;
    }
}
```

## Real World Code Example

Consider a social media application where users can add friends. To efficiently find and display a user's friends, we can use a HashMap data structure, which allows for fast lookups. The following code demonstrates this concept:

```java
import java.util.HashMap;

public class SocialMediaApp {

    public static void main(String[] args) {
        HashMap<String, String[]> friendsList = new HashMap<>();

        String[] user1Friends = {"user2", "user3", "user4"};
        String[] user2Friends = {"user1", "user4", "user5"};
        String[] user3Friends = {"user1", "user5"};

        friendsList.put("user1", user1Friends);
        friendsList.put("user2", user2Friends);
        friendsList.put("user3", user3Friends);

        displayFriends("user1", friendsList);
    }

    public static void displayFriends(String user, HashMap<String, String[]> friendsList) {
        String[] friends = friendsList.get(user);

        System.out.println(user + "'s friends:");
        for (String friend : friends) {
            System.out.println(friend);
        }
    }
}
```

In this example, we use a HashMap to store each user's friends list. The HashMap maps a user's identifier (a String) to an array of their friends' identifiers (String[]). We populate the HashMap with some sample data for three users and their respective friends. The `displayFriends` method retrieves the friends list of a given user from the HashMap and iterates through it, printing out each friend's identifier. This real-world example demonstrates the importance of selecting the appropriate data structure to optimize the performance of a program.
