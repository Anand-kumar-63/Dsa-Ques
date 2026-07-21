![[Pasted image 20260717104036.png]]
```
// class Solution {
// 	public static ArrayList<Integer> findUnion(int a[], int b[]) {
// 		// code here
// 		ArrayList<Integer> arr = new ArrayList<>();
// 		HashSet<Integer> set1 = new HashSet<>();
// 		int i = 0;
// 		int j = 0;
// 		while (i<a.length && j<b.length) {
// 			if (a[i] == b[j]) {
// 				if (!set1.contains(a[i])) {
// 					arr.add(a[i]);
// 					set1.add(a[i]);
// 				}
// 				i++;
// 				j++;
// 			}
// 			else if (a[i]>b[j]) {
// 				if (!set1.contains(b[j])) {
// 					arr.add(b[j]);
// 					set1.add(b[j]);
// 				}
// 				j++;
// 			}
// 			else {
// 				if (!set1.contains(a[i])) {
// 					arr.add(a[i]);
// 					set1.add(a[i]);
// 				}
// 				i++;
// 			}
// 		}
// 		if (i != a.length) {
// 			while (i <= a.length - 1) {
// 				if (!set1.contains(a[i])) {
// 					set1.add(a[i]);
// 					arr.add(a[i]);
// 				}
				
// 				i++;
// 			}
// 		} else {
// 			while (j <= b.length - 1) {
// 				if (!set1.contains(b[j])) {
// 					set1.add(b[j]);
// 					arr.add(b[j]);
// 				}
				
// 				j++;
// 			}
// 		}
		
// 		return arr;
// 	}
// }
```
- You have to Check for the particular element in the HashSet first and if not found then add it to the ArrayList and set as well. 
- Then apply two condition as both of them are sorted so if first element greater then second First add in the array then increase the index of the smaller one. 
  and later check if any array elements are left add them too by looping over it and adding it to the ArrayList...x