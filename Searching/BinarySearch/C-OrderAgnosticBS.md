```java
package Searching.BinarySerach;  
  
public class orderagnosticBS {  
    public static void main(String[] args) {  
        int[] array = {76, 66, 56, 44, 33, 9, 8, 7, 6};  
        int target = 56;  
        int result = FindElement(array, target, 0, array.length - 1);  
        if(result != -1) {  
            System.out.println("Element found at index: " + result);  
        }else{  
            System.out.println("Element not found in the array.");  
        }}  
    static int FindElement(int[] array, int num, int start, int end) {  
        // Determine the order of the array once  
        boolean isAscending = array[start] < array[end];  
        while (start <= end) {  
            // Calculate mid to avoid potential integer overflow  
            int mid = start + (end - start) / 2;  
            if (array[mid] == num) {  
                return mid; // Element found  
            }  
            if (isAscending) {  
                // Logic for ascending array  
                if (num < array[mid]) {  
                    end = mid - 1;  
                } else {  
                    start = mid + 1;  
                }  
            }else{  
                // Logic for descending array  
                if (num > array[mid]) {  
                    end = mid - 1;  
                } else {  
                    start = mid + 1;  
                }}
        }  
     return -1; // Element not found  
    }}
```