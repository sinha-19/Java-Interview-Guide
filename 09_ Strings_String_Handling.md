# 9. Strings and String Handling

---

## What is a String in Java?

- **String:** An object representing a sequence of characters.
- **Immutable:** Once created, a String cannot be changed (modification creates a new String).

---

## Creating Strings

```java
String s1 = "Hello";            // String literal (pooled)
String s2 = new String("Hi");   // New String object
```

---

## Common String Methods

| Method                | Description                            | Example Output      |
|-----------------------|----------------------------------------|---------------------|
| `length()`            | Returns length                         | `s.length()`        |
| `charAt(int)`         | Gets character at index                | `s.charAt(0)`       |
| `substring(int, int)` | Extracts substring                     | `s.substring(1, 4)` |
| `toLowerCase()`       | Converts to lower case                 | `s.toLowerCase()`   |
| `toUpperCase()`       | Converts to upper case                 | `s.toUpperCase()`   |
| `trim()`              | Removes whitespace                     | `s.trim()`          |
| `indexOf(String)`     | Finds index of substring               | `s.indexOf("lo")`   |
| `equals(String)`      | Compares contents                      | `s.equals(s2)`      |
| `equalsIgnoreCase()`  | Case-insensitive comparison            |                     |
| `replace(a, b)`       | Replaces characters                    | `s.replace('l','x')`|
| `split(String regex)` | Splits by regex                        | `s.split(",")`      |

---

## String Comparison

- Use `equals()` for value comparison:
  ```java
  if (a.equals(b)) { ... }
  ```
- `==` compares references (not contents).

---

## StringBuilder & StringBuffer

- **StringBuilder:** Mutable, not thread-safe, fast.
- **StringBuffer:** Mutable, thread-safe, slower.
- Use for many modifications (e.g., in loops).

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
String result = sb.toString();
```

---

## String Formatting

```java
String name = "Alice";
int score = 95;
String msg = String.format("%s scored %d", name, score);
// Output: Alice scored 95
```

---

## String Pool

- String literals are stored in a common pool for memory efficiency.
- `"abc" == "abc"` is true for literals, false for new String objects.

---

## Common Pitfalls

- Using `==` to compare Strings (compares references, not content).
- Forgetting immutability (e.g., `s.concat("x")` does not change `s`).
- Inefficient concatenation in loops (use `StringBuilder`).

---

## Interview Tips

- Be able to explain string immutability and the string pool.
- Know the differences between `String`, `StringBuilder`, and `StringBuffer`.
- Show usage of common string methods and formatting.

---

## Possible Follow-Up Questions

- What is the difference between `==` and `equals()` for Strings?
- Why are Strings immutable in Java?
- When should you use `StringBuilder`?
- How does the String pool work?
