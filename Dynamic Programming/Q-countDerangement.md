![[Pasted image 20260709142841.png]]
- You have to find the Number of ways in which you can arrange the values to Wrong Positions.
like you have a , b , c , d
so you have arrange them so that they don't placed at thier right positions
  b , a , d , c - example

- (n-1) * dreange(n-2) - when you are Exactly swapping it with the replacing element like a swapped with c - [ c , - , a , - ] you have 2 placed 
- (n-1) * derange(n-1)  when you don't Exactly swap it with the replacing element like a is replaced but c is not placed at the position of a  [c, - ,- ,-] you have three places to random sequence 
    you have to add both  [ (n-1) * derange(n-2) +  (n-1) * derange(n-1) ]
    