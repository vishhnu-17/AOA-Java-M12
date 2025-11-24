
# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE: 14-10-2025
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1. Sort the children’s greed factors and cookie sizes in non-decreasing order.  
2. Use two pointers to try matching each child with the smallest possible cookie.  
3. Move the cookie pointer forward for every cookie checked.  
4. Increase the child pointer only when a cookie can satisfy that child’s greed.  
5. Return the total number of children successfully matched with cookies.

### Developed By: Kurapati Vishnu Vardhan Reddy
### Register Number: 212223040103

## Program:
```java
import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        
        int i=0;
        for(int j=0;i<g.length && j<s.length;j++){
            if(g[i]<=s[j])i++;
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}

```

## Output:

<img width="360" height="349" alt="image" src="https://github.com/user-attachments/assets/588167b3-0926-401c-b356-2bc3ced77f43" />


## Result:
The program successfully print all the numbers from 1 to N. 
