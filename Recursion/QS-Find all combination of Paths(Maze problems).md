- Find all the possible ways to reach the Destination Position.
- We can go in all directions up(for backtracking)  , vertical , horizontal
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[][] maze = new int[n][n];
        String str = "";
        helper(maze, str, 0, 0, n);
    }
    static void helper(int[][] maze, String str, int i, int j, int n) {
        // Already visited
        if (maze[i][j] != 0) {
            return;
        }
        // Reached destination
        if (i == n - 1 && j == n - 1) {
            System.out.println(str);
            return;
        }
        // Mark visited
        maze[i][j] = -1;
        if (i < n - 1) {
            helper(maze, str + "D", i + 1, j, n);
        }
        if (j < n - 1) {
            helper(maze, str + "R", i, j + 1, n);
        }
        if (i > 0) {
            helper(maze, str + "U", i - 1, j, n);
	        }
        if (j > 0) {
            helper(maze, str + "L", i, j - 1, n);
        }
        // Backtrack
        maze[i][j] = 0;
    }
}
```

### Flood Fill 
![[Pasted image 20260807235656.png]]
![[Pasted image 20260807235703.png]]