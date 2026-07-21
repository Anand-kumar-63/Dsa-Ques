## find Ascii values 
```java
static void ascii(char ch){  
    System.out.println(ch+0);   
}
```

## Convert String to int
```java
// `Integer.parseInt()`, `Double.parseDouble()` , or `Long.parseLong()`
   int s = Integer.parseInt(String s);
// if the input is way too long that it cannot be handled by int or even long
import java.math.BigInteger;
   // convert the binary string into decimal
   BigInteger a1 = new BigInteger(a, 2);
   BigInteger b1 = new BigInteger(b, 2);
   // it doesn't support normal sum  
   BigInteger sum = a1.add(b1);
   return sum.toString(2);
```
## add without using add or sub operator using binary operators
```java
public int getSum(int a, int b) {
       while (b != 0) {
            int carry = (a & b) << 1;  // carry
            a = a ^ b;                // sum without carry
            b = carry;               // add carry in next step
        }
        return a;  
    }
```

### convert an int to an array of its digits
- String using 
```java
int num = 12345;
String s = String.valueOf(num);
int[] digits = new int[s.length()];
for (int i = 0; i < s.length(); i++) {
    digits[i] = s.charAt(i) - '0';
}
for (int d : digits) {
    System.out.print(d + " ");
}
```
- using remainder
```java
int num = 1236;
int count = 0;
while(num!=0){
  count++;
  num =/ 10;
}
int[] arr = new int[];
for(int i=arr.length-1;i>=0;i--){
  arr[i] = num&10;
  num = num/10;
}
```

### using priority Queue to kind the kth smallest element
```java
class Solution {
	public int kthSmallest(int[] arr, int k) {
		// Code here
		PriorityQueue<Integer> pq = new PriorityQueue<>();
		for (int x : arr) {
			pq.offer(x);
		}
		
		while(k>1){
		    pq.poll();
		    k--;
		}
		return pq.peek();
	}
}

```

### Use matrix binary search to find the kth smallest Element
```
Binary search can be done on the index if the Whole Array is Sorted gloabally
or on the elements present in the matrix by findind mid and compairing the value
```

### if sorted array is given then apply Binary Search
```

```

### if somewhere smaller than target lesser than target find out krna hai to binary search

### If You Have Infinite Array then how to find the last index 
  int s =0;
  int e  = 1;
compare target > arr[e]
  int ns=s;
  int s = e+1;
  e = (e-s+1) * 2 // every time increase the last index by 2 times

### Binary search peak left right
