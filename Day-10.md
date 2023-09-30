# Day 10 

### 1. How to Create an Object in Java?
- Using `new` keyword 
```java
MyClass myObject = new MyClass();
```
- Using **Object** Cloning
```java
MyClass myObject = new MyClass();
MyClass clonedObject = (MyClass) myObject.clone();
```
- Using Factory Methods
```java
MyClass myObject = MyClassFactory.createInstance();
```
- Using Anonymous Inner Classes: 
```java
Runnable runnable = new Runnable() {
    public void run() {
        // Implementation of run() method
    }
};
```
### 2. What is the use of a new keyword in Java?
- `new` keyword is used to create an instance or Object of a class.
### 3. What are the different types of variables in Java?
- Local Variables
- Instance Variables
- Static Variable
- Parameter Variables
- Static Variables
### 4. What is the difference between Instance variable and Local variables?
- Local variables exist for the duration of the method, constructor, or block in which they are declared.
On the other hand Instance variables exist for the lifetime of the object (instance) they are associated with.
### 5. In which area memory is allocated for instance variable and local variable?
- Local variables allocated into the stack memory while instance variables are allocated in the heap memory.
### 6. What is method overloading?
- Method overloading is a feature in Java (and many other object-oriented programming languages) that allows you to define multiple methods in the same class with the same name but different parameter lists.
```java
public class MathUtils {
    public int add(int a, int b) {
        return a + b;
    }
    public double add(double a, double b) {
        return a + b;
    }
    public int add(int a, int b, int c) {
        return a + b + c;
    }
}
```
