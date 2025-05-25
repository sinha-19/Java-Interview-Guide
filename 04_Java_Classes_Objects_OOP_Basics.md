# 4. Classes and Objects (OOP Basics)

---

## What is Object-Oriented Programming (OOP)?

OOP is a programming paradigm based on the concept of “objects”, which bundle data (fields) and behavior (methods). Java is a purely object-oriented language (except for primitives).

---

## Key OOP Concepts

- **Class:** Blueprint for objects, defines fields and methods.
- **Object:** Instance of a class, has its own state and behavior.
- **Encapsulation:** Hiding data with access modifiers and providing methods to access it.
- **Abstraction:** Hiding complex implementation details and showing only the essentials.
- **Inheritance:** Mechanism where a new class inherits properties and behavior from an existing class.
- **Polymorphism:** One name, many forms — methods behave differently based on the object.

---

## Defining a Class

```java
public class Person {
    // Fields (attributes)
    String name;
    int age;

    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Method (behavior)
    public void greet() {
        System.out.println("Hello, my name is " + name);
    }
}
```

---

## Creating Objects

```java
Person p1 = new Person("Alice", 30);
p1.greet(); // Output: Hello, my name is Alice
```

---

## Access Modifiers

| Modifier    | Class | Package | Subclass | World |
|-------------|-------|---------|----------|-------|
| `public`    |  ✔    |   ✔     |   ✔      |  ✔    |
| `protected` |  ✔    |   ✔     |   ✔      |       |
| (default)   |  ✔    |   ✔     |          |       |
| `private`   |  ✔    |         |          |       |

- **private:** Only within the class.
- **default (no modifier):** Only within the package.
- **protected:** Package + subclasses.
- **public:** Everywhere.

---

## Constructors

- Special method to initialize objects.
- Name matches class, no return type.
- Can overload constructors.

```java
public Person() { // Default constructor
    this.name = "Unnamed";
    this.age = 0;
}
```

---

## The `this` Keyword

Refers to the current object.

```java
this.name = name; // Distinguishes field from parameter
```

---

## Static Members

- **static fields/methods:** Belong to the class, not to instances.

```java
class MathHelper {
    static int square(int n) { return n * n; }
}
int x = MathHelper.square(5); // x = 25
```

---

## Common Pitfalls

- Forgetting to instantiate objects with `new`.
- Accessing private fields from outside the class.
- Not initializing object fields (leads to default values or nulls).

---

## Interview Tips

- Explain the difference between class and object.
- Show how encapsulation is achieved using access modifiers.
- Know how and why to use constructors.
- Be familiar with static vs instance members.

---

## Possible Follow-Up Questions

- What is the default value of object fields?
- Can you overload constructors in Java?
- What is the purpose of the `this` keyword?
- What happens if you don’t define any constructor?
