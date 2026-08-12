![[Pasted image 20260810232345.png]]
- When sum gets substracted it goes in negative values and dp Cannot go in Negative Indexing to save the dp value at that particular index and sum so we have to take an offset to add it in the original sum to make it positive. and then you can use the dp 
- When `sum` becomes negative, we cannot use it directly as an index because Java arrays do not support negative indexing.

	Therefore, we use an **offset** to shift every possible `sum` into the valid range of the DP array.
	Since the maximum possible absolute value of `sum` is `totalSum`, the possible range is:
	`-totalSum` to `+totalSum`
	
	So we use:
	`offset = totalSum`
	and store the state at:
	`dp[idx][sum + offset]`
	
	For example, if `totalSum = 5`:
	`sum = -5 → index = 0`
	`sum = 0 → index = 5`
	`sum = +5 → index = 10`
	Therefore, the DP size is:

`dp[arr.length][2 * totalSum + 1]`
```java
class Solution {
	public int totalWays(int[] arr, int target) {
		// code here
		int sum = 0;
		for(int i=0;i<arr.length;i++){
		    sum += arr[i];
		}
		// dp size [arr.length][sum+sum+1] for -sum+offset(eg. -5+5 = 0) to sum+offset(5+5 = 10)
		int[][] dp = new int[arr.length][sum+sum+1];
		
		int offset = sum;
		
		for(int[] item:dp){
		  for(int i=0;i<item.length;i++){
		     item[i] = -1;
		}}
		//in recursion i = 0 to n-1 and sum goes from -sum(if 0 -item at every recursion call) 
		// to +sum(of 0 +item at every recursion call)
		// so for dp you have to use a offset that sums up the sum to 0 to positive values because dp 2d matrix cannot go negative indexes
		return target(0 , dp , arr , target , 0 , offset);
	}
	static int target(int k , int[][] dp , int[] arr , int target , int sum , int offset){
		if (k == arr.length) {
			if (sum == target)
				return 1;
			else
				return 0;
		}
		// dp offset use to make sum positive or zero
        // dp size [arr.length][sum+sum+1] for -sum+offset(eg. -5+5 = 0) to   sum+offset(5+5 = 10)
        // Possible sum range: -sum to +sum 
        // offset = sum 
        // DP index = currentSum + offset 
        // -sum + offset = 0 
        // +sum + offset = 2 * sum 
        // Therefore DP size = [arr.length][2 * sum + 1]
        
		if(dp[k][sum+offset]!=-1){
		    return dp[k][sum+offset];
		}
		int add = target(k + 1,dp, arr, target, sum + arr[k],offset);
		int sub = target(k + 1,dp, arr, target, sum - arr[k],offset);
		return dp[k][offset+sum] = add + sub;
	}
}

```