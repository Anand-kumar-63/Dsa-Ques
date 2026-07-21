- Select the largest element and swap it with the last Element.
- TC  - O(n^2) Best , Avg , Worst.
- Passes will be (Length - 1).
![[Pasted image 20260716132617.png]]
- In bubble sort as we are Swapping the Adjacent Element we are Indirectly sorting the smaller segments. that why the bubble sort is faster 
- 
```
package Sorting.SelectionSort;  
  
import java.util.Arrays;  
  
public class Selection {  
    public static void main(String[] args) {  
        int[] arr = {29,9,7,45,12,3,42,1};  
        int n = arr.length;  
        
        for(int i=0;i<n-1;i++){ // no of passes  
            int max = 0;  // this is the initial index for the max element 
            for(int j=1; j<n-i; j++){  // now compare the max element
                if(arr[j]>arr[max]){  
                    max = j;  // change the index
                }  
            }  
            // now swap the max element with the last index
            int temp = arr[max];  
            arr[max] = arr[n-1-i];  
            arr[n-1-i] = temp;  
        }  
        System.out.println(Arrays.toString(arr));  
    }  
}
```

