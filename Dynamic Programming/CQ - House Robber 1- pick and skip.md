The **Pick and Skip** pattern is one of the most important concepts in Dynamic Programming.
It is used when, at every index, we have two choices:
```
1.Pick the current Element.
2.Skip the current Element.
```
Then we take the best answer according to the problem.
```
f(i) = max( pick, skip);
```
Where:-
- `pick`→ include current element
- `skip`→ ignore current element
#### Most Famous pick and skip Problem
![[Pasted image 20260528025743.png]]
![[Pasted image 20260528025754.png]]
#### Pick
If you rob current house:
```
nums[i] + solve(i+2)
```
Why `i+2`?
Because adjacent house cannot be picked.
#### Skip
If you skip current house:
```
solve(i+1)
```
#### Why DP Is Needed??
Recursion repeats same computations many times...
Example:-
```
solve(3)
```
May be called repeatedly.
So we store answers using:
- Memoization (Top Down)
- Tabulation (Bottom Up) - Iterative dp
```
class Solution {
    public int solve(int i, int[] nums, int[] dp) {
        if(i >= nums.length) {
            return 0;
        }
        if(dp[i] != -1) {
            return dp[i];
        }
        int pick = nums[i] + solve(i + 2, nums, dp);
        int skip = solve(i + 1, nums, dp);
        return dp[i] = Math.max(pick, skip);
    }
    public int rob(int[] nums) {
        int[] dp = new int[nums.length];
        Arrays.fill(dp, -1);
        return solve(0, nums, dp);
    }
}
```

![[Pasted image 20260528030629.png]]
### Using Tabulation
- That is also known as Iterative DP.
- You have to create an array that Contains  the max loot till that index of the Array.
![[Pasted image 20260624000242.png]]
See at index 0 the max loot is 6 and 
At index 1 the max loot can be the element at index 0 or the max loot till the [current index - 1]
At index 2 the max loot can be the element at [ index 2 + dp[i-2] ] or dp[i-1]  you have to find the max of both and push it into the DP
![[Pasted image 20260624001128.png]]


