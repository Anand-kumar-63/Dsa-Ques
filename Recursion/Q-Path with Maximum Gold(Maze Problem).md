![[Pasted image 20260808200110.png]]
```java
class Solution {
    static int max = 0;
    public int getMaximumGold(int[][] arr) {
        max = 0;
        int m = arr.length;
        int n = arr[0].length;
        int[][] visited = new int[m][n];
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++){
                if (arr[i][j] != 0) {
                    helper(visited, arr, i, j , 0);
                }
            }
        }
        return max;
    }
    static void helper(int[][] visited , int[][] arr , int i , int j , int loot){
        int n = arr[0].length;
        int m = arr.length;
        // Check if it is zero
        if(arr[i][j]==0){
            return;
        }
        // Check if it is visited already
        if(visited[i][j]!=0){
            return;
        }
        //if not visited mark it visited
        visited[i][j] = -1;
        loot += arr[i][j];
        // add in loot
        max = Math.max(max, loot);
        if(i<m-1){
          helper(visited,arr,i+1,j,loot);
        }
        if(j<n-1){
          helper(visited,arr,i,j+1,loot);
        }
        if(i>0){
          helper(visited,arr,i-1,j,loot);
        }
        if(j>0){
          helper(visited,arr,i,j-1,loot);
        }          
        visited[i][j] = 0;
    }
}
```