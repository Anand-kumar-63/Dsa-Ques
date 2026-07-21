- Array is divided into two one is sorted and another is Unsorted Array
- i = j
- while(j>0){
     compare the j-1 and j element
     if smaller then swap if not then break
     }
- It is stable algorithm of sorting 
```
import java.util.Arrays;
class Main {
    public static void main(String[] args) {
      int[] arr = {7,8,6,-1,0,87,54,30};
      int j;
      for(int i =1;i<arr.length;i++){
          j = i;
          while(j>0){
              if(arr[j-1]>arr[j]){
               swap(arr , j-1 , j);
               j--;
              }else{
                  break;
              }
          }
      }
      System.out.println(Arrays.toString(arr));
    }
    static void swap(int[] arr, int i , int j){
        int temp = arr[j];
        arr[j] = arr[i];
        arr[i] = temp;
    }
}
```
![[Pasted image 20260718134432.png]]
![[Pasted image 20260718134505.png]]
