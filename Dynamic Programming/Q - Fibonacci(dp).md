- using recursion > tc->0(2^n)  , sc->(nlogn)
- using memoisation dp > tc-0(2n) , sc-0(2n) 
- using tabulation dp > tc - 0(n) , sc-0(n)
- using space optimisation tabulation dp > tc - 0(n)  ,  sc - 0(1)  
```java
// using tabulation and space optimisation
class Solution {
    public int fib(int n) {
        if(n==1){
            return 1;
        }
        if(n==2){
            return 1;
        }
        int dp[]= new int[3];
        dp[0]=0;
        dp[1]=1;
        for(int i=0;i<n-1;i++){
            dp[2] = dp[0]+dp[1];
            dp[0]= dp[1];
            dp[1] = dp[2];
        }  
        return dp[2];
    }
}
```