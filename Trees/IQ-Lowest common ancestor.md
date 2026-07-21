![[Pasted image 20260417104342.png]]
 
```java
class Solution {
        public Node LCA(Node root, Node p, Node q) {
            // code here
            if(root.left == null && root.right == null) return root;
            
            if(root.data == p.data || root.data == q.data) return root;
            // p left q rifht || q left p right 
            if( (exist(root.left,p) && exist(root.right,q) ) || (exist(root.left,q) && exist(root.right,p))) return root;
            
            // p not left and q right then go right
            if(!(exist( root.left , p ))&&(exist( root.right , q ))) return LCA(root.right , p , q);
            
            // p left and q not right thne go left
            else if((exist( root.left , p ))&&(!exist( root.right , q ))) return LCA(root.left , p ,q);
            
            return root;
        }
        static boolean exist(Node root , Node p){
            if (root == null) return false;
            if (root.data == p.data) return true;
            return exist(root.left, p) || exist(root.right, p);
        }
     }
