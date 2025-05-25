# 7. Abstract Classes and Interfaces

---

## Abstract Classes

- **Definition:** A class that cannot be instantiated; it may have abstract (unimplemented) methods as well as concrete (implemented) methods.
- **Purpose:** To provide a base for other classes to extend, enforcing a contract for subclasses.

**Syntax:**
```java
abstract class Animal {
    abstract void makeSound(); // Abstract method

    void breathe() {           // Concrete method
        System.out.println("Breathing...");
    }
}
class Dog extends Animal {
    void makeSound() { System.out.println("Woof"); }
}
```

- Subclasses **must** implement all abstract methods.
- Can have constructors, fields, static methods.

---

## Interfaces

- **Definition:** A contract specifying methods that must be implemented; only method signatures (until Java 8).
- **Purpose:** Achieve abstraction and multiple inheritance (since classes can implement multiple interfaces).

**Syntax:**
```java
interface Movable {
    void move();
}
class Car implements Movable {
    public void move() { System.out.println("Moving..."); }
}
```

### Interface Features

- All methods are **public** and **abstract** by default (until Java 8).
- Fields are **public static final** (constants).
- A class can implement multiple interfaces.
- **Java 8+:** Static and default methods allowed in interfaces.
- **Java 9+:** Private methods allowed.

---

## Abstract Class vs Interface

| Feature         | Abstract Class           | Interface                   |
|-----------------|-------------------------|-----------------------------|
| Instantiation   | Cannot instantiate       | Cannot instantiate          |
| Methods         | Abstract & concrete      | Only abstract (Java 7-)     |
| Constructors    | Yes                     | No                          |
| Fields          | Any type                 | `public static final` only  |
| Multiple Inherit| Single inheritance       | Multiple inheritance        |
| Access Modifier | Any                      | `public` only (methods)     |

---

## Default & Static Methods in Interfaces (Java 8+)

```java
interface Logger {
    default void log(String msg) {
        System.out.println("LOG: " + msg);
    }
    static void staticLog(String msg) {
        System.out.println("STATIC LOG: " + msg);
    }
}
```

---

## Functional Interfaces & Lambda Expressions

- **Functional Interface:** Interface with a single abstract method. Used in lambda expressions.
```java
@FunctionalInterface
interface Calculator {
    int compute(int x, int y);
}
Calculator add = (a, b) -> a + b;
```

---

## Common Pitfalls

- Forgetting to implement all abstract/interface methods.
- Multiple inheritance conflicts (must resolve default methods explicitly).
- Not using `@Override` when implementing methods.
- Cannot instantiate abstract classes or interfaces directly.

---

## Interview Tips

- Explain when to use an abstract class vs an interface.
- Know how to use default and static methods in interfaces.
- Be able to write and implement interfaces and abstract classes.
- Understand functional interfaces and where lambdas apply.

---

## Possible Follow-Up Questions

- Can an abstract class have no abstract methods?
- Can an interface have constructors?
- What happens if two interfaces have the same default method?
- How does Java 8+ change what you can do with interfaces?

