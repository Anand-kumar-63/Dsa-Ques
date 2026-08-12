![[Pasted image 20260808190449.png]]
```java
class Solution {
    static boolean result = false;
    public boolean exist(char[][] arr, String word) {
        int m = arr.length;
        int n = arr[0].length;
        int si = 0;
        int sj = 0;
        if (m == 1 && n == 1 && word.length() == 1) {
            return arr[m - 1][n - 1] == word.charAt(0);
        }
        int[][] maze = new int[m][n];
        result = false;
        String ans = "";
        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr[0].length; j++) {
                helper(maze, arr, word, 0, i, j);
            }
        }
        return result;
    }
    static void helper(int[][] maze, char[][] arr, String word, int idx, int i, int j) {
        int m = arr.length;
        int n = arr[0].length;
        if (idx == word.length()) {
            result = true;
            return;
        }
        if (i < 0 || i > m - 1 || j < 0 || j > n - 1) {
            return;
        }
        if (maze[i][j] != 0) {
            return;
        }
        if (arr[i][j] == word.charAt(idx)) {
            idx++;
        } else {
            return;
        }
        maze[i][j] = -1;
        helper(maze, arr, word, idx, i + 1, j);
        helper(maze, arr, word, idx, i, j + 1);
        helper(maze, arr, word, idx, i - 1, j);
        helper(maze, arr, word, idx, i, j - 1);
        maze[i][j] = 0;
    }
    
}
```