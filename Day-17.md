# Day 17

### 1. What is Mutable String in Java Explain with an example
- In Java, strings are typically immutable, meaning that once you create a string object, you cannot change its content. Any operation that appears to modify a string actually creates a new string object with the modified content. However, there are mutable alternatives for working with strings in Java, such as StringBuilder and StringBuffer.
```java
public class MutableStringExample {
    public static void main(String[] args) {
        // Create a StringBuilder with an initial value
        StringBuilder stringBuilder = new StringBuilder("Hello, ");

        // Append additional text
        stringBuilder.append("world!");

        // Insert text at a specific position
        stringBuilder.insert(7, "Java ");

        // Replace text
        stringBuilder.replace(0, 5, "Hi");

        // Delete characters
        stringBuilder.delete(3, 6);

        // Convert the StringBuilder to a String
        String result = stringBuilder.toString();

        // Print the result
        System.out.println(result); // Output: "Hi, Java world!"
    }
}
```
### 2. WAP to reverse a String
```bash
Input: "PWSKILLS" 
Output: "SLLIKSPW"
```
```java
//Solution
public class ReverseString {
    public static void main(String[] args) {
        String input = "PWSKILLS";
        String reversed = reverseString(input);
        System.out.println("Original String: " + input);
        System.out.println("Reversed String: " + reversed);
    }

    public static String reverseString(String str) {
        char[] charArray = str.toCharArray();
        int left = 0;
        int right = charArray.length - 1;

        while (left < right) {
            // Swap characters at left and right pointers
            char temp = charArray[left];
            charArray[left] = charArray[right];
            charArray[right] = temp;

            // Move the pointers towards the center
            left++;
            right--;
        }

        return new String(charArray);
    }
}
```
### 3. WAP to reverse a sentence while preserving the position
```bash
Input: Think Twice
Output: "kniht eciwt" 
```
```java
//Solution
public class ReverseWordCharacters {
    public static void main(String[] args) {
        String sentence = "Think Twice";
        String reversedSentence = reverseWordCharacters(sentence);
        
        System.out.println("Original Sentence: " + sentence);
        System.out.println("Reversed Sentence: " + reversedSentence);
    }

    public static String reverseWordCharacters(String sentence) {
        String[] words = sentence.split(" ");

        StringBuilder reversedBuilder = new StringBuilder();

        for (String word : words) {

            String reversedWord = reverseString(word);
            reversedBuilder.append(reversedWord).append(" ");
        }

        return reversedBuilder.toString().trim();
    }

    public static String reverseString(String str) {

        char[] charArray = str.toCharArray();

        int left = 0;
        int right = charArray.length - 1;
        while (left < right) {
            char temp = charArray[left];
            charArray[left] = charArray[right];
            charArray[right] = temp;
            left++;
            right--;
        }
        return new String(charArray);
    }
}

```
### 4. WAP to sort a String Alphabetically
```java
import java.util.Arrays;

public class SortStringAlphabetically {
    public static void main(String[] args) {
        String input = "programming";
        String sortedString = sortStringAlphabetically(input);
        
        System.out.println("Original String: " + input);
        System.out.println("Sorted String: " + sortedString);
    }

    public static String sortStringAlphabetically(String str) {
        // Convert the string to a character array
        char[] charArray = str.toCharArray();

        // Sort the character array
        Arrays.sort(charArray);

        // Convert the sorted character array back to a string
        return new String(charArray);
    }
}
```