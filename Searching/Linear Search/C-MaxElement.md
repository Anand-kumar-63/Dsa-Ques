```java
package Searching;  
  
import java.util.Scanner;  
  
public class MAXelement {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        int[] arr = {1,2,34,-5,-7,90,3,5};  
        int result = Findmax(arr);  
        System.out.println("The minimum element in the Array is : "+result);  
    }  
    // assume it to be a non-empty array  
    static int Findmax(int[] array){  
      int min = array[0];  
      for(int num:array){  
          if(num<min){  
              min = num;  
          }  
      }  
     return min;  
    }  
}
```