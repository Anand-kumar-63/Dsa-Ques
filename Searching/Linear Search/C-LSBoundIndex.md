```java
package Searching;  
  
import java.util.Scanner;  
  
public class LSBoundindex {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        int[] array = new int[8];  
        while (true) {  
            System.out.println("Enter the array elements");  
            for (int i = 0; i < array.length; i++) {  
                array[i] = sc.nextInt();  
            }  
            System.out.println("Enter the number you want to check");  
            int num = sc.nextInt();  
  
            System.out.println("Enter the starting and ending index");  
            int startindex = sc.nextInt();  
            int endIndex = sc.nextInt();  
  
            // returning index  
            int result = linearSearch(array, num , startindex , endIndex);  
            System.out.println(result);  
  
            // returning boolean value  
            boolean result2 = LinearSearch2(array, num , startindex , endIndex);  
            System.out.println(result2);  
  
            // returning the element itself if found  
            int result3 = LinearSearch3(array, num , startindex , endIndex);  
            System.out.println(result3);  
        }  
    }  
  
    // returning the index of the array at the element position  
    static int linearSearch(int[] array, int target , int start , int end) {  
  
        if(start < 0 || end > array.length) {  
            return -1;  
        }  
        // edge case if the array is empty return -1;  
        else if (array.length <= 0) {  
            return -1;  
        } else {  
            int ArrayLength = array.length;  
            for (int i = start; i < end; i++) {  
                if (target == array[i]) {  
                    return i;  
                }  
            }  
        }  
        return -1;  
    }  
  
    // Return Boolean  
    static boolean LinearSearch2(int[] array, int target , int start , int end) {  
  
        if(start < 0 || end > array.length) {  
            return false;  
        }  
        // if array length is 0  
        else if (array.length <= 0) {  
            return false;  
        } else {  
            for (int i = start; i < end; i++) {  
                // if tagret matches the array element then return true  
                if (target == array[i]) {  
                    return true;  
                }  
            }  
        }  
        return false;  
    }  
  
    // return the element if found  
    static int LinearSearch3(int[] array, int num , int start , int end) {  
  
        if(start < 0 || end > array.length) {  
            return -1;  
        }  
        else if (array.length <= 0) {  
            return Integer.MAX_VALUE;  
        } else {  
            for (int i = start; i < end; i++) {  
                if (num == array[i]) {  
                    return num;  
                }  
            }  
        }  
        // returning interger.MAXVALUE because the element itself can be -1;  
        System.out.println(Integer.MAX_VALUE);  
        return Integer.MAX_VALUE;  
    }  
  
}
```