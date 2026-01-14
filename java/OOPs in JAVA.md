
![[Types-of-OOPS-2.gif]]


### 1. Class

A [Class](https://www.geeksforgeeks.org/java/classes-objects-java/) is a user-defined blueprint or prototype from which objects are created. It represents the set of properties or methods that are common to all objects of one type. Using classes, you can create multiple objects with the same behavior instead of writing their code multiple times. In general, class declarations can include these components in order: 

- ****Modifiers****: A class can be public or have default access (Refer to [this](https://www.geeksforgeeks.org/java/access-modifiers-for-classes-or-interfaces-in-java/) for details).
- ****Class name:**** The class name should begin with the initial letter capitalized by convention.
- ****Body:**** The class body is surrounded by braces, { }.

### 2. Object

An [Object](https://www.geeksforgeeks.org/java/object-class-in-java/) is a basic unit of Object-Oriented Programming that represents real-life entities. A typical Java program creates many objects, which as you know, interact by invoking methods. The objects are what perform your code, they are the part of your code visible to the viewer/user. An object mainly consists of: 

- ****State****: It is represented by the attributes of an object. It also reflects the properties of an object.

- ****Behavior****: It is represented by the methods of an object. It also reflects the response of an object to other objects.

- ****Identity****: It is a unique name given to an object that enables it to interact with other objects.

- [****Method****](https://www.geeksforgeeks.org/java/methods-in-java/)****:**** A method is a collection of statements that perform some specific task and return the result to the caller.

## Simple Java Program Showing an Object

```
// Define a class named Car
class Car {
    String brand;
    String model;
}

public class Main {
    public static void main(String[] args) {
        // Create an object (instance) of the Car class
        Car myCar = new Car();

        // Assign values to the object's fields
        myCar.brand = "Toyota";
        myCar.model = "Camry";
    }
}
```

so here Car is the class and myCar is an object


### ***3. Abstraction***


****Abstraction in Java**** is the process of hiding the implementation details and only showing the essential details or features to the user. It allows to focus on what an object does rather than how it does it. The unnecessary details are not displayed to the user.

****Note:**** In Java, abstraction is achieved by [interfaces](https://www.geeksforgeeks.org/java/interfaces-in-java/) and [abstract classes](https://www.geeksforgeeks.org/java/abstract-classes-in-java/). We can achieve 100% abstraction using interfaces.


### ***4.****Encapsulation

Encapsulation is defined as the process of wrapping data and the methods into a single unit, typically a class. It is the mechanism that binds together the code and the data. It manipulates. Another way to think about encapsulation is that it is a protective shield that prevents the data from being accessed by the code outside this shield. 

- Technically, in encapsulation, the variables or the data in a class is hidden from any other class and can be accessed only through any member function of the class in which they are declared.

- In encapsulation, the data in a class is hidden from other classes, which is similar to what ****data-hiding**** does. So, the terms "encapsulation" and "data-hiding" are used interchangeably.

- Encapsulation can be achieved by declaring all the variables in a class as private and writing public methods in the class to set and get the values of the variables.


### **5.*** Inheritance 


Inheritance is an important pillar of OOP (Object Oriented Programming). It is the mechanism in Java by which one class is allowed to inherit the features (fields and methods) of another class. We are achieving inheritance by using **extends** keyword. Inheritance is also known as "***is-a**" relationship.

'is-a' relationship" means a child (sub) class is a specialized type of its parent (super) class.

ex->car is a vehicle or dog is a animal

### **6.*** **Polymorphism***


The word [****polymorphism****](https://www.geeksforgeeks.org/java/polymorphism-in-java/) means having ****many forms****, and it comes from the Greek words ****poly (many)**** and ****morph (forms)****, this means one entity can take many forms. In Java, polymorphism allows the same method or object to behave differently based on the context, specially on the project's actual runtime class.

![[polymorphism_in_java.webp]]



Polymorphism in Java

### Types of Polymorphism

Polymorphism in Java is mainly of 2 types as mentioned below: 

1. [Method Overloading](https://www.geeksforgeeks.org/java/method-overloading-in-java/)
2. [Method Overriding](https://www.geeksforgeeks.org/java/overriding-in-java/) 

### ****Method Overloading and Method Overriding****

****1. Method Overloading:**** Also, known as ****compile-time polymorphism****, is the concept of Polymorphism where more than one method share the same name with different signature(Parameters) in a class. The return type of these methods can or cannot be same.

****2. Method Overriding:**** Also, known as run-time polymorphism, is the concept of Polymorphism where method in the child class has the same name, return-type and parameters as in parent class. The child class provides the implementation in the method already written.



Generalization and Specialization in inheritance

You use **specialization** to break down a broad concept (top-down) and **generalization** to build up commonality from specifics (bottom-up), both relying on **inheritance** to share features and build a cohesive, reusable class structure.
