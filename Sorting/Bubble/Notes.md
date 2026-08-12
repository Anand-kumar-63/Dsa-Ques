- Bubble Sort
```
package Sorting;  
import java.util.Arrays;   
public class bbl {  
    public static void main(String[] args) {  
        int[] arr = {9,7,4,-1,-16,0,3,2,7,1};  
        int n = arr.length;  
        for(int i=1; i<=n-1; i++){ // outer passes will be n-1  
            for(int j=0;j<n-i;j++){ // reduce the size of the array every singe time  
                if(arr[j]>arr[j+1]){  
                    int temp = arr[j];  
                    arr[j] = arr[j+1];  
                    arr[j+1] = temp;  
                }  
            }  
        }  
        System.out.println(Arrays.toString(arr));  
    }  
}

TC - o(n^2)

```

- Better Version we are handling if the Remaining Array is Sorted. 
```
import java.util.Arrays;  
  
public class bbl {  
    public static void main(String[] args) {  
        int[] arr = {7,1,2,3,4,5,6};   
        int n = arr.length;  
        for(int i=1; i<=n-1; i++){ // outer passes will be n-1  
            int swap = 0;  
            for(int j=0;j<n-i;j++){ // reduce the size of the array every singe time  
                if(arr[j]>arr[j+1]){  
                    swap++;  
                    int temp = arr[j];  
                    arr[j] = arr[j+1];  
                    arr[j+1] = temp;  
                }  
            }  
	            if(swap==0)break;  
        }  
        System.out.println(Arrays.toString(arr));  
    }  
}

{7,1,2,3,4,5,6}; 
TC - o(n) for best case
```