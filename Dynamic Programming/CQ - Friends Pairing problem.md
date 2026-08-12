![[Pasted image 20260809172619.png]]
![[Pasted image 20260809173829.png]]
![[Pasted image 20260809172524.png]]
```java
class Solution {
    public int countFriendsPairings(int n) {
     if(n<=2) return n;
     // if a gets alone then arrangements of n-1 elememts and if a gets paired   with anyone then its arrangements with n-2 elements
     return countFriendsPairings(n-1) + (n-1)*countFriendsPairings(n-2);
}}

```