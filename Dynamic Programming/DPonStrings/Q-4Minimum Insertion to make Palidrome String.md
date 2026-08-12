![[Pasted image 20260812185944.png]]
- length - Palindromic Subsequence
```java
class Solution {

    public int minInsertions(String s) {

        return s.length() - lcs(s);

    }

    static int lcs(String s) {

        StringBuilder a = new StringBuilder(s);

        StringBuilder b = new StringBuilder(s).reverse();

        int[][] dp = new int[a.length()][b.length()];

        for(int[] arr:dp){

            for(int i=0; i<arr.length; i++){

                 arr[i] = -1;

            }

        }

        int i = a.length()-1;

        int j = b.length()-1;

        return helper(dp,i,j,a,b);

    }

    static int helper(int[][] dp , int i , int j , StringBuilder a , StringBuilder b){

        if(i<0||j<0){

            return 0;

        }

        if(dp[i][j]!=-1){

             return dp[i][j];

        }

        if(a.charAt(i) == b.charAt(j)){

            return dp[i][j] = 1 + helper(dp,i-1,j-1,a,b);

        }

        else{

            return dp[i][j] = Math.max(helper(dp,i-1,j,a,b),helper(dp,i,j-1,a,b));

        }

    }

}
```