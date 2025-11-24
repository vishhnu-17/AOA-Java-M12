# EX 2D Pattern Matching using Naive Approach.
## DATE: 14-10-2025
## AIM:
To write a Java program to for given constraints.  
Given text string with length n and a pattern with length m, the task is to print all occurrences of the pattern in the text.  
Note: You may assume that n > m.

Examples:

Input: text = "THIS IS A TEST TEXT", pattern = "TEST"  
Output: Pattern found at index 10  

Input: text = "AABAACAADAABAABA", pattern = "AABA"  
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12  

## Algorithm
1. Read the input text and pattern strings.
2. Iterate through the text from index 0 to n–m.
3. For each index, compare the pattern with the substring of the text character by character.
4. If all characters match, record the starting index as a pattern match.
5. Continue until the entire text is checked and print all matched positions.

### Developed by: Kurapati Vishnu Vardhan Reddy
### Register Number: 212223040103

## Program:
```java
import java.util.Scanner;

public class NaivePatternSearch {
    static void search(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();

        for (int i = 0; i <= n - m; i++) {
            int j;

            // Check for pattern match character by character
            for (j = 0; j < m; j++) {
                if (text.charAt(i + j) != pattern.charAt(j))
                    break;
            }

            // If pattern found
            if (j == m)
                System.out.println("Pattern found at index " + i);
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String text = scanner.nextLine();
        String pattern = scanner.nextLine();

        search(text, pattern);

        scanner.close();
    }
}
```

## Output:

<img width="764" height="275" alt="image" src="https://github.com/user-attachments/assets/07dfda06-9799-4673-b8dd-601493a954bb" />


## Result:
The program successfully implemented and the expected output is verified.
