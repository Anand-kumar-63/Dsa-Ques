# Minimum cost to connect ropes - 
![[Pasted image 20260503013050.png]]
- By using the min heap and add the top two min values and then add back to the queue until queue size becomes one  and at the same time maintain a count and add sum it it 

![[Pasted image 20260503014154.png]]
![[Pasted image 20260503032418.png]]
- First create a triplet object in which three fields are there Dist x and y and we need to implement the Comparable interface and then override the CompareTo method to tell the priority Queue that done sorting on the Basis of  distance because due to many fields in an object the priority queue will sort on the basic of what value???....
- then use a priority queue to implement max heap then grow it till k size and them remove all the elements and then the remaining are the k closest to the orgin  

# K closest Elements..
![[Pasted image 20260503232549.png]]  
- In this k closest elements find Out Karne the to a particular element that is given so first we have
- first form class pair in which we will store number and diff with that element so that we can store that pair in the priorityQueue and that priority queue will make a max heap on the basis of diff of the element and number in the array
- To find diff of that element with the given one's and Then compare the pair that is going into the queue to make a max heap on the basis of diff not on the basis on numbers...
  you have to find the max heap upto to k elements only and after you have to start removing the PriorityQueue Elements after adding one ....In this way you can remove all the (n-k) Farest Elements left with k-Closest Elements now extract them out of the queue and print them

## LeetCode 347 Top K frequent Elements
![[Pasted image 20260504004328.png]]
# BST to Maxheap -
![[Pasted image 20260504235411.png]]
