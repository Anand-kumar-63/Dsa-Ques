![[Pasted image 20260710122933.png]]
### Napsack using Tabulation - 
```
weights = [1,3,4,5]
values = [1,4,5,7]
capacity W = 7
```
Maximum profit using first `i` items when bag capacity is `j`.
```
I/W 0 1 2 3 4 5 6 7
0       
1
2
3
4
```
Rows = items
Columns = capacity of bag
Example:
```
dp[3][5]
```
Means :- 
using first 3 items:
```
(1,3,4)
```
with capacity:
```
5
```
what is max profit?


