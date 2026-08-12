![[Pasted image 20260812185835.png]]
```java
class Solution {

    public int countSubstrings(String s) {

        int count = 0;

        int[][] dp = new int[s.length()][s.length()];

        for(int[] arr:dp){

            Arrays.fill(arr,-1);

        }

        // int ans2 = findsub2(0,s.length()-1,s);

        // for(int i=0;i<s.length();i++){

        //     for(int j=i;j<s.length();j++){

        //             if(helper(dp,i,j,s)){

        //               count++;

        //           }

        //     }

        // }

       for(int i=0;i<s.length();i++){

        for(int j=i;j<s.length();j++){

             if((j-i)==0){

               dp[i][j] = 1;

               count++;

             }

             else if((j-i)==1){

                if(s.charAt(i)==s.charAt(j)){

                    dp[i][j] = 1;

                    count++;

                }

                else{

                    dp[i][j]=0;

                }

             }

             else{

                 if(s.charAt(i)==s.charAt(j)){

                   if(helper(dp,i+1,j-1,s)){

                    count++;

                   }  

                 }        

             }

         }

       }

        return count;

    }

    static boolean helper(int[][] dp,int i , int j , String s){

             if(i>j){

                return true;

             }

             if(dp[i][j]!=-1){

                return dp[i][j]==1?true:false;

             }

             if(s.charAt(i)==s.charAt(j)){

                boolean ret = helper(dp,i+1,j-1,s);

                dp[i][j] = ret==true?1:0;

                return ret;

             }

             dp[i][j] = 0;

             return false;

    }

    // static boolean helper(int[][] dp , int i , int j , String s){

    //        if(i>j){

    //         return true;

    //        }

    //        if(dp[i][j]!=-1){

    //           return dp[i][j]==1?true:false;

    //        }

    //        if(s.charAt(i)==s.charAt(j)){

    //           boolean ret = helper(dp,i+1,j-1,s);

    //           dp[i][j] = ret==true?1:0;

    //           return ret;

    //        }

    //        dp[i][j] = 0;

    //        return false;

    // }

    // static int findsub(int i, int j, String s){

    //   if(j==s.length()){

    //     return 0;

    //   }

    //   if(s.charAt(i)!=s.charAt(j)){

    //      i = j;

    //      return findsub(i,j+1,s);

    //   }

    //   else{

    //     int count = 0;

    //     if(j-i>1){

    //       count++;

    //     }

    //     return 1 + findsub(i+1,j-1,s) + count;

    //   }

    // }

    // static int findsub2(int i , int j , String s){

    //     if(s.charAt(i)==s.charAt(j)){

  

    //     }

    // }

}
```