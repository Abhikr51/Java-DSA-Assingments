# Day 16

### 1. WAP(Write a Program) to remove Duplicates from a String.(Take any String example with duplicates character)
```java
public class RemoveDuplicatesFromString {
    public static void main(String[] args) {
        String inputString = "programming";
        String resultString = removeDuplicates(inputString);

        System.out.println("Original string: " + inputString);
        System.out.println("String after removing duplicates: " + resultString);
    }
    public static String removeDuplicates(String str) {
        StringBuilder resultBuilder = new StringBuilder();
        boolean[] encountered = new boolean[256];
        
        for (int i = 0; i < str.length(); i++) {
            char currentChar = str.charAt(i);
            
            if (!encountered[currentChar]) {
                resultBuilder.append(currentChar);
                encountered[currentChar] = true;
            }
        }
        
        return resultBuilder.toString();
    }
}

```
### 2. WAP to print Duplicates characters from the String
```java
public class PrintDuplicateCharacters {
    public static void main(String[] args) {
        String inputString = "programming";
        System.out.println("Original string: " + inputString);

        String duplicates = findDuplicateCharacters(inputString);
        System.out.println("Duplicate characters: " + duplicates);
    }

    public static String findDuplicateCharacters(String str) {
        StringBuilder duplicatesBuilder = new StringBuilder();
        boolean[] encountered = new boolean[256]; // Assuming ASCII characters
        
        for (int i = 0; i < str.length(); i++) {
            char currentChar = str.charAt(i);
            
            if (!encountered[currentChar]) {
                encountered[currentChar] = true;
            } else if (duplicatesBuilder.indexOf(String.valueOf(currentChar)) == -1) {
                duplicatesBuilder.append(currentChar);
            }
        }
        
        return duplicatesBuilder.toString();
    }
}

```
### 3. WAP to check if "2552" is palindrome or not.
```java
public class PalindromeCheck {
    public static void main(String[] args) {
        String input = "2552";
        boolean isPalindrome = isPalindrome(input);

        if (isPalindrome) {
            System.out.println(input + " is a palindrome.");
        } else {
            System.out.println(input + " is not a palindrome.");
        }
    }

    public static boolean isPalindrome(String str) {
        int left = 0;
        int right = str.length() - 1;

        while (left < right) {
            if (str.charAt(left) != str.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }

        return true;
    }
}

```
### 4. WAP to count the number of consonants, vowels, special characters in a String.
```java
public class CountCharacters {
    public static void main(String[] args) {
        String inputString = "Hello, World!";

        int vowelCount = 0;
        int consonantCount = 0;
        int specialCharCount = 0;

        for (int i = 0; i < inputString.length(); i++) {
            char ch = Character.toLowerCase(inputString.charAt(i));
            
            if (Character.isLetter(ch)) {
                if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
                    vowelCount++;
                } else {
                    consonantCount++;
                }
            } else {
                specialCharCount++;
            }
        }

        System.out.println("Input string: " + inputString);
        System.out.println("Vowels: " + vowelCount);
        System.out.println("Consonants: " + consonantCount);
        System.out.println("Special characters: " + specialCharCount);
    }
}

```
### 5. WAP to implement Anagram Checking least inbuilt methods being used.
```java
public class AnagramCheck {
    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";

        if (areAnagrams(str1, str2)) {
            System.out.println(str1 + " and " + str2 + " are anagrams.");
        } else {
            System.out.println(str1 + " and " + str2 + " are not anagrams.");
        }
    }

    public static boolean areAnagrams(String str1, String str2) {
        str1 = str1.replaceAll("\\s", "").toLowerCase();
        str2 = str2.replaceAll("\\s", "").toLowerCase();

        if (str1.length() != str2.length()) {
            return false;
        }

        int[] charCount = new int[256];

        for (int i = 0; i < str1.length(); i++) {
            charCount[str1.charAt(i)]++;
        }

        for (int i = 0; i < str2.length(); i++) {
            charCount[str2.charAt(i)]--;
        }
        for (int i = 0; i < 256; i++) {
            if (charCount[i] != 0) {
                return false;
            }
        }

        return true;
    }
}
```
### 6. WAP to implement Pangram Checking with least inbuilt methods being used.
```java
public class PangramCheck {
    public static void main(String[] args) {
        String inputString = "The quick brown fox jumps over the lazy dog";

        if (isPangram(inputString)) {
            System.out.println("The string is a pangram.");
        } else {
            System.out.println("The string is not a pangram.");
        }
    }

    public static boolean isPangram(String str) {
        boolean[] isPresent = new boolean[26];

        str = str.toLowerCase();
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);

            if (ch >= 'a' && ch <= 'z') {
                isPresent[ch - 'a'] = true;
            }
        }
        for (boolean letterPresent : isPresent) {
            if (!letterPresent) {
                return false;
            }
        }

        return true;
    }
}
```
### 7. WAP to find if String contains all unique characters.
```java
public class UniqueCharactersCheck {
    public static void main(String[] args) {
        String inputString = "abcdefg";

        if (containsUniqueCharacters(inputString)) {
            System.out.println("The string contains all unique characters.");
        } else {
            System.out.println("The string does not contain all unique characters.");
        }
    }

    public static boolean containsUniqueCharacters(String str) {
        boolean[] isPresent = new boolean[256];

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            if (isPresent[ch]) {
                return false; 
            }
            isPresent[ch] = true;
        }

        return true;
    }
}
```
### 8. WAP to find the maximum occurring character in a String
```java
public class MaxOccurringCharacter {
    public static void main(String[] args) {
        String inputString = "programming";
        char maxOccurringChar = findMaxOccurringCharacter(inputString);
        System.out.println("Input string: " + inputString);
        System.out.println("Maximum occurring character: " + maxOccurringChar);
    }

    public static char findMaxOccurringCharacter(String str) {
        int[] charCount = new int[256];

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            charCount[ch]++;
        }

        char maxChar = '\0';
        int maxCount = 0;
        for (int i = 0; i < 256; i++) {
            if (charCount[i] > maxCount) {
                maxChar = (char) i;
                maxCount = charCount[i];
            }
        }
        return maxChar;
    }
}
```