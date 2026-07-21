```java
package Searching.BinarySerach;  
  
import java.util.Scanner;  
  
public class descedingBS {  
    public static void main(String[] args) {  
        Scanner in = new Scanner(System.in);  
        int[] binaryarray = {190, 180, 170, 66, 65, 54, 44, 34, 3, 2, 1};  
        System.out.println("Enter the element you want to Search using binary approach");  
        int num = in.nextInt();  
        int result = findbinary(binaryarray, num, 0, 10);  
        System.out.println("The index at which element is found is :" + result);  
    }  
  
    static int findbinary(int[] array, int target, int start, int end) {  
        if (start <= end) {  
            int mid = (start + end) / 2;  
            if (target > array[mid]) { // go to left ;;  
                return findbinary(array, target, start, mid - 1);  
            } else if (target < array[mid]) { // go to right;;  
                return findbinary(array, target, mid + 1, end);  
            } else {  
                System.out.println("Element found at index " + mid);  
                return mid;  
            }  
        }  
        return -1;  
    }  
}
```