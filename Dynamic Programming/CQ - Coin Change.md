![[Pasted image 20260712204226.png]]
![[Pasted image 20260712212453.png]]
- You have to take every possible combinations for that you can opt for pick and skip approach.
- you can pick a coins as many times as you want.
- sum will get reduced Everytime you pick the coins  w-coins[i]
- and every time you have to compare the sum with the current coins index value if it is grater then you can pick it otherwise you have to return skip

Approach-
- See you have to first write the pick and skip logic then deal with edge cases 
- While picking up the element you also have to take care about the amount that is left and the next arr element if the arr element is greater than you have to skip...then return skip only
- if not then write the pick logic 
- and then the most important base case if idx reaches the end then you have to check two cases if the amount == 0 then return 0 that show no more elements to select  and if the amount is not eqaual to zero then Integer.Max_value as it gets returned and Math.min will take the min from both calls so it will pick the min not the highest value 