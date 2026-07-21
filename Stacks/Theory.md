Stacks is a data structure 
### Implementation of stack using LinkedList
![[Pasted image 20260305005209.png]]
```java
package Stacks;  
import java.util.Stack;    
class ListNode{  
    int val;  
    ListNode next;  
    ListNode(int data) {  
        this.val = data;  
    }}  
class stack{  
      int size;  
      ListNode head;  
      int peek()throws Exception{  
          if(head==null){  
              throw new Error("Null Pointer Exception");  
          }  
          return head.val;  
      }  
      int pop()throws Exception{  
          if(head==null){  
              throw new Error("Null Pointer Exception");  
          }  
          int x = head.val;  
          head = head.next;  
          size--;  
          return x;  
      }  
      int push(int val){  
          ListNode temp = new ListNode(val);  
          temp.next = head;  
          head = temp;  
          size++;  
          return val;  
      }  
      void display(){  
          ListNode temp = head;  
          while(temp!=null){  
              System.out.print(temp.val + " ");  
              temp = temp.next;  
          }  
          System.out.println(" ");  
      }}  
public class LLstack {  
    public static void main(String[] args)throws Exception{  
       stack first = new stack();  
//       first.pop();  
         first.push(90);  
         first.push(91);    
         first.display();  // 90 91  
         first.pop();  // 90
         System.out.println(first.peek()); // 91  
    }}
```