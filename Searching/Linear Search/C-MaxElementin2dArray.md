```java
package Searching;  
import java.util.Scanner;  
public class MAXelement2Darray {  
    public static void main(String[] args) {  
        int[][] array = {{1, 2, 33}, {44, 53, -3}, {-9, 10, 9}};  
        int Result = MAXELEMENT(array);  
        int Result2 = MINElement(array);  
        System.out.println(Result2);  
        System.out.println(Result);  
    }  
    static int MAXELEMENT(int[][] array) {  
        //check for empty array  
         if(array.length<=0){  
             System.out.println("Array has no element");  
             return Integer.MAX_VALUE;  
         }  
        int max = array[0][0];  
        if (array.length <= 0) {  
            System.out.println("Array is empty");  
            return Integer.MAX_VALUE;  
        } else {  
            for (int[] arr:array) {  
                for (int item:arr) {  
                    if (item > max) {  
                        max = item;  
                     }}}}  
        return max;  
    };  
static int MINElement(int[][] array ){  
  // check for empty array  
    if(array.length<=0){  
        System.out.println("Array has no elements");  
        return Integer.MIN_VALUE;  
    }  
    int min = array[0][0];  
    System.out.println(min);  
    for(int[] arr:array){  
        for(int item:arr){  
            if(item<min){  
                min = item;  
            }  
        }  
    }  
    return min;  
};  
}
```