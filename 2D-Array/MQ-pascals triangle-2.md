![[Pasted image 20260714193231.png]]

```java
class Solution {
    public List<Integer> getRow(int rowIndex) {
        if(rowIndex==0){
            List<Integer> l = new ArrayList<>();
            l.add(1);
            return l;
        }
        if(rowIndex==1){
            List<Integer> l = new ArrayList<>();
            l.add(1);
            l.add(1);
            return l;
        }
        List<List<Integer>> ll = new ArrayList<>();
        List<Integer> l1 = new ArrayList<>();
        List<Integer> l2 = new ArrayList<>();
        l1.add(1);
        l2.add(1);
        l2.add(1);
        ll.add(l1);
        ll.add(l2);
        for(int i=2;i<=rowIndex;i++){
            List<Integer> nl = new ArrayList<>();
            List<Integer> el = ll.get(ll.size()-1);
            nl.add(1);
            for(int j=0;j<=el.size()-2;j++){
               nl.add(el.get(j)+el.get(j+1));
            }
            nl.add(1);
            ll.add(nl);
        }
        return ll.get(rowIndex);
    }
}
```