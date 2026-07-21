![[Pasted image 20260716151627.png]]
```
class Solution {
    public int[] findIntersectionValues(int[] arr1, int[] arr2) {
        int[] ans = new int[2];
        int count = 0;
        int i = 0;
        int j = 0;
        while (i <= arr1.length - 1){
            if (arr1[i] == arr2[j]) {
                count++;
                i++;
                j = 0;
            }
            else if(j==arr2.length-1){
                j=0;
                i++;
            }
            else{
            j++;
            }
        }
        ans[0]=count;
        count = 0;
        i = 0;
        j = 0;
        while (j <= arr2.length - 1) {
            if (arr1[i] == arr2[j]) {
                count++;
                j++;
                i = 0;
            }
            else if(i==arr1.length-1){
                i=0;
                j++;
            }
            else{
            i++;
            }
        }
        ans[1]=count;
        return ans;
        // int[] ans = new int[2];
        // int count = 0;
        // for(int i=0;i<arr1.length;i++){
        //     for(int j = 0;j<arr2.length;j++){
        //       if(arr1[i]==arr2[j]){
        //         count++;
        //         break;
        //       }
        //     }
        // }
        // ans[0] = count;
        // count = 0;
        // for(int i=0; i<arr2.length; i++){
        //     for(int j = 0; j<arr1.length; j++){
        //       if(arr1[j] == arr2[i]){
        //         count++;
        //         break;
        //       }
        //     }
        // }
        // ans[1] = count;
        // return ans;
    }
    
}
```