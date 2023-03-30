# Lesson 2.2: Linked Lists

## Description
A linked list is a linear data structure in which elements are stored in nodes, and each node points to the next node in the sequence. Unlike arrays, linked lists do not have a fixed size and can be resized easily. There are three types of linked lists: singly linked lists, doubly linked lists, and circular linked lists.

## Generic Code Example

Here's an example of a simple singly linked list in Java:

```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class LinkedListExample {
    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);

        printList(head);
    }

    public static void printList(Node head) {
        Node current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
    }
}
```

**Explanation**: In this example, we create a simple singly linked list with three elements. The `Node` class represents the nodes in the list, containing a `data` field and a `next` field that points to the next node. The `printList` method iterates through the list and prints the data of each node.

## Real World Code Example

Here's an example of a real-world use of a doubly linked list in Java, implementing a simple cache (Least Recently Used - LRU Cache):

```java
class DoublyLinkedListNode {
    int key;
    int value;
    DoublyLinkedListNode prev;
    DoublyLinkedListNode next;

    DoublyLinkedListNode(int key, int value) {
        this.key = key;
        this.value = value;
        this.prev = null;
        this.next = null;
    }
}

public class LRUCache {
    private int capacity;
    private Map<Integer, DoublyLinkedListNode> cache;
    private DoublyLinkedListNode head;
    private DoublyLinkedListNode tail;

    public LRUCache(int capacity) {
        this.capacity = capacity;
        this.cache = new HashMap<>();
        this.head = new DoublyLinkedListNode(-1, -1);
        this.tail = new DoublyLinkedListNode(-1, -1);
        this.head.next = this.tail;
        this.tail.prev = this.head;
    }

    public int get(int key) {
        if (cache.containsKey(key)) {
            DoublyLinkedListNode node = cache.get(key);
            moveToHead(node);
            return node.value;
        }
        return -1;
    }

    public void put(int key, int value) {
        if (cache.containsKey(key)) {
            DoublyLinkedListNode node = cache.get(key);
            node.value = value;
            moveToHead(node);
        } else {
            if (cache.size() >= capacity) {
                cache.remove(tail.prev.key);
                removeNode(tail.prev);
            }
            DoublyLinkedListNode newNode = new DoublyLinkedListNode(key, value);
            cache.put(key, newNode);
            addNode(newNode);
        }
    }

    private void moveToHead(DoublyLinkedListNode node) {
        removeNode(node);
        addNode(node);
    }

    private void addNode(DoublyLinkedListNode node) {
        node.next = head.next;
        node.prev = head;
        head.next.prev = node;
        head.next = node;
    }

    private void removeNode(DoublyLinkedListNode node) {
        node.prev.next = node.next;
        node.next.prev = node.prev;
    }
}

public class LRUCacheExample {
    public static void main(String[] args) {
        LRUCache cache = new LRUCache(3);
        cache.put(1, 10);
        cache.put(2, 20);
        cache.put(3, 30);

        System.out.println(cache.get(1));
        System.out.println(cache.get(4));

        cache.put(4, 40);

        System.out.println(cache.get(2));
    }
}
```

**Explanation**: This example demonstrates a simple LRU (Least Recently Used) Cache using a doubly linked list in combination with a HashMap. The `LRUCache` class has a `capacity`, a `cache` map, a `head`, and a `tail`. The `DoublyLinkedListNode` class is used to create the nodes in the list, containing `key`, `value`, `prev`, and `next` fields.

The `get` method retrieves the value associated with the specified key, and if the key exists in the cache, it moves the corresponding node to the head of the list. The `put` method inserts or updates the value of the key in the cache. If the cache reaches its capacity, the least recently used item is removed before adding a new one. The `moveToHead`, `addNode`, and `removeNode` methods are helper methods for managing the doubly linked list.

In the `LRUCacheExample` class, we create an LRU cache with a capacity of 3, add three items, and test the `get` and `put` methods.
