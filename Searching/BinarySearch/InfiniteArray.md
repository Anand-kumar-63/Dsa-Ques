```java
// find the target in the infinite sorted array as it is infinite array you cannot use array.length to find out the length of the array  
package Searching.BinarySerach;  
  
import java.util.Scanner;  
  
public class infiniteArray {  
    public static void main(String[] args) {  
        int[] array = {1,2,3,4,4,5,5,6,6,6,7,7,7,7,8,8,8,9,10,11,12};  
        System.out.println("Enter the target");  
        int target = new Scanner(System.in).nextInt();  
  
        int start = 0;  
        int end = 1;  
        while(target>array[end]){  
            int newstart = start;  
            start = end+1;  
            end = end + ((end-newstart)+1)*2;  
        }  
        int result = Findtarget(array, target , start , end);  
        System.out.println(result);  
    }  
  static int Findtarget(int[] array , int target , int start , int end){  
    while(start<=end){  
        int mid = start+(end-start)/2;  
        if(target>array[mid]){  
            return Findtarget(array, target , mid+1,end);  
        }  
        else if(target<array[mid]){  
            return Findtarget(array, target , start,mid-1);  
        }  
        else {  
            return mid;  
        }  
    }  
    return -1;  
  };}
```