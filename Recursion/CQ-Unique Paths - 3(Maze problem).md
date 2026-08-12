![[Pasted image 20260808011628.png]]
```java
    class Solution {
        static int count = 0;
        static int obs = 0;
        public int uniquePathsIII(int[][] arr) {
            count = 0;
            obs = 0;
            int m = arr.length;
            int n = arr[0].length;
            int si =0;
            int sj=0;
            for (int i = 0; i < m; i++) {
                for (int j = 0; j < n; j++) {
                    if (arr[i][j] == 1) {
                        si = i;
                        sj = j;
                    }
                    if (arr[i][j] == -1) {
                        obs++;
                    }
                }
            }
            int[][] maze = new int[m][n];
            helper(maze, arr, si, sj, 0);
            return count;
        }
        static void helper(int[][] maze, int[][] arr, int i, int j, int c) {
            int m = arr.length;
            int n = arr[0].length;
            if (arr[i][j] == -1) return;
            if (maze[i][j] != 0) return;
            if (arr[i][j] == 2) {
                    int res = (m * n) - 1 - obs;
                    if (c == res) {
                        count++;
                    }
                    return;
            }
            maze[i][j] = -2;
            if (i < m - 1) {
                helper(maze, arr, i + 1, j, c + 1);
            }
            if (j < n - 1) {
                helper(maze, arr, i, j + 1, c + 1);
            }
            if (i > 0) {
                helper(maze, arr, i - 1, j, c + 1);
            }
            if (j > 0) {
                helper(maze, arr, i, j - 1, c + 1);
            }
            maze[i][j] = 0;
        }
    }
```
- Check obstacle and count it before calling the function.
- Make an visited 2d array and mark it -2 for visiting  and 0 for exiting the function.
	- and apply backtracking using every possible combination to visit