![[Pasted image 20260718205708.png]]
```java
class Solution {
    ArrayList<Integer> find(int arr[], int target) {
        // code here
        int n = arr.length;
		int start = 0;
		int end = n - 1;
		ArrayList<Integer>  ans = new ArrayList<>();
		while (start <= end) {
			
			int mid = (start + end)/2;
			
			if (arr[mid] == target) {
				
				int i = mid;
				int j = mid;
				
				while(i>0 && arr[i-1]==target || j<n-1 && arr[j+1]==target ) {
				    
					if (i>0 && arr[i-1] == target && arr[j+1] == target) {
						i--;
						j++;
					}
					else if (j<n-1 && arr[j+1] == target) {
						j++;
					}else if(i>0 && arr[i-1]==target){
					    i--;
					}
				}
				ans.add(i);
				ans.add(j);
				return ans;
			} 
			
			else if (arr[mid]<target) {
				start = mid + 1;
			}
			else {
				end = mid - 1;
			}
		}
		ArrayList<Integer>  def = new ArrayList<>();
		def.add(-1);
		def.add(-1);
		return def;
    }
}

```
### Method-2 
- You have to first Find the  first occurence then for the first index end  = mid-1 and for the end end index start= mid+1;
![[Pasted image 20260718205930.png]]
![[Pasted image 20260718211350.png]]
![[Pasted image 20260718211320.png]]