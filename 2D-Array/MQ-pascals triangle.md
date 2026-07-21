![[Pasted image 20260714190557.png]]
- always remember that the Pascals Triangle List always Contains [1],[1,1]
- so using this apply for loop on it and add the first and second element in the arraylist and push it to the new ArraylLst

```java
class Solution {

    public List<List<Integer>> generate(int numRows) {

        List<List<Integer>> ll = new ArrayList<>();
        List<Integer> l1 = new ArrayList<>();
        List<Integer> l2 = new ArrayList<>();

        l1.add(1); // [1]
  
        l2.add(1);
        l2.add(1); // [1, 1]  
        
        ll.add(l1);
        if(numRows==1) return ll;
        
        ll.add(l2);
        if(numRows==2) return ll;
        for (int i = 3; i <= numRows; i++) {

  // make a new arrayList
            List<Integer> ln = new ArrayList<>();
  // use the topmost arraylist stored in the List<list<Integer>>
            List<Integer> l = ll.get(ll.size()-1);
  // add 1 as the first element in the new ArrayList
            ln.add(1);
  // now use that extracted arraylist and add the frist two elements and push it        as the elements on the new ArraYList 
           for(int j=0;j<=l.size()-2;j++){
                ln.add(l.get(j)+l.get(j+1));
            }
   // later add one more 1 at the end of the new arrayList         
            ln.add(1);
    // add it to the main arrayList         
            ll.add(ln);
        }
        return ll;
    }
}
```