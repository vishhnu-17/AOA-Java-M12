# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 14-10-2025
## AIM:
To write a Java program for the following constraints.  
Longest Palindromic Substring  
Given a string **s**, return the longest palindromic substring in **s**,  
using **Manacher's Algorithm**.

## Algorithm
1. Insert separators between characters to transform the string for uniform palindrome expansion.  
2. Maintain arrays and pointers (P-array, center, right boundary) to track palindrome radii.  
3. For each position, mirror the palindrome length from the opposite side when possible for optimization.  
4. Expand around each center to find the maximum palindrome radius.  
5. Convert the transformed indices back to the original string and return the longest palindromic substring.

### Developed by: Kurapati Vishnu Vardhan Reddy
### Register Number: 212223040103

## Program:
```java
import java.util.Scanner;

public class Solution {
    public String longestPalindrome(String s) {

        if (s == null || s.length() == 0) return "";

        StringBuilder t = new StringBuilder();

        t.append('^');
        for (char c : s.toCharArray()) {
            t.append('#');
            t.append(c);
        }
        t.append("#$");
        char[] str = t.toString().toCharArray();

        int n = str.length;
        int[] P = new int[n];
        int C = 0, R = 0;
        int maxLen = 0, centerIndex = 0;

        for (int i = 1; i < n - 1; i++) {
            int mirror = 2 * C - i;

            if (i < R)
                P[i] = Math.min(R - i, P[mirror]);

            while (str[i + P[i] + 1] == str[i - P[i] - 1])
                P[i]++;

            if (i + P[i] > R) {
                C = i;
                R = i + P[i];
            }

            if (P[i] > maxLen) {
                maxLen = P[i];
                centerIndex = i;
            }
        }

        int start = (centerIndex - maxLen) / 2;
        return s.substring(start, start + maxLen);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

        Solution sol = new Solution();
        String result = sol.longestPalindrome(input);

        System.out.println("Longest Palindromic Substring: " + result);
        scanner.close();
    }
}
```

## Output:

<img width="831" height="209" alt="image" src="https://github.com/user-attachments/assets/e73b7be2-93db-48c8-9125-49e8b298c3d3" />

## Result:
The program successfully implemented and the expected output is verified.
