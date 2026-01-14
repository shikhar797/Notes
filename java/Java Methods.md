In Java, a **method** is ==a block of code that performs a specific, reusable task when it is called== Method. Methods are essential for organizing code, promoting modularity, and improving readability and maintainability by breaking down complex problems into smaller, manageable chunks. 

All methods in Java must be declared within a class, which aligns with Java's object-oriented nature. 

Method Declaration Syntax

A method declaration consists of several components: 

java

```
modifier returnType methodName(parameterList) {
    // method body (statements)
}
```

- **`modifier`**: Such as `public`, `private`, `protected`, or `static`, which defines the access level and behavior of the method.

- **`returnType`**: The data type of the value the method returns after completion (e.g., `int`, `String`, `boolean`). If the method does not return a value, the keyword `void` is used.

- **`methodName`**: A unique identifier (following `camelCase` convention) used to call the method. The method name and parameter list together form the **method signature**.

- **`parameterList`**: A comma-delimited list of input parameters enclosed in parentheses `()`. Each parameter must specify a data type and a name (e.g., `int x, String name`). If there are no parameters, empty parentheses `()` are used.

Note : Function in any other language


## Note: for calling inside static method

There are two ways to call method inside static method

#### 1. one is calling another static method i.e. you can call any other static method inside a static method.

 ex-> Calling Another Static Method

You can call another static method within a static block without needing an object instance. 

java

```
public class Example {

    public static void staticMethod() {
        System.out.println("Inside static method.");
    }

    public static void main(String[] args) {
        s.o.p(staticMethod());
    }
}
```

#### 2. Calling a Non-Static (Instance) Method

To call a non-static method from within a static block, you must first create an instance of the class and then call the method using that instance . 

java

```
public class Example {

    public void instanceMethod() {
        System.out.println("Inside instance method.");
    }

    public static void main(String[] args) {
        Example instance=new Example();
        s.o.p(instance.instanceMethod());
    }
}
```



##### In java all the primitive data types are passed by value and all the non primitive data types are passed by reference.

##### for ex-> if i pass cal(int a ,int b) then its will be pass by value;

##### but if i pass int A[]={1,2,3,4,5} ,
##### void swap(int A[]){
##### // then this will be passed by reference
##### }



### Method overloading

Method overloading in Java is ==a feature that allows a class to have multiple methods with the same name, provided their **parameter lists are different**==. This mechanism is a form of compile-time (static) polymorphism, and it enhances code readability and re-usability by allowing developers to use a single, intuitive method name for related operations that handle different types of input. 

Rules for Method Overloading

To successfully overload a method in Java, the methods must adhere to the following rules within the same class: 

- **Same Method Name:** All methods must share the same name.
- 
- **Different Parameter List:** The key requirement is that the parameter lists must differ. This difference can be achieved in three ways:
    - **Different number of parameters** (e.g., one method with two `int` parameters and another with three `int` parameters).
    - **Different data types of parameters** (e.g., one method with `int` parameters and another with `double` parameters).
    - **Different order of parameters** (e.g., one method with `String`, `int` and another with `int`, `String`).

- **Return Type Doesn't Matter:** The return type can be the same or different, but it alone is not sufficient to overload a method.

- **Access Modifiers Don't Matter:** Access modifiers (public, private, etc.) can be different.




#### Variable Argument 

In Java,**variable arguments (varargs)**, introduced in JDK 5, ==allow a method to accept a variable number of arguments of a specific type==. This feature simplifies method declarations and eliminates the need for method overloading to handle different argument counts. 

Key Concepts

- **Syntax:** A varargs parameter is defined using an ellipsis (`...`) after the data type in the method's parameter list, for example: `dataType... variableName`.
- **Internal Mechanism:** Internally, the Java compiler treats the varargs parameter as an array of the specified type.
- **Flexibility:** You can call a varargs method with zero or more arguments, passed as a comma-separated list or even an array. 

Rules and Usage

- **Single Varargs Parameter:** A method can have only one varargs parameter.
- **Last Parameter:** The varargs parameter must always be the last parameter in the method's signature to allow the compiler to differentiate it from other fixed parameters. 

java

```
public class VarargsExample {

    // Valid: combines a fixed parameter and a varargs parameter
    public static void display(String name, int... marks) {
        System.out.println("Student: " + name);
        System.out.print("Marks: ");
        // Inside the method, 'marks' is treated as an array
        for (int mark : marks) {
            System.out.print(mark + " ");
        }
        System.out.println();
    }

    // Invalid: varargs is not the last parameter
    // public static void displayInvalid(int... marks, String name) {}

    public static void main(String[] args) {
        // Calling the method with different number of arguments
        display("Alice", 85, 90, 95);
        display("Bob", 80, 88);
        display("Charlie"); // Calling with zero varargs arguments
    }
}
```