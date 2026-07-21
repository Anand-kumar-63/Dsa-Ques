#### [Basic problems]
## Insert an Element at the bottom of the stack using recursion
```java 

```
## Parenthesis Checker
![[Pasted image 20260305014924.png]]

```java
// you have to push the characters if they are ( , { ,[  other check the similer at the top of the stack and pop it out... at the end check for the empty stack
class Solution {
    public boolean isBalanced(String s) {
           Stack<Character> st = new Stack<>();
        int i = 0;
        while(i < s.length()){
            char ch = s.charAt(i);

            if((ch+"").equals("(") || (ch+"").equals("[") || (ch+"").equals("{")) {
                st.push(ch);
                i++;
            }
            else{
                if(st.isEmpty()){
                    return false;
                }
                else if(((ch+"").equals(")") && (st.peek()+"").equals("(")) ||
                        ((ch+"").equals("}") && (st.peek()+"").equals("{")) ||
                        ((ch+"").equals("]") && (st.peek()+"").equals("[")))
                {
                    st.pop();
                    i++;
                }
                else{
                    return false;
                }
            }
        }
        return st.isEmpty();
        }
    }

```
## Remove consecutive Characters
![[Pasted image 20260305161852.png]]
```java
// User function Template for Java

class Solution {
    public String removeConsecutiveCharacter(String s) {
        Stack<Character> st = new Stack<>();
        for(int i=0; i<s.length(); i++){
                char ch = s.charAt(i);
                if(st.isEmpty()){
                    st.push(ch);
                }else{
                    if((st.peek()).equals(ch)){
                        continue;
                    }else{
                        st.push(ch);
                    }
                }
        }
        StringBuilder sb = new StringBuilder();
        int size = st.size();
        for(int i=0;i<size;i++){
            sb.append(st.pop());
        }
        sb.toString();
        StringBuilder reverse = new StringBuilder(sb).reverse();
        return reverse.toString();
    }
}
```

## Leetcode682
![[Pasted image 20260305211554.png]]
## Leetcode2487
you have to take a stack of type Node and then store all the nodes inside it then while loop condition jab tak stack empty nhi hota we will check the value of peek with the new List formed if top value greater then pop and add it to list and pop and if then only pop out of the stack 
![[Pasted image 20260305220408.png]]
## next greater element gfg
- you have to extract the array value  from the last and put it inside the stack then  you have to check that if the stack top value is less than the arr[i] if it is then you have to pop() till stack gets empty or peek value becomes greater than the arr[i] value then accordingly you can change the arr[i] to -1 or the peek value respqectively in the case of empty stack or the peek value..
![[Pasted image 20260307145955.png]]
## Next greater Element2 503-
![[Pasted image 20260307195818.png]]
- you have to put all the array element from end into the stack then the same nextgreater element rules.. 
![[Pasted image 20260308182949.png]]

## Stock span problem-
![[Pasted image 20260309013045.png]]
![[Pasted image 20260309162447.png]]

## Celebrity problem
m1
![[Pasted image 20260309233306.png]]
m2
