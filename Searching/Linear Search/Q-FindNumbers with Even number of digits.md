```java
  
//using Remainder method and linear search  
  
package Searching;  
import java.util.Scanner;  
public class Problemno1295 {  
    public static void main(String[] args) {  
        Scanner in = new Scanner(System.in);  
        int[] array = {12, 233, 3587, 411, 5000, 1, 23309};  
//        int Result = findNumbers(array);  
//        System.out.println("Total number of elements contains Two digits are "+Result);  
        int result = Finddigits(81264892);  
        System.out.println("Number of digits in the number "+result);  
    }  
    static int findNumbers(int[] nums) {  
        int count = 0;  
        int Numbercount = 0;  
        for (int item : nums) {  
            // handeling the case when number is -ve  
            if(item<0){  
                item *= -1;  
            }  
            count = 0;  
            while (item > 0) {  
                if (item % 10 >= 0) {  
                    count++;  
                }  
                item /= 10;  
            }  
            if(count%2==0) Numbercount++;  
        }  
        return Numbercount;  
    }  
  
    // method to find number of digits  
    static int Finddigits(int num){  
        if(num<0){  
            num *= -1;  
        }  
        return (int)(Math.log10(num)+1);  
    }  
}
```