### 2.1.4: Real-world example: Loan interest calculation using two-dimensional arrays

Two-dimensional arrays have numerous practical applications in various industries, including the financial sector. In this example, we will explore how a bank might use two-dimensional arrays to manage and calculate loan interest rates for different loan types and tenures.

Banks often offer different types of loans, such as personal loans, car loans, and home loans, with varying interest rates depending on the loan tenure. These interest rates can be represented using a two-dimensional array, where rows represent different loan types, and columns represent different loan tenures. By indexing the two-dimensional array, the bank can easily access and calculate the interest rate for a specific loan type and tenure.

#### Practical Java code example

Let's create a Java example that demonstrates how to use a two-dimensional array to represent interest rates for different loan types and tenures and calculate the total interest for a given loan amount.

```java
public class BankLoanInterestExample {
    public static void main(String[] args) {
        // Declare and initialize interest rates for different loan types and tenures
        double[][] interestRates = {
            {0.03, 0.035, 0.04}, // Personal loan interest rates for 1, 3, and 5-year tenures
            {0.025, 0.03, 0.032}, // Car loan interest rates for 1, 3, and 5-year tenures
            {0.02, 0.023, 0.025}  // Home loan interest rates for 1, 3, and 5-year tenures
        };

        // Example: Calculate total interest for a 5-year car loan of $20,000
        int loanType = 1; // Car loan
        int tenureIndex = 2; // 5-year tenure
        double loanAmount = 20000;

        double interestRate = interestRates[loanType][tenureIndex];
        double totalInterest = loanAmount * interestRate;

        System.out.println("Total interest for a 5-year car loan of $20,000: $" + totalInterest);
    }
}
```

In this example, we declare and initialize a two-dimensional array called `interestRates` to represent the interest rates for different loan types and tenures. We then specify the loan type, tenure index, and loan amount for a 5-year car loan of $20,000. We calculate the total interest by accessing the interest rate from the `interestRates` array using the loan type and tenure index and multiplying it by the loan amount. Finally, we print the total interest.

When you run this code, the output will be:

```
Total interest for a 5-year car loan of $20,000: $640.0
```

This example demonstrates how a bank can use two-dimensional arrays to manage and calculate interest rates for different loan types and tenures. In practice, banks would work with more complex data structures and algorithms to account for factors like credit scores and market trends.
