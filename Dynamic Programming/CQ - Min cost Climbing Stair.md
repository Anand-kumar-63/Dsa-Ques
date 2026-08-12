- Explanation you have to select between the { next } or { next to next stair } selecting the current element.
- Tmne Current stair select Kri and now you have to select between next stair or next to next stair sum of [arr[i]+(i+1)]  is smaller or the sum of [arr[i]+(i+2)] this is.

Memoisation - min cost from that particular stair to the top
arr[i] + min(arr[i+1],arr[i+2]);
![[Pasted image 20260528185001.png]]

![[Pasted image 20260528145056.png]]

```
//Back-end complete function Template for Java
class Solution {
    static int dp[];
    static int minCostClimbingStairs(int[] cost) {
        // Write your code here
        int n = cost.length;
        dp = new int[n];
        Arrays.fill(dp,-1);
        return Math.min(mincost(0,cost),mincost(1,cost));
    }
    static int mincost(int i , int[] arr){
        if(i >= arr.length) return 0;
        
        if(dp[i]!=-1) return dp[i];
        
        int step = mincost(i+1,arr);
        int stepskip = mincost(i+2,arr);
        
        dp[i] = arr[i] + Math.min(step,stepskip);
        
        return dp[i];
    }
};
```
## Using Tabulation 


![[Pasted image 20260809154313.png]]
![[Pasted image 20260624012339.png]]


### Tabulation and Memoisation 
- in Memoization - you have to find the min/max cost from the ith index to the end and in memoisation dp fill in backward direction

  
- In tabulation - you have to find the min/max cost till the ith index from the start and dp fill from the start 
![[Pasted image 20260809155042.png]]
- Example of Tabulation-
![[Pasted image 20260809155532.png]]