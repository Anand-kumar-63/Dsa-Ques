![[Pasted image 20260718144702.png]]

```
package Searching.BinarySerach;  
import java.util.Arrays;  
import java.util.Scanner;  
  
public class Binary {  
    public static void main(String[] args) {  
        Scanner in = new Scanner(System.in);  
        int[] binaryarray = {1, 2, 3, 4, 5, 6, 7, 8, 10, 11};  
        Arrays.sort(binaryarray);  
        System.out.println("Enter the element you want to Search using binary approach");  
        int num = in.nextInt();  
        int result = findbinary(binaryarray, num, 0, 10);  
        System.out.println("The index at which element is found is :" + result);  
    }  
    static int findbinary(int[] array, int target, int start, int end) {  
        if (array.length == 0) {  
            System.out.println("Array is empty");  
            return -1;  
        }  
        if(start<=end){  
        int mid = (start + end) / 2;  
  
        if (target == array[mid]) {  
            System.out.println("Element found at index " + mid);  
            return mid;  
        }  
        else if(target > array[mid]) {  
               return findbinary(array, target, mid + 1, end);  
        }  
        else{  
              return findbinary(array, target, start, mid - 1);  
        }}  
        return -1;  
    }}
```

### Why binary Search
![[Pasted image 20260718145450.png]]
![[Pasted image 20260718145506.png]]
![[Pasted image 20260718145538.png]]
- K is the total number of levels - log(n)
- Total Comparisions in worst case is Log(N)