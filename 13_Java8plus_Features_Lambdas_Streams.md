# 13. Java 8+ Features (Lambdas, Streams, etc.)

---

## Lambda Expressions

- **Definition:** Short way to write anonymous functions, mainly for passing behavior.
- **Syntax:**  
  ```java
  (parameters) -> expression
  (a, b) -> a + b
  ```

- **Example (Runnable):**
  ```java
  Runnable r = () -> System.out.println("Hello!");
  ```

- **Used with:** Functional interfaces (interfaces with one abstract method).

---

## Functional Interfaces

- Annotated with `@FunctionalInterface`
- Example: `Runnable`, `Comparator`, `Callable`, `Supplier`, `Consumer`, `Predicate`, `Function`

---

## Method References

- Reference to an existing method:
  - `System.out::println`
  - `String::toUpperCase`
- Used instead of lambdas when just calling a method.

---

## Streams API

- **Purpose:** Process sequences of elements (collections, arrays) using a functional style.
- **Features:** Filtering, mapping, reducing, sorting, collecting.

**Example:**
```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
names.stream()
    .filter(n -> n.startsWith("A"))
    .map(String::toUpperCase)
    .forEach(System.out::println); // Output: ALICE
```

### Common Stream Operations

| Operation      | Description                        |
|----------------|------------------------------------|
| `filter()`     | Select elements matching condition |
| `map()`        | Transform elements                 |
| `forEach()`    | Perform action for each element    |
| `collect()`    | Gather results (to List, Set, etc) |
| `reduce()`     | Combine elements to single value   |
| `sorted()`     | Sort elements                      |
| `count()`      | Count elements                     |

---

## Default & Static Methods in Interfaces

- **Default methods:** Provide method implementation in interface.
- **Static methods:** Utility methods in interface.

```java
interface MyInterface {
    default void show() { System.out.println("Show"); }
    static void hello() { System.out.println("Hello!"); }
}
```

---

## Optional

- **Purpose:** Avoid null values.
- **Example:**
  ```java
  Optional<String> opt = Optional.ofNullable(name);
  if (opt.isPresent()) {
      System.out.println(opt.get());
  }
  ```

---

## Date and Time API (java.time)

- Replaces old `java.util.Date` and `Calendar`.
- **Classes:** `LocalDate`, `LocalTime`, `LocalDateTime`, `ZonedDateTime`, `Period`, `Duration`

```java
LocalDate today = LocalDate.now();
LocalDate dob = LocalDate.of(2000, 1, 1);
Period age = Period.between(dob, today);
```

---

## Other Notable Features

- **Nashorn JavaScript engine** (deprecated in Java 15)
- **CompletableFuture** for async programming
- **Type inference** with `var` (Java 10+)
- **Records** (Java 14+, concise data classes)

---

## Common Pitfalls

- Not closing streams (they don’t auto-close unless used with files/resources)
- Mutability issues with streams (streams are not storage containers)
- Not understanding lazy evaluation in streams
- Using lambdas with non-effectively final variables

---

## Interview Tips

- Be able to write a lambda for sorting, filtering, or mapping.
- Know the main Stream API operations and method references.
- Understand the difference between `Optional` and `null`.
- Know why Java 8+ APIs are preferred for collections and date/time.

---

## Possible Follow-Up Questions

- What is the difference between `map` and `flatMap` in streams?
- How do you handle checked exceptions in lambdas?
- Can streams be reused?
- Why is `Optional` preferable to returning `null`?
