
dll Implementation , reverse dll using three pointer or two pointers
``
```java
package LinkedList;  
  
import java.util.List;  
  
class ListNode{  
    int data;  
    ListNode prev;  
    ListNode next;  
    ListNode(int val){  
        this.data = val;  
    }  
}  
class DLL{  
    ListNode head = null;  
    ListNode tail = null;  
    int size;  
    void addAtHead(int val){  
        ListNode temp = new ListNode(val);  
        if( head == null ){  
            head = temp;  
            tail = temp;  
        }  
        else{  
             head.prev = temp;  
             temp.next = head;  
             head = temp;  
        }  
        size++;  
    }  
    void InsertAtTail(int val){  
        ListNode temp = new ListNode(val);  
        if(tail==null){  
            head = temp;  
            tail = temp;  
        }  
        else{  
            tail.next = temp;  
            temp.prev = tail;  
            tail = temp;  
        }  
        size++;  
    }  
  
    void DeleteAtTail(){  
        if(tail==null){  
            return;  
        }  
        else{  
          tail = tail.prev;  
          tail.next.prev = null;  
          tail.next = null;  
        }  
        size--;  
    }  
    void DeleteAtHead(){  
        if(head==null){  
            return;  
        }  
        else{  
            head = head.next;  
            head.prev.next  = null;  
            head.prev = null;  
        }  
        size--;  
    }  
    void display(){  
        ListNode temp = head;  
        while(temp!=null){  
            System.out.println(temp.data);  
            temp = temp.next;  
        }  
    }  
  
    static ListNode DisplayReverse(ListNode head){  
        if(head.next==null){  
            System.out.println(head.data);  
            return head;  
        }  
        ListNode temp = head;  
        DisplayReverse(temp.next);  
        System.out.println(temp.data);  
        return head;  
    }  
  
    void insert(int val , int target){  
        ListNode isrt = new ListNode(val);  
        ListNode temp = head;  
          while(temp.data!=target){  
               temp = temp.next;  
          }  
          temp.next.prev = isrt;  
          isrt.next = temp.next;  
          temp.next = isrt;  
          isrt.prev = temp;  
    }  
    void delete(int target){  
        ListNode temp = head;  
          
    }  
  
}  
public class dll{  
  
}
```
### Reverse linkedList
![[Pasted image 20260302201446.png]]
![[Pasted image 20260302201537.png]]
## rotate a doubly linkedList
- you can a temp pointer 
-- first you have to make it circular linked list and them you have to move the head pointer according to the value of p and break the bond between prev and head element.
![[Pasted image 20260302203723.png]]
## Remove duplicates in the DoublyLinkedList 
![[Pasted image 20260303143524.png]]
```java Method -2
##using two pointers
class Solution {
    Node removeDuplicates(Node head) {
         Node fwd = new Node(-1);
         Node k = fwd;
         Node i = head;
         while(i != null){ // you have to check for the i to not to be null
             if(k == fwd || k.data != i.data)
             {
                 k.next = i;
                 i.prev = k;
                 k = i;
             }
             i = i.next;
         }
        Node NewHead = fwd.next;
        if(NewHead!=null){
            NewHead.prev = null;
        }
        k.next = null;
        return NewHead;
    }
}
```

## Flatten a DoublyLinked List
![[Pasted image 20260303183527.png]]
![[Pasted image 20260303183540.png]]