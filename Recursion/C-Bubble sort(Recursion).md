```java
package Recursion;  
import java.util.Arrays;  
// Bubble Sort Using Recursion col and row approach public class Bubblesort2 {  
public static void main(String[] args){  
  int[] test = {10,9,8,7,6,5,4,3,2,1};  
  int[] result = Bubble_sort(test , 0 , test.length-1);  
  System.out.println(Arrays.toString(result));  
}  
static int[] Bubble_sort(int[] array , int c, int r){  
    if(r==0){  
        return array;}  
    if(r>c){  
        if(array[c]>array[c+1]){  
            int temp = array[c];  
            array[c] = array[c+1];  
            array[c+1] = temp;  
        }  
       return Bubble_sort(array,c+1,r);}  
    else {  return Bubble_sort(array , 0  , r-1);  }}  
}
```