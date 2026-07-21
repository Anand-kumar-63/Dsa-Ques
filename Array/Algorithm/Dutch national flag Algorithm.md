The **Dutch National Flag Algorithm** is used to sort an array containing only:0s, 1s, and 2s
in a **single traversal**.
problem 
IP -
[2,0,2,1,1,0]
OP -
[0,0,1,1,2,2]
### Use 3 pointers:

| Pointer | Meaning               |
| ------- | --------------------- |
| `low`   | position for next `0` |
| `mid`   | current element       |
| `high`  | position for next `2` |

```
0 → low  
0 → mid  
n-1 → high 

The goal is to arrange elements into three partitions: without using traditional sorting algorithms like Bubble Sort or Merge Sort.

0 to low-1 → 0s  
low to mid-1 → 1s  
mid to high → unknown  
high+1 to end → 2s
```
## Algorithm Logic
The algorithm processes elements one by one:
#### Case 1: mid is `0`
- Swap it with the element at `low`
- Increment both `low` and `mid`
Reason:
```
0 belongs to left side
```
#### Case 2: mid is `1`
- Leave it in the middle
- Increment `mid`
Reason:
```
1 is already in correct partition 
```
#### Case 3: mid is `2`
- Swap it with the element at `high`
- Decrement `high`
Reason:
```
2 belongs to right side
```
`mid` is not incremented immediately because the swapped element must still be checked.
 
![[Pasted image 20260526153727.png]]

![[Pasted image 20260526153714.png]]
