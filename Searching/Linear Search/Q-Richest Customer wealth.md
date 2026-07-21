```java
package Searching;  
  
import java.util.Scanner;  
  
public class Problem1672 {  
    public static void main(String[] args) {  
        Scanner in = new Scanner(System.in);  
        int[][] accounts= new int[][]{  
                {1, 2, 3},  
                {22, -10},  
                {-10, -9, 40},  
                {18, -3}  
        };  
        int result = findRichest(accounts);  
        System.out.println("The Richest guy has wealth " + result);  
    }  
  
    static int FindRcihest(int[][] accounts) {  
        int[] total = new int[accounts.length];  
        int sum;  
        // Handleing the edge case  
        if (accounts.length < 0) return Integer.MIN_VALUE;  
        else  
        {  
            for (int j = 0; j < accounts.length; j++) {  
                sum = 0;  
                for (int i = 0; i < accounts[j].length; i++) {  
                    sum +=accounts[j][i];  
                    total[j] = sum;  
                }  
            }  
        }  
        int max = Integer.MIN_VALUE;  
        for (int item:total)  
            if (max < item) {  
                max = item;  
            }  
        return max;  
    }  
  
    //More suitable approach  
    static int findRichest(int[][] array){  
        int max = Integer.MIN_VALUE;  
        for(int person=0;person<array.length;person++){  
            int sum = 0;  
            for(int bank = 0 ; bank < array[person].length;bank++){  
                sum += array[person][bank];  
            }  
            // now you have to check it with the minimum value  
            if(sum>max){  
                max = sum;  
            }  
        }  
        return max;  
    }  
}
```