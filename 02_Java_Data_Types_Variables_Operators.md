# 2. Java Data Types, Variables, and Operators

---

## Data Types in Java

Java is statically typed; every variable must have a declared type. Types are divided into:

### **A. Primitive Data Types**

| Type      | Size (bits) | Default | Example Values         |
|-----------|-------------|---------|-----------------------|
| `byte`    | 8           | 0       | -128 to 127           |
| `short`   | 16          | 0       | -32,768 to 32,767     |
| `int`     | 32          | 0       | -2^31 to 2^31-1       |
| `long`    | 64          | 0L      | -2^63 to 2^63-1       |
| `float`   | 32          | 0.0f    | 3.4e-038 to 3.4e+038  |
| `double`  | 64          | 0.0d    | 1.7e-308 to 1.7e+308  |
| `char`    | 16          | '\u0000'| 'a', '1', '$'         |
| `boolean` | 1 (logical) | false   | true, false           |

### **B. Reference Types**

- **Objects** (instances of classes)
- **Arrays**
- **Strings** (special class, immutable)

---

## Variables

- **Declaration:**  
  `int age;`
- **Initialization:**  
  `age = 25;`
- **Declaration + Initialization:**  
  `String name = "Alice";`

**Naming Rules:**
- Start with a letter, `$`, or `_`
- Cannot start with a digit
- Case-sensitive
- Cannot use Java reserved keywords

---

## Literals

- Integer: `10`, `0b101`, `0xFF`, `1_000_000`
- Floating-point: `3.14`, `2.0e5`
- Char: `'A'`, `'\n'`
- String: `"Hello"`
- Boolean: `true`, `false`

---

## Type Casting

- **Implicit (Widening):**  
  `int i = 5; double d = i; // OK`
- **Explicit (Narrowing):**  
  `double d = 5.7; int i = (int) d; // i = 5`

---

## Operators

| Type               | Operators                                              | Example             |
|--------------------|-------------------------------------------------------|---------------------|
| Arithmetic         | `+`, `-`, `*`, `/`, `%`, `++`, `--`                   | `a + b`             |
| Assignment         | `=`, `+=`, `-=`, `*=`, `/=`, `%=`                     | `a += 2`            |
| Relational         | `==`, `!=`, `>`, `<`, `>=`, `<=`                      | `a > b`             |
| Logical            | `&&`, `||`, `!`                                       | `a && b`            |
| Bitwise            | `&`, `|`, `^`, `~`, `<<`, `>>`, `>>>`                 | `a << 2`            |
| Ternary            | `? :`                                                 | `max = (a > b) ? a : b` |
| instanceof         | `instanceof`                                          | `obj instanceof String` |
| String Concatenation | `+`                                                 | `"Hi " + name`      |

---

## Example

```java
int x = 10, y = 20;
int sum = x + y;
double avg = (x + y) / 2.0;
boolean isEqual = (x == y);
String message = "Sum: " + sum;
```

---

## Common Pitfalls

- Integer division truncates decimal (`5/2` gives `2`)
- Uninitialized local variables cause compilation errors
- Overflow/underflow in arithmetic
- Comparing objects with `==` instead of `.equals()`

---

## Interview Tips

- Be able to explain primitive vs reference types
- Know how type casting works
- Understand operator precedence and associativity

---

## Possible Follow-Up Questions

- What is the difference between `==` and `.equals()` for objects?
- What happens when you add an `int` and a `double`?
- Can you use `null` with primitive data types?
- How does Java handle overflow?
