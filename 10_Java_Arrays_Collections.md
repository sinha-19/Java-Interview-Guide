# 10. Arrays and Collections

---

## Arrays

- **Definition:** Fixed-size, ordered collection of elements of the same type.
- **Declaration and Initialization:**
  ```java
  int[] numbers = new int[5];
  String[] names = {"Alice", "Bob", "Charlie"};
  ```
- **Access:** Zero-based index (`numbers[0]`)
- **Length:** `array.length`
- **Multidimensional Arrays:**  
  ```java
  int[][] matrix = new int[3][4];
  ```

---

## Common Array Operations

| Task           | Example                       |
|----------------|------------------------------|
| Traverse       | `for (int i : arr) {}`       |
| Sort           | `Arrays.sort(arr);`          |
| Search         | `Arrays.binarySearch(arr, x)`|
| Copy           | `Arrays.copyOf(arr, newLen)` |

- Use `java.util.Arrays` for utility methods.

---

## Limitations of Arrays

- Fixed size (cannot grow/shrink)
- Only homogeneous elements
- No built-in methods for common operations (add, remove, etc.)

---

## Collections Framework

- **Definition:** Set of interfaces and classes for storing and manipulating groups of data as objects.
- **Located in:** `java.util` package

### Main Interfaces

| Interface   | Description                               | Implementations         |
|-------------|-------------------------------------------|------------------------|
| List        | Ordered, duplicates allowed               | ArrayList, LinkedList  |
| Set         | Unordered, no duplicates                  | HashSet, TreeSet       |
| Queue       | FIFO, ordered                             | LinkedList, PriorityQueue |
| Map         | Key-value pairs, keys unique              | HashMap, TreeMap       |

---

## List Example

```java
List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
String f = list.get(0); // "Apple"
```

---

## Set Example

```java
Set<Integer> set = new HashSet<>();
set.add(10);
set.add(20);
boolean hasTen = set.contains(10); // true
```

---

## Map Example

```java
Map<String, Integer> map = new HashMap<>();
map.put("Alice", 90);
map.put("Bob", 85);
int score = map.get("Alice"); // 90
```

---

## Generics

- Allow type-safe collections
- Example: `List<String>` vs. raw `List`

---

## Iterating Collections

```java
for (String s : list) {
    System.out.println(s);
}
for (Map.Entry<String, Integer> entry : map.entrySet()) {
    System.out.println(entry.getKey() + ": " + entry.getValue());
}
```

---

## Collection Utilities

- `Collections.sort(list);`
- `Collections.reverse(list);`
- `Collections.max(list);`

---

## Common Pitfalls

- ArrayIndexOutOfBoundsException
- Using raw types instead of generics
- Modifying a collection while iterating (ConcurrentModificationException)

---

## Interview Tips

- Know the differences between ArrayList and LinkedList
- Understand when to use Set vs. List
- Be able to explain how HashMap works internally (hashing, collisions)
- Familiarity with iterators and enhanced for loop

---

## Possible Follow-Up Questions

- How does HashSet ensure uniqueness?
- Difference between HashMap and TreeMap?
- When would you use an array over an ArrayList?
- What is the initial capacity of ArrayList?
