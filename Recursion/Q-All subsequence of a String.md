![[Pasted image 20260802233035.png]]
```java
class Solution {
	public List<String> powerSet(String s) {
		List<String> list= new ArrayList<>();
		helper(s,0,list,"");
		Collections.sort(list);
		return list;
	}
	static void helper(String s , int idx, List<String> arr , String ans){
	       if(idx==s.length()){
	           arr.add(ans);
	           return;
	       }
	       helper(s,idx+1,arr,ans+s.charAt(idx));
	       helper(s,idx+1,arr,ans);
	}
}
```