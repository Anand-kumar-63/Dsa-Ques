
![[Pasted image 20260518010353.png]]
```java
// you have to go till leaf node in any subtree to find the min depth  you can't  just retrun 0 is the left subtree is null and right is not you have to traverse the right then

class Solution {
    int minDepth(Node root) {
       if(root==null){
           return 0;
       }
       // this if when left is null but right is not null so you have to calculate        the depth in right SubTree 
                1 left is null so go to right
                 \
                  3
                 / \
                2   10
               /
              6
             / \
            4   7
             \   \
              5   9
                 /
                8         
       if(root.left==null && root.right!=null) return 1 + minDepth(root.right); 
       // this if when righ is null but left is not null so you have to calculate          the depth in left SubTree 
                5
              /   \
             4     10 here right is null
            /      /
           3      8
          /      / \
         2      6   9
        /        \
       1          7
       else if(root.right==null && root.left!=null) return 1 + minDepth(root.left);
       else return 1 + Math.min(minDepth(root.left),minDepth(root.right));        
}}
```

### BST key in a Range
![[Pasted image 20260518012802.png]]
![[Pasted image 20260518012825.png]]
