A **HashSet** is a data structure that stores **unique elements** and provides **very fast lookup, insertion, and deletion** operations. It is implemented using a **hash table**.
### Key characteristics
- ✅ **No duplicate values** are allowed.
- ✅ **Fast operations** (average time complexity is **O(1)** for add, remove, and contains).
- ❌ **No guaranteed order** of elements.
- ❌ Cannot access elements by index like an array or list.
### Example (Java)
```
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        HashSet<String> fruits = new HashSet<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Apple"); // Duplicate - ignored

        System.out.println(fruits);
        System.out.println(fruits.contains("Banana")); // true

        fruits.remove("Orange");
        System.out.println(fruits);
    }
}
```
**Possible output:**
```
[Apple, Orange, Banana]
true
[Apple, Banana]
```
Notice that:
- `"Apple"` appears only once, even though it was added twice.
- The order of elements is not guaranteed.
### How it works
A `HashSet` computes a **hash code** for each element to determine where to store it in memory. This allows it to quickly check whether an element already exists.
### When to use a HashSet
Use a `HashSet` when you need to:
- Remove duplicates from a collection.
- Check if an item exists quickly.
- Store a collection of unique values.
### HashSet vs ArrayList

| Feature      | HashSet          | ArrayList                   |
| ------------ | ---------------- | --------------------------- |
| Duplicates   | ❌ Not allowed    | ✅ Allowed                   |
| Order        | ❌ Not guaranteed | ✅ Preserves insertion order |
| Search       | ⚡ O(1) average   | 🐢 O(n)                     |
| Index access | ❌ No             | ✅ Yes                       |

**Example of removing duplicates:**
```
ArrayList<Integer> numbers = new ArrayList<>();
numbers.add(1);
numbers.add(2);
numbers.add(2);
numbers.add(3);

HashSet<Integer> uniqueNumbers = new HashSet<>(numbers);

System.out.println(uniqueNumbers); // [1, 2, 3]
```
In short, think of a `HashSet` as a **bag of unique items** where finding or adding an item is very fast, but the order of the items is not important.