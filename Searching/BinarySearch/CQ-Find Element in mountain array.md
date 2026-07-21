![[Pasted image 20260719150911.png]]
- you have to first find the peak Element 
```java
/**
 * // This is MountainArray's API interface.
 * // You should not implement it, or speculate about its implementation
 * interface MountainArray {
 *     public int get(int index) {}
 *     public int length() {}
 * }
 */
class Solution {
    public int findInMountainArray(int target, MountainArray arr) {
        int peak = findindex(target, arr, 0, arr.length() - 1);
        int start = findstartindex(target, arr, 0, peak);
        int end = findendindex(target, arr, peak + 1, arr.length() - 1);
        if (start == -1) {
            return end;
        } else {
            return start;
        }
    }
    static int findindex(int target, MountainArray arr, int start, int end) {
        int n = arr.length()-1;
        while (start <= end) {
            int mid = (start + end) / 2;
            int midval = arr.get(mid);
            int mid1 = mid>0?arr.get(mid - 1):Integer.MIN_VALUE;
            int mid2 = mid<n?arr.get(mid + 1):Integer.MIN_VALUE;
            if (midval > mid1 && midval > mid2) {
                return mid;
            } else if (midval > mid1 && midval < mid2) {
                start = mid + 1;
            } else {
                end = mid - 1;
            }
        }
        return -1;
    }

    static int findstartindex(int target, MountainArray arr, int start, int end) {
        while (start <= end) {
            int mid = (start + end) / 2;
            int midval = arr.get(mid);
            if (midval == target) {
                return mid;
            } else if (midval > target) {
                end = mid - 1;
            } else {
                start = mid + 1;
            }
        }
        return -1;
    }
    static int findendindex(int target, MountainArray arr, int start, int end) {
        while (start <= end) {
            int mid = (start + end) / 2;
            int midval = arr.get(mid);
            if (midval == target) {
                return mid;
            } else if (midval > target) {
                start = mid + 1;
            } else {
                end = mid - 1;            }
        }
        return -1;

        }    }
```