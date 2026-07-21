It is used to find the **maximum sum subarray** in an array in **O(n)** time.
```
[-2,1,-3,4,-1,2,1,-5,4] array given
Find the contiguous subarray with the largest sum.
op-
[4,-1,2,1]
```
#### Core Idea
At every index, decide:
- Should we:
    - continue the current subarray?
- OR
    - start a new subarray from current element?
```
currentSum = max(nums[i], currentSum + nums[i])
maxSum = max(maxSum, currentSum)
```

```java
public class Kadane {
    public static int maxSubArray(int[] nums) {
        int currentSum = nums[0];
        int maxSum = nums[0];

        for(int i = 1; i < nums.length; i++) {
            currentSum = Math.max(nums[i], currentSum + nums[i]);
            maxSum = Math.max(maxSum, currentSum);
            if( currentSum < 0 ) currentSum = 0;
        }
        return maxSum;
    }
    public static void main(String[] args) {
        int[] nums = {-2,1,-3,4,-1,2,1,-5,4};
        System.out.println(maxSubArray(nums));
    }
}
```
#### why It Works
If the current sum becomes negative:-
```
currentSum < 0
```
Then carrying it forward will only reduce future sums.
So we discard it and start fresh:-
```java
simpler version

int sum = 0;  
int max = Integer.MIN_VALUE;  
  
for(int num : nums) {  
  
sum += num;  
  
max = Math.max(max, sum);  
  
if(sum < 0) {  
sum = 0;  
}  
}
```

Explanation- 
if any subarray sum is -ve Then Adding it in Forward will only reduce the subarray sum then we can exclude that sum subarray from further computations and start fresh from the index we are at.
and at the same time maximum sum is getting stored so if not able to find any max value greater than previous.
last return max_sum
### LeetCode 53
![[Pasted image 20260525002158.png]]

![[Pasted image 20260525002143.png]]



