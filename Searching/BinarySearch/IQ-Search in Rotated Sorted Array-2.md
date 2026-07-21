```java
// class Solution {

//     public boolean search(int[] arr, int target) {

//         if (arr.length == 1) {

//             return arr[0] == target;

//         }

//         int pvt = pivot(arr);

//         if (pvt == -1) {

//             boolean ans = false;

//             for (int i = 0; i < arr.length; i++){

//                 if(arr[i]==target){

//                       ans = true;  

//                 }

//             }

//             return ans;

//         }

//         if (pvt != -1 && arr[pvt] == target) {

//             return true;

//         }

//         boolean start = findtarget(arr, target, 0, pvt - 1);

//         boolean end = findtarget(arr, target, pvt + 1, arr.length - 1);

//         return start ? start : end;

//     }

  

//     static int pivot(int[] arr) {

//         int n = arr.length;

//         int start = 0;

//         int end = n - 1;

//         while (start <= end) {

//             int mid = (start + end) / 2;

//             if (mid < n - 1 && arr[mid] > arr[mid + 1]) {

//                 return mid;

//             } else if (mid > 0 && arr[mid] < arr[mid - 1]) {

//                 return mid - 1;

//             }

//             //

//             else if (arr[mid] == arr[start] && arr[mid] == arr[end]) {

//                 if (start<n-1 && arr[start] > arr[start + 1])

//                     return start;

//                 start++;

//                 if (end>0 && arr[end] > arr[end - 1])

//                     return end;

//                 end--;

//             }

//             // If left is sorted then Pviot should be on the Right Side..

//             else if (arr[mid] > arr[start] || arr[mid] == arr[start] && arr[mid] > arr[end]) {

//                 start = mid + 1;

//             } else {

//                 end = mid - 1;

//             }

//         }

//         return -1;

//     }

  

//     static Boolean findtarget(int[] arr, int target, int start, int end) {

//         while (start <= end) {

//             int mid = (start + end) / 2;

//             if (target == arr[mid]) {

//                 return true;

//             } else if (target < arr[mid]) {

//                 end = mid - 1;

//             } else {

//                 start = mid + 1;

//             }

//         }

//         return false;

//     }

// }

class Solution {

    public boolean search(int[] nums, int target) {

        int start = 0;

        int end = nums.length - 1;

        while (start <= end) {

            int mid = start + (end - start) / 2;

            if (nums[mid] == target) {

                return true;

            }

             // If we cannot determine which half is sorted

            if (nums[start] == nums[mid] && nums[mid] == nums[end]) {

                start++;

                end--;

            }

            // Left half is sorted

            else if (nums[start] <= nums[mid]) {

                if (target >= nums[start] && target < nums[mid]) {

                    end = mid - 1;

                } else {

                    start = mid + 1;

                }

            }

            // Right half is sorted

            else {

                if (target > nums[mid] && target <= nums[end]) {

                    start = mid + 1;

                } else {

                    end = mid - 1;

                }

            }

        }

        return false;

    }

}
```