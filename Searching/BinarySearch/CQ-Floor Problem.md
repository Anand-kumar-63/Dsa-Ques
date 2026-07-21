```java
// you have given a sorted array and you have to find out  
// the value that is just less than or eqaul to the target  
// value  
// if sorted array is given apply binary sort  
  
package Searching.BinarySerach;  
import javax.script.ScriptContext;  
import java.util.Scanner;  
public class FloorProblem{  
    public static void main(String[] args) {  
        int[] array = {1,3,4,5,7,9,13,14};  
        System.out.println("Enter the target you want to check the value for: ");  
        int target = new Scanner(System.in).nextInt();  
        int start = 0;  
        int end = array.length;  
        int result = FindFloorValue(array , target , start , end);  
        System.out.println(result);  
    }  
    static int FindFloorValue(int[] array , int target , int start , int end){  
        // what if the target element is greater than the largest number itself  
        if(array.length == 0){  
            System.out.println("Empty array");  
            return -1;  
        }  
        if(target > array[array.length-1]){  
            System.out.println("Error ");  
            return -1;  
        }  
        if(target<array[0]){  
            System.out.println("Array out of bound Exception");  
            return Integer.MIN_VALUE;  
        }  
  
        while(start<=end){  
            int mid = start + (end-start)/2;  
            if(array[mid] == target){  
                return array[mid];  
            }  
            else if(array[mid]<target){  
                return FindFloorValue(array , target , mid+1 , end);  
            }  
            else{  
                return FindFloorValue(array , target , start , mid-1);  
            }    
        }  
        return array[end];  
    };  
}
```