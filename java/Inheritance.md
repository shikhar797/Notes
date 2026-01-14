
1.Parent class constructor is not inherited in the child class .


2. In java, ****super**** keyword is used to access methods of the ****parent class**** while ****this**** is used to access methods of the ****current class****.

ex->this
 
`class Person {`
    `String name;`
    `Person(String name) {`
        `this.name = name; // 'this.name' is the instance variable, 'name' is the parameter`
    `}`
    `void display() {`
        `System.out.println("Name: " + this.name);`
    `}`
`}`

ex->super

```
class Employee extends Person {
    int employeeId;
    Employee(String name, int id) {
        super(name); // Calls Person(String name) constructor
        this.employeeId = id;
    }
    void display() {
        super.display(); // Calls Person.display()
        System.out.println("ID: " + employeeId);
    }
}
```


3. super_class instance =new sub_class() this allowed in java 
