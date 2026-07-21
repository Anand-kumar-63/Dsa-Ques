```java
//package Searching.BinarySerach;  
//  
//import java.util.Scanner;  
//  
//public class CielingProblem {  
//    public static void main(String[] args) {  
//        int[] array = {1,2,3,4,8,10,23,35};  
//        int target = new Scanner(System.in).nextInt();  
//        int Result = FindCeilValue(array , target , 0 , array.length-1);  
//        System.out.println(Result);  
//    }  
//  
//    static int FindCeilValue(int[] array , int target,int start , int end){  
//        int mid = start + (end-start)/2;  
//        if(start<=end){  
//            if(target>array[mid]){  
//               return FindCeilValue(array , target , mid+1,end);  
//            }  
//            else if(target < array[mid]){  
//                return FindCeilValue(array , target , start , mid-1);  
//            }  
//            else{  
//                return mid;  
//            }  
//        }  
//        return array[start];  
//    }}  
package Searching.BinarySerach;  
import java.util.Scanner;  
public class CielingProblem{  
    public static void main(String[] args) {  
        int[] array = {1,3,4,5,7,9,13,14};  
        System.out.println("Enter the target");  
        int target = new Scanner(System.in).nextInt();  
        int start = 0;  
        int end = array.length;  
        int result = FindCielValue(array , target , start , end);  
        System.out.println(result);  
    }  
static int FindCielValue(int[] array , int target , int start , int end){  
  if(array.length == 0){  
      System.out.println("Empty array");  
      return -1;  
  }  
  if(target > array[array.length-1]){  
      return Integer.MIN_VALUE;  
  }  
  while(start<=end){  
      int mid = start + (end-start)/2;  
      if(array[mid] == target){  
          return array[mid];  
      }  
      else if(array[mid]<target){  
          return FindCielValue(array , target , mid+1 , end);  
      }  
      else if(array[mid] > target){  
          return FindCielValue(array , target , start , mid-1);  
      }  
      else {  
          return -1;  
      }  
  }  
return array[start];  
    };  
}
```