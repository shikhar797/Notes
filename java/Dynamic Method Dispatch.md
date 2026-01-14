
# Dynamic Method Dispatch in Java

## Introduction

Dynamic Method Dispatch, also known as **Runtime Polymorphism**, is one of the most powerful concepts in Java's object-oriented programming. It allows Java to determine which method to invoke at runtime rather than compile time. This feature is fundamental in achieving **method overriding** and is widely used in real-world applications.

## Understanding Dynamic Method Dispatch

In Java, method calls are resolved dynamically at runtime using **Dynamic Method Dispatch**. This mechanism enables **a superclass reference variable to refer to a subclass object**, and Java determines which overridden method to execute based on the actual object type.

### Key Points:

- It enables **runtime polymorphism**.
- Method invocation is determined by the object that the reference variable refers to (not the type of reference itself).
- It allows for **flexible and maintainable** code by supporting method overriding.


example 

## Real-World Use Case

Imagine you are developing a **payment system** where different payment methods (Credit Card, PayPal, UPI) should have their own processing logic. Using **Dynamic Method Dispatch**, you can achieve this as follows:

`// Parent class`
`class Payment {`
    `void processPayment() {`
        `System.out.println("Processing generic payment");`
    `}`
`}`

`// Child class 1`
`class CreditCardPayment extends Payment {`
    `@Override`
    `void processPayment() {`
        `System.out.println("Processing credit card payment");`
    `}`
`}`

`// Child class 2`
`class PayPalPayment extends Payment {`
    `@Override`
    `void processPayment() {`
        `System.out.println("Processing PayPal payment");`
    `}`
`}`

`public class PaymentSystem {`
    `public static void main(String[] args) {`
        `Payment payment;`

        `// Process Credit Card Payment`
        `payment = new CreditCardPayment();`
        `payment.processPayment(); // Output: Processing credit card payment`

        `// Process PayPal Payment`
        `payment = new PayPalPayment();`
        `payment.processPayment(); // Output: Processing PayPal payment`
    `}`
`}`

