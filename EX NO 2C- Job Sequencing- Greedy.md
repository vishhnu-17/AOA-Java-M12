# EX 2C Job Sequencing using Greedy Approach
## DATE: 14-10-2025

## AIM:
To write a Java program for given constraints.
You're given N jobs, each with:

- A unique jobId
- A deadline (by which it must be completed)
- A profit (earned only if completed on or before the deadline)

Each job:
- Takes exactly 1 unit of time  
- Only one job can be done at a time  

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm
1. Sort all jobs in descending order of profit to prioritize high-profit tasks.  
2. Find the maximum deadline and create an array of time-slots.  
3. For each job, check backwards from its deadline to find an empty slot.  
4. If a free slot exists, schedule the job and add its profit.  
5. Return the number of jobs completed and the total profit earned.

### Developed by: Kurapati Vishnu Vardhan Reddy 
### Register Number: 212223040103

## Program:
```java
import java.util.*;

public class JobScheduling {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static int[] jobScheduling(Job[] jobs, int n) {
        
        Arrays.sort(jobs,(a,b)-> Integer.compare(b.profit,a.profit));
        
        int maxd=0;
        for(Job job:jobs){
            maxd=Math.max(maxd,job.deadline);
        }
        
        int[] slot = new int[maxd+1];
        Arrays.fill(slot,-1);
        
        int count=0;
        int profit=0;
        
        for(Job job:jobs){
            for(int j=job.deadline;j>0;j--){
                if(slot[j]==-1){
                    slot[j]=job.id;
                    count++;
                    profit+=job.profit;
                    break;
                }
            }
        }
        
        return new int[]{count,profit};
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();
            jobs[i] = new Job(id, deadline, profit);
        }

        int[] result = jobScheduling(jobs, n);
        System.out.println(result[0] + " " + result[1]);
    }
}
```

## Output:
<img width="363" height="435" alt="image" src="https://github.com/user-attachments/assets/2eb3802d-0b69-414d-84d4-d2306d6f6f5d" />

## Result:
The program successfully implemented and the expected output is verified.
