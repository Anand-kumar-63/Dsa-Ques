![[Pasted image 20260809005338.png]]
```java
class Solution {
    public int numIslands(char[][] arr) {
        int m = arr.length;
        int n = arr[0].length;
        int[][] visited = new int[m][n];
        int count = 0;
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (arr[i][j] != '0' && visited[i][j] != -1) {
                    helper(visited, arr, i, j);
                    count++;
                }
            }
        }
        return count;
    }
    static void helper(int[][] visited, char[][] arr, int i, int j) {
        int n = arr[0].length;
        int m = arr.length;
        // Check if it is zero
        // Check if it is visited already
        if (visited[i][j] != 0) {
            return;
        }
        //if not visited mark it visited
        visited[i][j] = -1;
        if (arr[i][j] == '0') {
            return;
        }
        if (i < m - 1) {
            helper(visited, arr, i + 1, j);
        }
        if (j < n - 1) {
            helper(visited, arr, i, j + 1);
        }
        if (i > 0) {
            helper(visited, arr, i - 1, j);
        }
        if (j > 0) {
            helper(visited, arr, i, j - 1);
        }
    }
}
```