```java
Question7:- Selection Sort 
package Recursion;  
import java.util.Arrays;  
public class SelectionSort {  
    public static void main(String[] args){  
        int[] test = {99,2,9,7,3,4,5,1,12};  
        int[] result = Selection_sort(test , 0 , test.length-1 , 1);  
        System.out.println(Arrays.toString(result));  
    }  
    static int[] Selection_sort(int[] array , int c , int r , int max_index){  
        if(r==0){return array;}  
        if(r>c){  
            if(array[c]>array[max_index]){  
                return Selection_sort( array , c+1 , r , c);  
            }else {  
                return Selection_sort(array , c+1 , r, max_index );  
            }}  
        else{  
            // now swap the thing  
            int temp = array[max_index];  
            array[max_index] = array[r];  
            array[r] = temp;  
            return Selection_sort(array, 0 , r-1 , 0);  
        }}}
```
- first iterate till c reaches r then reduce the r and c = 0;