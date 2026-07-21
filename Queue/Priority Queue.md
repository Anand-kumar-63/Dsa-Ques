![[Pasted image 20260501185513.png]]
## Types of Priority Queue
 **Max Priority Queue**
    - Element with **highest value** has highest priority
    - Example: `[10, 5, 20] → 20 removed first`
 **Min Priority Queue**
    - Element with **lowest value** has highest priority
    - Example: `[10, 5, 20] → 5 removed first`
### Common Operations -
![[Pasted image 20260426211745.png]]
## Implementation (Binary Heap)
Priority queues are usually implemented using a **heap**:
- Min Heap → for min priority queue
- Max Heap → for max priority queue
```java
import java.util.*;
public class Main {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        pq.add(10);
        pq.add(5);
        pq.add(20);
        System.out.println(pq.peek()); // 5
        while (!pq.isEmpty()) {
            System.out.println(pq.poll());
        }}}
```
``` java
// MaxHeap
PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());
```



