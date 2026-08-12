![[Pasted image 20260531012953.png]]
![[Pasted image 20260601160124.png]]
- In How Many Ways you can Reach the Destination.
### Using Tabulation 
	- It ta kes less space as compare to the Memoization in this only you have to iterate over the for loop.
- To reach every cell you have to go through some certain cells if you need 2 ways to reach to a cell then to reach the cell next to it will require dp[i-1][j] + dp[i][j-1] 
![[Pasted image 20260809155900.png]]
![[Pasted image 20260601171641.png]]
![[Pasted image 20260601171615.png]]
### Tabulation and Space Optimisation -
- You have to make a grid that is smaller as compare than m * n;
- So make one arr  2 * n
- and use iteration to walk over every cell and add the up and left value in it and then copy it in above cell and then repeat the process m-1 time till reach the mth row 
- return value at 2 and n-1;
![[Pasted image 20260809162850.png]]

```java
class Solution {
    public int uniquePaths(int m, int n) {
        if(m==1){
            return 1;
        }
        int[][] arr = new int[2][n];
        for(int i=0;i<n;i++){ // filling first row with 1
            arr[0][i] = 1;
        }
        arr[1][0] = 1; // filling second row first element with 1
        
        for(int i=1;i<m;i++){ // m-1 times so that you can reach the bottom 
           
           for(int k=1;k<n;k++){  // this is for adding the up and left value to the current cell and as there are n elements in a row so you have to find value at every cell so 1 to n-1 times for loop 
             arr[1][k] = arr[1][k-1] + arr[0][k];
           }
           
           // this is copy the value of current cell to the above cell and as there are n elements in a row so you have to copy every element so 1 to n-1 times for loop 
           for(int j=1;j<n;j++){
              arr[0][j] = arr[1][j];
           }
        }
        // return the second row last element 
        return arr[1][n-1];
    }
}
```

