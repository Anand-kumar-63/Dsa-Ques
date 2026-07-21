## Rotate an array
### Left rotation-
```
Input:[1,2,3,4,5,6,7]
k = 3
Output:[4,5,6,7,1,2,3]
# Logic of Left Rotation
Split array into 2 parts:
A = first k elements
B = remaining elements
```
Steps:
1. Reverse A
2. Reverse B
3. Reverse whole array
```
import java.util.*;
public class Main {
    static void reverse(int[] arr, int start, int end) {
        while(start < end) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;

            start++;
            end--;
        }}
    static void leftRotate(int[] arr, int k) {
        int n = arr.length;
        k = k % n;
        // Reverse first k elements
        reverse(arr, 0, k - 1);
        // Reverse remaining elements
        reverse(arr, k, n - 1);
        // Reverse complete array
        reverse(arr, 0, n - 1);
    }
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5,6,7};
        leftRotate(arr, 3);
        System.out.println(Arrays.toString(arr));
    }
}
```


### Right rotation
#### Logic of Right Rotation
Steps:
1. Reverse whole array
2. Reverse first k elements
3. Reverse remaining elements
```
import java.util.*;
public class Main {
    static void reverse(int[] arr, int start, int end) {
        while(start < end) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            start++;
            end--;
        }
    }
    static void rightRotate(int[] arr, int k) {
        int n = arr.length;
        k = k % n;
        // Reverse whole array
        reverse(arr, 0, n - 1);
        // Reverse first k elements
        reverse(arr, 0, k - 1);
        // Reverse remaining elements
        reverse(arr, k, n - 1);
    }
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5,6,7};
        rightRotate(arr, 3);
        System.out.println(Arrays.toString(arr));
    }
}
```

### Subarray
```java
public class subArray {  
    public static void main(String[] args){  
        int[] arr = {1,3,4,2,4,6,7,9};  
        printsubarray(arr);  
    }  
    static void printsubarray(int[] arr){  
        int n = arr.length;  
        for(int i=0;i<n;i++){  
            for(int j=i;j<n;j++){  
                for(int k=i;k<=j;k++){  
                    System.out.print(arr[k]);  
                }  
                System.out.print(" ");  
            }  
            System.out.println("");  
        }  
    }  
}
tc - o(n^3)
```
Output-
![[Pasted image 20260525145832.png]]

### Find Subarray Sum
![[Pasted image 20260525150529.png]]