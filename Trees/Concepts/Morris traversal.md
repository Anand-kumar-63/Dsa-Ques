**Morris Traversal** is a clever tree traversal algorithm used to traverse a binary tree **without using recursion or a stack**—so it runs in **O(1) extra space**.

It works by temporarily modifying the tree structure (creating “threads”) to remember how to return to a node after visiting its left subtree.

### 🌳 Key Idea
Normally, traversing a binary tree (like **inorder traversal**) requires:
- recursion (call stack), or
- an explicit stack
**Morris Traversal avoids both** by:
- making temporary links (threads) from a node’s predecessor back to the node.
![[Pasted image 20260517201057.png]]

Steps:
1. Start at the root.
2. if( root != null)
	  if( root.left != null )
         print(root.data)
         root = root.right 
    - If the node **has a left child**:
        - Find its **inorder predecessor** (rightmost node in left subtree)
        - If predecessor’s right is NULL:
            - Set it to point to current (create thread)
            - Move to left child
        - Else (thread already exists):
            - Remove the thread
            - Visit current node
            - Move to right child
![[Pasted image 20260517221316.png]]
### Why It Works
The temporary threads let you:
- return to a node after finishing its left subtree
- without storing anything in a stack
After traversal, the tree is restored to its original form.

### Example-
![[Pasted image 20260517235802.png]]
