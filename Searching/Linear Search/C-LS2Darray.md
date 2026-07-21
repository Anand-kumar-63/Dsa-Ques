```java
package Searching;  
import java.util.Scanner;  
public class LS2Darray {  
    public static void main(String[] args) {  
        Scanner in = new Scanner(System.in);  
        int[][] array = {  
                {1,23,4,5},  
                {7,78,9,6},  
                {23,45},  
                {1}  
        };  
        System.out.println("Enter the Element you want to search");  
        int target = in.nextInt();  
        TwoDfind(array , target);  
    }  
    static int[] TwoDfind(int[][] array , int target){  
        // edge case if the Arrays length is zero or not  
        if(array.length<=0){  
            System.out.println("Array having zero values");  
            return new int[0];  
        }  
        else {  
            int rows = array.length;  
            for(int i=0;i<array.length;i++){ // for loop for every index of the array  
                for (int j =0;j<array[i].length;j++){ // since every element at index  
                                                      // is the array itself...                    if(target == array[i][j]){  
                        System.out.println("Element Found at index i and j "+i+" "+j);  
                        return new int[]{i,j};  
                    }}  
            }}  
        return new int[0];  
    }  
}
```