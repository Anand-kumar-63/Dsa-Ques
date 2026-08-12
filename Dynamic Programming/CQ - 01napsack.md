![[Pasted image 20260810001749.png]]
- We have to  combine all the possible combinations.
  using pick and skip with some conditions.
- first check if the W-wt[idx]<0 then pick = skip;
- If idx == val.length  or W==  0 return 0;
- And for dp use the variables that are changing like W and idx both make a 2D dp
```java
class Solution {
    static int max = 0;
    public int knapsack(int W, int val[], int wt[]) {
        // code here
        int[][] dp = new int[val.length][W+1];
        return helper(dp,W,val,wt,0);
    }
    static int helper(int[][] dp,int C,int[] val, int[] wt,int idx){
        if(C<0){
            return 0;
        }
        if(idx == val.length || C==0){
            return 0;
        } 
        if(dp[idx][C]!=0){
            return dp[idx][C];
        }
        int pick = val[idx] + helper(dp,C-wt[idx],val,wt,idx+1);
        int skip = helper(dp,C,val,wt,idx+1); 
        if(C-wt[idx] < 0 ) pick = skip;
        
        dp[idx][C] = Math.max(pick , skip);
        return Math.max(pick , skip);
    }
}

```