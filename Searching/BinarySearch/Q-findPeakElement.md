```java
//A peak element is an element that is strictly greater than its neighbors.  
//Given a 0-indexed integer array nums, find a peak element, and return its index.  
 // If the array contains multiple peaks, return the index to any of the peaks.//You may imagine that nums[-1] = nums[n] = -∞. In other words, an element is always  
// considered to be strictly greater than a neighbor that is outside the array.  
//You must write an algorithm that runs in O(log n) time.  
  
//Example 1:  
//Input: nums = [1,2,3,1]  
//Output: 2  
//Explanation: 3 is a peak element and your function should return the index number 2.  
package Searching.BinarySerach;  
public class FindPeakElement162 {  
    public static void main(String[] args) {  
        int[] array = {1,2,3,4,5};  
        int result = FindPeakElement(array);  
        System.out.println(result);  
    }  
    static int FindPeakElement(int[] array){  
        int start = 0;  
        int size = array.length;  
        int end = size-1;  
        if(array.length<=1){  
            return 0;  
        }  
        while(start <= end) {  
            int mid = start + (end - start) / 2;  
            // you have to check the edge case where your mid can be 0  
            if(mid==0){  
                // if mid index at 0 is and element is greater than  
                // element at mid+1 in this case you have to retunr the element at index 0 , only 2 element                // mountain array will exist                if(array[mid] > array[mid+1]){  
                    return mid;  
                }  
                return mid+1;  
            }  
            else if(mid==size-1){  
                // if mid index is at size-1 and the element at last index is greatest than  
                // you have to return the element at last index otherwise the element at index less then last                if(array[mid]>array[mid-1]){  
                    return mid;  
                }  
                return mid-1;  
            }  
            else if(mid>0 && (mid<size-1) && (array[mid] > array[mid-1]) && (array[mid] > array[mid+1])){  
                return mid;  
            }  
            else if (mid > 0  && mid<size-1 && array[mid] < array[mid - 1] && array[mid] > array[mid+1]) {  
                end = mid-1;  
            } else if (mid  >0  && mid<size-1  &&array[mid] > array[mid - 1] && array[mid] < array[mid+1]) {  
                start = mid + 1;  
            }else if(array[mid]<array[mid-1]&& array[mid]<array[mid+1]){  
                end = mid-1;  
            }  
        }  
        return 0;  
    }  
}
```