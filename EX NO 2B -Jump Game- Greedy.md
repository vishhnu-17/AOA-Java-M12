
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 14-10-2025
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. Track the farthest reachable index while scanning the array from left to right.  
2. If the current index ever exceeds the farthest reachable position, return false.  
3. Update the reachable position using max(pos, i + nums[i]) at each step.  
4. Continue expanding the maximum jump window as long as reachable.  
5. If the loop finishes without failing, the last index is reachable.

### Developed By : Kurapati Vishnu Vardhan Reddy
### Register Number : 212223040103


## Program:
```java
import java.util.*;

public class JumpGame {

    // Function to check if we can reach the last index
    public static boolean canReachLastIndex(int[] nums) {
        int pos=0;
        for(int i=0;i<nums.length;i++){
            if(i>pos)return false;
            pos=Math.max(pos,i+nums[i]);
        }
        return true;
    }

    // Main method for input and calling the function
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Size of array
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt(); // Elements of array
        }

        System.out.println("Can reach last index: " + canReachLastIndex(nums));
    }
}

```

## Output:

<img width="740" height="253" alt="image" src="https://github.com/user-attachments/assets/26a8779c-2ed8-4eed-8ee4-889b63aeb391" />


## Result:
The program successfully implemented and the expected output is verified.
