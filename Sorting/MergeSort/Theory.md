![[Pasted image 20260805185300.png]]
![[Pasted image 20260806225448.png]]

```java
import java.util.Arrays;
public class Main {
    public static void main(String[] args) {
        int[] arr = {3, 4, 8, 1, 2, -1, 0, 78, 67, -10};
        arr = mergesort(arr);
        System.out.println(Arrays.toString(arr));
    }
    static int[] mergesort(int[] arr) {
        if (arr.length <= 1) {
            return arr;
        }
        int n = arr.length;
        int[] a = new int[n / 2];
        int[] b = new int[n - n / 2];
        int idx = 0;
        for (int i = 0; i < n / 2; i++) {
            a[i] = arr[idx++];
        }
        for (int i = 0; i < b.length; i++) {
            b[i] = arr[idx++];
        }
        a = mergesort(a);
        b = mergesort(b);
        return merge(a, b, arr);
    }
    static int[] merge(int[] a, int[] b, int[] arr) {
        int i = 0;
        int j = 0;
        int k = 0;
        while (i < a.length && j < b.length) {
            if (a[i] < b[j]) {
                arr[k++] = a[i++];
            } else {
                arr[k++] = b[j++];
            }
        }
        while (i < a.length) {
            arr[k++] = a[i++];
        }
        while (j < b.length) {
            arr[k++] = b[j++];
        }
        return arr;
    }}
```
## Method-2
![[Pasted image 20260806232716.png]]

### Inplace 
![[Pasted image 20260806234617.png]]
### TC
![[Pasted image 20260806233055.png]]
- At Every Level there are total (n-1) Comparisions and total number of levels are logn
- so TC  - NlogN