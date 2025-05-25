# 6. Encapsulation, Abstraction, and Access Modifiers

---

## Encapsulation

- **Definition:** Bundling data (fields) and methods that operate on that data into a single unit (class).
- **Purpose:** Protects internal state by restricting direct access and allows controlled manipulation via methods (getters/setters).

**Example:**
```java
public class Account {
    private double balance; // private = encapsulated

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
}
```

---

## Abstraction

- **Definition:** Hiding complex implementation details and exposing only essential features via interfaces or abstract classes.
- **Purpose:** Reduces complexity, increases reusability, and separates “what” from “how”.

**Example (Interface):**
```java
interface Shape {
    void draw(); // Abstract - no implementation here
}
class Circle implements Shape {
    public void draw() { System.out.println("Draw Circle"); }
}
```

**Example (Abstract Class):**
```java
abstract class Vehicle {
    abstract void move();
}
class Car extends Vehicle {
    void move() { System.out.println("Car moves"); }
}
```

---

## Access Modifiers

| Modifier    | Class | Package | Subclass | World |
|-------------|-------|---------|----------|-------|
| `public`    |  ✔    |   ✔     |   ✔      |  ✔    |
| `protected` |  ✔    |   ✔     |   ✔      |       |
| (default)   |  ✔    |   ✔     |          |       |
| `private`   |  ✔    |         |          |       |

**Notes:**
- Use `private` for fields to encapsulate data.
- Use `public` for methods that provide controlled access.
- `protected` is mainly used for inheritance.
- (default, no keyword): visible only within the package.

---

## Getters & Setters

- Provide controlled access to private fields.
- Can add validation or logic.

```java
public class Person {
    private int age;

    public int getAge() { return age; }
    public void setAge(int a) {
        if (a > 0) age = a;
    }
}
```

---

## Common Pitfalls

- Exposing fields as `public` breaks encapsulation.
- Forgetting to use getters/setters for important validation.
- Overusing accessors for trivial logic (sometimes direct access is fine for immutable fields).

---

## Interview Tips

- Explain why encapsulation improves security and maintainability.
- Know how abstraction helps decouple interface from implementation.
- Be able to implement and use access modifiers properly.

---

## Possible Follow-Up Questions

- What is the difference between abstraction and encapsulation?
- Can you access a `private` field from a subclass?
- When would you use `protected` instead of `private`?
- What is the default access modifier in Java?
