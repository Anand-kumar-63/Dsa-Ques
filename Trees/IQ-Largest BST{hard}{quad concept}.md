![[Pasted image 20260515193439.png]]
![[Pasted image 20260515193448.png]]
- Every nodes gives four info about max , min , size , is BST
  first you will go left and then right 
- After that you will calculate the BST for the current node if it is a BST or not 
- Now you calculate the size using 1 + LeftSize + RightSize
- now you calculate the min and max for the current node by Compairing it with min and max values of left and right subtree 
- then if this particular node is a BST then maxsize = Math.max(size , maxsize)
- then return quad(max,min,size,bst);

