# 3. Control Flow Statements

---

## Conditional Statements

### **A. if, else if, else**

```java
if (condition) {
    // Code if condition is true
} else if (anotherCondition) {
    // Code if anotherCondition is true
} else {
    // Code if none are true
}
```

### **B. switch Statement**

Used for multi-way branching based on a single variable (int, char, String).

```java
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Other");
}
```
- **Since Java 7, `switch` supports Strings.**

---

## Looping Statements

### **A. for Loop**

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

### **B. while Loop**

```java
int n = 0;
while (n < 5) {
    System.out.println(n);
    n++;
}
```

### **C. do-while Loop**

Executes at least once.

```java
int n = 0;
do {
    System.out.println(n);
    n++;
} while (n < 5);
```

---

## Jump Statements

| Statement | Purpose                                      |
|-----------|----------------------------------------------|
| `break`   | Exit loop or switch                          |
| `continue`| Skip to next iteration of loop               |
| `return`  | Exit from method, optionally with value      |

---

## Enhanced for Loop (for-each)

Used for arrays and collections.

```java
int[] arr = {1, 2, 3};
for (int num : arr) {
    System.out.println(num);
}
```

---

## Labeled break/continue

For breaking out of nested loops.

```java
outer:
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        if (i == j) break outer;
    }
}
```

---

## Common Pitfalls

- Forgetting `break` in `switch` (causes fall-through).
- Infinite loops (missing update/condition).
- Off-by-one errors in loops.
- Using assignment `=` instead of comparison `==` in conditions.

---

## Interview Tips

- Be ready to trace and debug code with nested loops and conditions.
- Know the difference between `while` and `do-while`.
- Understand switch fall-through and how to prevent it.

---

## Possible Follow-Up Questions

- Can switch work with Strings in Java?
- What is the difference between `continue` and `break`?
- How do you exit from multiple nested loops?
- When would you use a do-while loop?
