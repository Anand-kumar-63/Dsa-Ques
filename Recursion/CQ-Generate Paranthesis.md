![[Pasted image 20260803161802.png]]
```java
class Solution {
    public ArrayList<String> generateParentheses(int n) {
           ArrayList<String> al = new ArrayList<>();
           generate("",0,0,n,al);
           return al;
    }
    static void generate(String str , int l , int r , int n , ArrayList<String> arr){      if(r==(n/2)){
               arr.add(str);
               return;
           }
           if(l<n/2){
              generate(str+"(",l+1,r,n,arr);
           }
           if(l>r){
               generate(str+")",l,r+1,n,arr);
           }}
}
```
- it's a Special kind of Pick and Skip problem in which you have to choose either to take left or right 
![[Pasted image 20260803161902.png]]