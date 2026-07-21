```java
package Searching;  
  
import java.util.Scanner;  
  
public class LSString {  
    public static void main(String[] args) {  
        Scanner in = new Scanner(System.in);  
        String str = in.next();  
        char ch = 'v';  
  
        char result = LinearSearch2(str , ch);  
        System.out.println(result);  
  
        char result2 = LinearSearch3(str , ch);  
        System.out.println(result2);  
    }  
    static int LinearSearch(String str, char target) {  
        if (str.length() <= 0) {  
            return -1;  
        } else {  
            for (int i = 0; i < str.length(); i++) {  
                if (target == str.charAt(i)) {  
                    return i;  
                }  
            }  
        }  
        return -1;  
    }  
    static char LinearSearch2(String str, char target) {  
        if (str.length() <= 0) {  
            return Character.MAX_VALUE;  
        } else {  
            for (int i = 0; i < str.length(); i++) {  
                if (target == str.charAt(i)) {  
                    return str.charAt(i);  
                }  
            }  
        }  
        System.out.println(Character.MAX_VALUE);  
        return Character.MAX_VALUE;  
    }  
  
    // using Enhanched for loop  
    static char LinearSearch3(String str, char target) {  
        for (char c : str.toCharArray()) {  
            if (target == c) {  
                return c;  
            }  
        }  
        return Character.MAX_VALUE;  
    }  
  
}
```