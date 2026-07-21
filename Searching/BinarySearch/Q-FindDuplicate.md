```java
// 287. Find the Duplicate Number  
//Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.  
//There is only one repeated number in nums, return this repeated number.  
//You must solve the problem without modifying the array nums and using only constant extra space.  
//Example 1:  
//Input: nums = [1,3,4,2,2]  
//Output: 2  
package Searching.BinarySerach;  
import java.util.Arrays;  
public class Problem287 {  
    public static void main(String[] args) {  
        int[] array = {1,3,4,2,2};  
        Arrays.sort(array);  
        int start = 0;  
        int end = array.length-1;  
        int result = FindDouble(array , start , end);  
        System.out.println(result);  
    }  
    static int FindDouble(int[] array, int start,int end){  
        if(array.length <=0 ){  
            return  Integer.MIN_VALUE;  
        }  
        while(start<=end){  
            int mid = start+(end-start)/2;  
            if( mid<end && mid>0 && array[mid]==array[mid+1] || array[mid]==array[mid-1]){  
                return array[mid];  
            }  
            else {  
                start = mid+1;  
            }  
        }  
        return Integer.MIN_VALUE;  
    }  
}
```