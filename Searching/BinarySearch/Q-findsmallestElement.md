```java
// you are provided with a letters array that  
// consist of different letters arranged in ascending order  
// you have to find out the least letter greater than the target letter and array  
// contains atleast two distinct letters -- {a,a,b,b,c},{a,b,c,d,e,f,f,g,g}  
package Searching.BinarySerach;  
import java.util.Scanner;  
public class Problem744 {  
    public static void main(String[] args) {  
        char[] array = {'c','f','j'};  
        System.out.println("Enter the Target");  
        String str = new Scanner(System.in).next();  
        char target = str.charAt(0);  
  
        char ch = FindLeastMax(array, target);  
        System.out.println(ch);  
    }  
    static char FindLeastMax(char[] array, char target) {  
        int start = 0;  
        int end = array.length;  
        // checking for < smallest element  
        if ((int) target > (int) array[array.length - 1]) {  
            return array[0];  
        };  
        // checking for > largest element  
        if ((int) target < (int) array[0]) {  
            return array[0];  
        }  
        // checking for empty array  
        if (array.length <= 0) {  
            System.out.println("Empty array");  
            return '$';  
        }  
        while (start <= end) {  
            int mid = start + (end - start) / 2;  
  
            if ((int) target == (int) array[mid]) {  
                if (mid == array.length - 1) {  
                    return array[0];  
                } else {  
                    int i;  
//                    while ((int)array[i] == (int) target) {  
//                        i++;  
//                    }  
                    for(i=mid;i<=array.length-1;i++){  
                        if((int)array[i]==(int)target){  
                            continue;  
                        }  
                        else{  
                            break;  
                        }  
                    }  
                    if (i <= array.length - 1) {  
                        return array[i];  
                    } else {  
                        return array[0];  
                    }  
                }  
            }  
            if ((int) target > (int) array[mid]) {  
                start = mid + 1;  
            } else if ((int) target < (int) array[mid]) {  
                end = mid - 1;  
            } else {  
                return array[0];  
            }  
        }  
        return array[start];  
    }  
}
```