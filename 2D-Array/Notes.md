### Basic Questions
## 
![[Pasted image 20260714151145.png]]

## print column wise
![[Pasted image 20260714151124.png]]
![[Pasted image 20260714151725.png]]
## Print snake pattern
```
import java.util.*;  
public class snakepattern {  
    public static void main(String[] args){  
        int[][] arr = {{1,2,3,4},{2,3,4,5},{5,6,7,8},{8,35,5,6}};  
        int i =0;  
        int j =0;  
        int n = arr[0].length-1;  
        for(i=0;i<arr.length;i++) {  
            if (j == n+1) {  
                for (j = n; j >= 0; j--) {  
                    System.out.print(arr[i][j] + " ");  
                }  
            } else {  
                for (j = 0; j < arr[0].length; j++) {  
                    System.out.print(arr[i][j] + " ");  
                }  
            }  
            System.out.println(" ");  
        }  
    }  
}
```

## Snake print column wise
```
import java.util.*;  
public class snakeColumnwise {  
    public static void main(String[] args) {  
        int[][] arr = {{1,2,3,4},{5,6,7,8},{9,8,7,6},{4,7,5,6}};  
        int i =0;  
        int j =0;  
        for(j=0;j<arr[0].length;j++) {  
            if (i == 0) {  
                for (i = 0; i < arr.length; i++) {  
                    System.out.print(arr[i][j] + " ");  
                }  
            } else {  
                for (i = arr.length - 1; i >= 0; i--) {  
                    System.out.print(arr[i][j] + " ");  
                }  
            }  
            System.out.println(" ");  
        }  
    }  
}
```

## Reverse the rows of the matrix
```
import java.util.*;  
public class reverseMTRXrows {  
    public static void main(String[] args) {  
           int[][] arr = {{1,2,4,5},{3,5,6,7},{5,6,7,8}};  
           for(int i=0; i<arr.length; i++){  
               int s = 0;  
               int e = arr[0].length-1;  
               int j = 0;  
               while(s<e && j<=arr[0].length/2){  
                   int temp = arr[i][s];  
                   arr[i][s] = arr[i][e];  
                   arr[i][e] = temp;  
                   s++;  
                   e--;  
                   j++;  
               }  
           }  
           for(int[] a:arr){  
            System.out.println(Arrays.toString(a));  
           }  
    }  
}
```

## Matrix transpose
```java
import java.util.Arrays;  
  
public class transposematrix {  
    public static void main(String[] args) {  
        int[][] arr = {{1,2,3,4},{5,6,7,8},{8,9,7,5},{24,214,66,7}};  
        for(int[] a:arr){  
            System.out.println(Arrays.toString(a));  
        }  
        for(int i=0; i<arr.length; i++){  
            for(int j=0; j<=i; j++){  
                if(i!=j){  
                    int temp = arr[i][j];  
                    arr[i][j] = arr[j][i];  
                    arr[j][i] = temp;  
                }else{  
                    continue;  
                }  
            }  
        }  
        System.out.println(" ");  
        for(int[] a:arr){  
         System.out.println(Arrays.toString(a));  
       }  
    }  
}
```
![[Pasted image 20260714165657.png]]

#### another solution
![[Pasted image 20260714170655.png]]