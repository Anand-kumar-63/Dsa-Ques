![[Pasted image 20260811165836.png]]
- In this take two pointer and same skip and skip variation 
- start with last index of both and then move backwards in one string and then in other and return of max among both..
- if both equal then return 1 + both slides by 1 
- if both not equal then return  i slides by 1 or j slides by 1 and return max among them
![[Pasted image 20260811170401.png]]
```java
class Solution {
    public int lcs(String s1, String s2) {
        // code here
        int n = s1.length()-1;
        int m= s2.length()-1;
        int[][] dp = new int[s1.length()][s2.length()];
        for(int[] item:dp){
            for(int i=0;i<item.length;i++){
                item[i] = -1;
            }
        }
        return helper(dp,s1,s2,n,m);
    }
    static int helper(int[][] dp , String s1 , String s2 ,int i , int j){
        if(i<0 || j<0){
            return 0;
        }
        if(dp[i][j]!=-1){
            return dp[i][j];
        }
        if(s1.charAt(i)==s2.charAt(j)){
            return dp[i][j] = 1 + helper(dp,s1,s2,i-1,j-1);
        }
        else{
            return dp[i][j] = Math.max(helper(dp,s1,s2,i-1,j),helper(dp,s1,s2,i,j-1));
        }
    }
}
```

### Tabulation 
![[Pasted image 20260812234749.png]]
![[Pasted image 20260812234802.png]]

![[Pasted image 20260812234857.png]]