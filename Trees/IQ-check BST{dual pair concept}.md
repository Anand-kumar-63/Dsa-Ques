### using ArrayList
![[Pasted image 20260515162037.png]]

![[Pasted image 20260515162009.png]]

### using (min-max) pair return
Find max of the binary tree ,  same for min
![[Pasted image 20260515162537.png]]

But we need both max and min pair from every node so we have to return  an Object
![[Pasted image 20260515163745.png]]
return Twin( max , min )
```java
/*
class Node {
    int data;
    Node left;
    Node right;

    Node(int val) {
        data = val;
        left = right = null;
    }
}
*/
class Twin{
      int max;
      int min;
      Twin(int max , int min){
          this.max = max;
          this.min = min;
      }
}
class Solution {
    boolean flag;
    public boolean isBST(Node root) {
        // ArrayList<Integer> arr = new ArrayList<>();
        flag = true;
        Maxmin(root);
        //  for(int i=0;i<arr.size()-1;i++){
        //      if(arr.get(i) >= arr.get(i+1)){
        //          return false;
        //      }
        //  }
        return flag;
    }
    Twin Maxmin(Node root){
        if(root==null) return new Twin(Integer.MIN_VALUE , Integer.MAX_VALUE);
        Twin left = Maxmin(root.left);
        Twin right = Maxmin(root.right);
        if(left.max >= root.data || root.data >= right.min) flag = false;
        int max = Math.max( root.data , Math.max(left.max,right.max));
        int min = Math.min( root.data , Math.min(left.min , right.min));
        return new Twin(max,min);
    }
    // static void dfs(Node root , ArrayList<Integer> arr){
    //       if(root==null) return;
    //       dfs(root.left,arr);
    //       arr.add(root.data);
    //       dfs(root.right,arr);
    // }
}
```
- You have to return a twin object with (max , min ) of Left Subtree and right Subtree and then calculate the max value and min value using left and right max and min value and the root Value.
- then calculate at every root that if the left subtree min value is less than and right subtree max value is greater than the root value if it is not then flag false and it is not a binary search Tree

### Method2- 
simple inorder traversal store in arraylist then check for the NextGreater series 
```java
/*class Node {
    int data;
    Node left;
    Node right;
    Node(int val) {
        data = val;
        left = right = null;
    }}
*/class Solution {
    public boolean isBST(Node root) {
        ArrayList<Integer> arr = new ArrayList<>();
        dfs(root ,arr);
         for(int i=0;i<arr.size()-1;i++){
             if(arr.get(i) >= arr.get(i+1)){
                 return false;
             }
         }
         return true;
    }
    static void dfs(Node root , ArrayList<Integer> arr){
           if(root==null) return;
           dfs(root.left,arr);
           arr.add(root.data);
           dfs(root.right,arr);
    }
}
```