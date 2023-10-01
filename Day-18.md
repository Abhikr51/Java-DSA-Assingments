# Day 18

### 1.Why do we need static keyword in Java Explain with an example?
-  `static` keyword is used to define members (variables and methods) that belong to a class rather than to an instance of the class. This means that static members are shared among all instances of the class, and you can access them without creating an object of the class. There are several reasons why you might use the `static` keyword:
```java
class MyClass {
    static int instanceCount = 0;

    int data;

    public MyClass(int data) {
        this.data = data;
        instanceCount++;
    }

    static int getInstanceCount() {
        return instanceCount;
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating two instances of MyClass
        MyClass obj1 = new MyClass(10);
        MyClass obj2 = new MyClass(20);

        // Accessing instanceCount using the class name
        System.out.println("Number of instances created: " + MyClass.getInstanceCount()); // Output: 2

        // Accessing instanceCount using an object (not recommended)
        System.out.println("Number of instances created: " + obj1.instanceCount); // Output: 2
    }
}
```

### 2. What is class loading and how does the Java program actually executes?
- Class loading is a crucial step in the execution of Java programs. It is a process by which the Java Virtual Machine (JVM) loads the classes and interfaces used by a Java program into memory. The class loading process involves the following steps:

    - Loading
    - Linking
    - Initialization

### 3. Can we mark a local variable as static
- No, we cannot mark a local variable as static in Java. The static keyword is used to define members (variables and methods) at the class level, not at the method or block level. Local variables are limited in scope to the method or block in which they are declared and are not associated with a class.

### 4. Why is the static block executed before the main method in java?
- `static` block is executed before the main method because it's part of the class initialization process, and it allows you to perform necessary setup tasks before your program's entry point is reached.
### 5. Why is a static method also called a class method?
- A `static` method in Java is also commonly referred to as a "class method" because it is associated with the class itself, rather than with any specific instance of the class. The term "class method" emphasizes the fact that you can call the method on the class directly, without needing to create an instance of the class.

### 6. What is the use of static blocks in java? 
- Initializing Static Variables.
- Loading Native Libraries
- Resource Acquisition and Setup
- One-Time Tasks
### 7. Difference between Static and Instance variables 
| Static Variable                                       | Instance Variable                                         |
|------------------------------------------------------|------------------------------------------------------------|
| Class (shared among all instances)                   | Each instance of the class (unique to each object)       |
| Declared using the `static` keyword                  | Declared without the `static` keyword                     |
| Allocated memory once for the class                  | Allocated memory separately for each object              |
| Initialized only once (usually in a static block)     | Initialized individually for each object (in constructors) |
| Accessed using the class name                         | Accessed using an instance of the class                   |
| Modified using the class name                        | Modified using an instance of the class                   |
| Shared among all instances of the class               | Specific to each object, not shared                      |
| Counters, configuration values, global constants     | Object-specific attributes, instance-specific settings    |
| Can be used directly in static methods               | Cannot be accessed directly in static methods              |
| Can be accessed indirectly via class name or object | Can be accessed directly using the instance              |
| Available throughout the lifetime of the program    | Available as long as the object exists                   |

### 8. Difference between static and non static members.
| Static Members                 | Non-Static (Instance) Members  |
|--------------------------------|-------------------------------|
| Associated with                | Class                         |
| Declaration                     | `static` keyword not used     |
| Memory Allocation               | Allocated once for the class  | Allocated for each instance   |
| Initialization                  | Initialized once (static block)| Initialized individually      |
| Access                          | Accessed using the class name  | Accessed using the instance   |
| Modification                    | Modified using the class name | Modified using the instance   |
| Sharing Data                    | Shared among all instances    | Specific to each instance     |
| Use Cases                       | Counters, global constants   | Object-specific attributes    |
| Accessibility in Static Methods | Directly accessible           | Not directly accessible      |
| Accessibility in Instance Methods| Accessed indirectly            | Accessed directly            |
| Scope                           | Throughout the program        | As long as the object exists |
