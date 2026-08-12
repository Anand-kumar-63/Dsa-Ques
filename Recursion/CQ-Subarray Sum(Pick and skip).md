![[Pasted image 20260802232325.png]]
```java
    class Solution {
    	static boolean isSubsetSum(int arr[], int sum) {
    		int[][] dp = new int[arr.length][sum + 1];
    		int ans = helper(0, arr, sum, 0, dp);
    		if (ans == -1) {
    			return false;
    		}
    		else {return true; }
    	}
    	static int helper(int idx, int[] arr, int sum, int ans, int[][] dp) {
    		if (ans == sum) {
    			return 1;
    		}
    		if (idx >= arr.length || ans > sum) {
    			return - 1;
    		}
    		if (dp[idx][ans] != 0) {
    			return dp[idx][ans];
    		}
    		int pick = helper(idx + 1, arr, sum, ans + arr[idx], dp);
    		int skip = helper(idx + 1, arr, sum, ans, dp);
    		return dp[idx][ans] = pick == 1?pick:skip == 1?skip:-1;
    	}
    }
```
- while using dp you have to always check for the Changing Values  here idx and ans both are changing
- if idx== 3 and ans=11 its -1
- if idx== 3 and ans =8 its 1
  Because we can skip the values in Between 