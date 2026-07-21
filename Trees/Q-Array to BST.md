![[Pasted image 20260518001907.png]]
```java
/*
class Node {
    int data;
    Node left, right;

    Node(int item) {
        data = item;
        left = right = null;
    }
}
*/
class Solution {
    public Node sortedArrayToBST(int[] arr) {
        return bst(arr, 0 ,arr.length-1);
    }
    static Node bst(int[] arr , int li , int hi){
        if(li>hi) return null;
        int mid = (li+hi)/2;
        Node root = new Node(arr[mid]);
        root.left = bst(arr,li,mid-1);
        root.right = bst(arr,mid+1,hi);
        return root;
    }
}
```