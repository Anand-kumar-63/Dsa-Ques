The **diameter of a binary tree** is the **length of the longest path between any two nodes** in the tree.
![[Pasted image 20260416225138.png]]

![[Pasted image 20260416225546.png]]

![[Pasted image 20260416225659.png]]
![[Pasted image 20260416231119.png]]
![[Pasted image 20260416231258.png]]

```java 
class Solution{
  int diamter = 0;
  public int DaimeterofBinaryTree(String[] args){
         height(root);
         return daimeter;
  }
  private int height(TreeNode root){
      if(node==null) return 0;
      int left = height(node.left);
      int right = height(node.right);
      diameter = Math.max( diameter , left + right );
      return 1+Math.max(left,right);
  }
}
```
```