Note - https://www.youtube.com/watch?v=ILZeLFgLlQM
one of the major use of prefix sum is finding sum of Sub Array
```java
int[] ps = new int[n];
for(int i=0;i<n;i++){
  ps[i] = ps[i] + cs;
  cs = cs+ps[i];
}
arr -
1,2,3,4,5
ps -
1,3,6,10,15
```

### Equilibrium point
- Simply use Prefix sum and Suffix sum 
- when both prefix and suffix sum are equal then you can return that index
![[Pasted image 20260525033532.png]]
![[Pasted image 20260525033546.png]]

### Equal left and equal right sub problem
![[Pasted image 20260525155648.png]]
![[Pasted image 20260525155656.png]]
- Input can be [0,0,0,0,0] so for this OP - 0
### Average of Prefix 
![[Pasted image 20260525161334.png]]

