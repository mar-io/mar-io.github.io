## Module 1: Introduction to Data Structures and Algorithms

### Lesson 1.1: Importance of Data Structures and Algorithms

Data structures and algorithms are fundamental to computer science. They provide the building blocks for all software systems, and they are essential for solving complex problems.

A data structure is a way of organizing data so that it can be easily accessed and manipulated. Some common data structures include arrays, linked lists, stacks, and queues.

An algorithm is a step-by-step procedure for solving a problem. Some common algorithms include sorting, searching, and graph traversal.

Data structures and algorithms are important because they can make a big difference in the performance of a software system. A well-designed data structure can make a problem much easier to solve, and a well-chosen algorithm can make a program run much faster.

### Generic Code Example

The following code shows how to implement a simple stack data structure in Java:

```java
class Stack {

  private int[] data;
  private int top;

  public Stack() {
    data = new int[10];
    top = -1;
  }

  public void push(int item) {
    top++;
    data[top] = item;
  }

  public int pop() {
    int item = data[top];
    top--;
    return item;
  }

  public boolean isEmpty() {
    return top == -1;
  }
}
```

This code shows how to implement a simple stack data structure using an array. The `data` array stores the items in the stack, and the `top` variable keeps track of the current position of the top item on the stack.

To push an item onto the stack, the `push()` method first increments the `top` variable and then stores the item in the `data` array at the specified index. To pop an item off the stack, the `pop()` method first decrements the `top` variable and then returns the item at the specified index.

### Real World Code Example

The following code shows how to use a stack to implement a simple calculator:

```java
class Calculator {

  private Stack<String> operators;
  private Stack<Integer> operands;

  public void push(String operator) {
    operators.push(operator);
  }

  public void push(int operand) {
    operands.push(operand);
  }

  public int pop() {
    int result = operands.pop();
    if (!operators.isEmpty()) {
      String operator = operators.pop();
      switch (operator) {
        case "+":
          result += operands.pop();
          break;
        case "-":
          result -= operands.pop();
          break;
        case "*":
          result *= operands.pop();
          break;
        case "/":
          result /= operands.pop();
          break;
      }
    }
    return result;
  }

  public int calculate() {
    int result = 0;
    while (!operators.isEmpty()) {
      result = pop();
    }
    return result;
  }
}
```

This code shows how to use a stack to implement a simple calculator. The `operators` stack stores the operators, and the `operands` stack stores the operands.

To push an operator onto the stack, the `push()` method first stores the operator in the `operators` stack. To push an operand onto the stack, the `push()` method first stores the operand in the `operands` stack.

To pop an item off the stack, the `pop()` method first pops the top item off the `operators` stack and then pops the top item off the `operands` stack. The `calculate()` method pops all of the items off of the `operators` stack and then performs the specified operation on the operands.

The following code shows how to use the calculator:

```
Calculator calculator = new Calculator();
calculator.push("+");
calculator.push(5);
calculator.push(6);
System.out.println(calculator.calculate()); // prints 11
```

This code pushes the `+` operator, the number 5, and the number 6 onto the calculator's stack. The `calculate()` method then pops the `+` operator off of the stack and performs the addition operation on the operands. The result is printed to the console.
