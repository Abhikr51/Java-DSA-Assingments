# Day 14

### 1. Write a simple String program to take input from user
```java
import java.util.Scanner;

public class UserInputStringExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String userInput = scanner.nextLine();
        scanner.close();
        System.out.println("You entered: " + userInput);
    }
}

```
### 2. How do you concatenate two strings in Java? Give an example?
- Using the + Operator: You can use the + operator to concatenate strings. When you use + between two string operands, Java automatically combines them into a single string.
```java
String str1 = "Hello, ";
String str2 = "World!";
String result = str1 + str2;
System.out.println(result);
```
### 3. How do you find the length of a string in Java Explain with an example?
- In Java, we can find the length (number of characters) of a string using the length() method provided by the java.lang.String class. Here's how you can use it with an example:
```java
public class StringLengthExample {
    public static void main(String[] args) {
        // Define a string
        String myString = "Hello, World!";

        // Find the length of the string
        int length = myString.length();

        // Display the length of the string
        System.out.println("The length of the string is: " + length);
    }
}
```
### 4. How do you compare two strings in Java? Give an Example
- Most reliable way to compare two strings is to use `compare()` method.
```java
String str1 = "Hello";
String str2 = "World";
boolean areEqual = str1.equals(str2);

if (areEqual) {
    System.out.println("The strings are equal.");
} else {
    System.out.println("The strings are not equal.");
}
```
### 5. Write a program to find the length of the string "refrigerator".
```java
public class StringLengthExample {
    public static void main(String[] args) {
        String str = "refrigerator";
        int length = str.length();
        System.out.println("The length of the string is: " + length);
    }
}
```
### 6. Write a program to check if the letter 'e' is present in the word 'Umbrella'.
```java
public class isPresentCharacter {
    public static void main(String[] args) {
        String word = "Umbrella";
        boolean containsE = word.contains("e");
        if (containsE) {
            System.out.println("'e' is present in the word.");
        } else {
            System.out.println("'e' is not present in the word.");
        }
    }
}
```
### 7. Write a program to delete all consonants from the string "Hello, have a good day".

```java
public class RemoveConsonantsExample {
    public static void main(String[] args) {
        String inputString = "Hello, have a good day";
        StringBuilder resultBuilder = new StringBuilder();

        for (int i = 0; i < inputString.length(); i++) {
            char currentChar = inputString.charAt(i);
            if (isVowel(currentChar) || currentChar == ' ') {
                resultBuilder.append(currentChar);
            }
        }
        String resultString = resultBuilder.toString();
        System.out.println("Original string: " + inputString);
        System.out.println("String with consonants removed: " + resultString);
    }
    public static boolean isVowel(char c) {
        c = Character.toLowerCase(c);
        return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u';
    }
}
```