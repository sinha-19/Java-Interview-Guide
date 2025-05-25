# 5. Inheritance and Polymorphism

---

## Inheritance

Inheritance allows a class (subclass/child) to acquire fields and methods from another class (superclass/parent).

### **Syntax**

```java
class Animal {
    void eat() {
        System.out.println("Eating");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking");
    }
}
```

- `Dog` inherits `eat()` from `Animal`.

### **Types of Inheritance in Java**

- **Single:** One subclass, one superclass (supported)
- **Multilevel:** Class inherits from a class that inherits from another (supported)
- **Hierarchical:** Multiple subclasses from a single superclass (supported)
- **Multiple inheritance** is NOT supported (but can be achieved via interfaces).

---

## The `super` Keyword

- Access parent class methods or fields.
- Call parent constructor.

```java
class Animal {
    Animal() { System.out.println("Animal created"); }
}
class Dog extends Animal {
    Dog() { super(); System.out.println("Dog created"); }
}
```

---

## Method Overriding

Subclass redefines a method from its superclass.

```java
class Animal {
    void sound() { System.out.println("Some sound"); }
}
class Dog extends Animal {
    @Override
    void sound() { System.out.println("Woof"); }
}
```

---

## Polymorphism

- **Definition:** One interface, many implementations.
- **Types:** Compile-time (method overloading) and runtime (method overriding).

### **Upcasting and Dynamic Method Dispatch**

```java
Animal a = new Dog(); // Upcasting
a.sound(); // Calls Dog's sound() due to dynamic dispatch
```

---

## Abstract Classes and Methods

- **Abstract class:** Cannot be instantiated, can have abstract (unimplemented) methods.
- **Abstract method:** Must be implemented by subclasses.

```java
abstract class Shape {
    abstract void draw();
}
class Circle extends Shape {
    void draw() { System.out.println("Drawing Circle"); }
}
```

---

## The `final` Keyword

- **final class:** Cannot be subclassed.
- **final method:** Cannot be overridden.
- **final variable:** Becomes a constant.

---

## Interfaces

- Define contracts (methods) for classes to implement.
- Multiple interfaces can be implemented (solves multiple inheritance).

```java
interface Printable {
    void print();
}
class Document implements Printable {
    public void print() { System.out.println("Printing..."); }
}
```

---

## Common Pitfalls

- Forgetting to use `@Override` when overriding methods.
- Accessing subclass-only methods through a superclass reference (requires casting).
- Attempting multiple inheritance with classes (not allowed).

---

## Interview Tips

- Be able to explain dynamic method dispatch and upcasting.
- Know the difference between abstract classes and interfaces.
- Discuss why Java doesn’t support multiple inheritance for classes.

---

## Possible Follow-Up Questions

- How is polymorphism implemented in Java?
- What is the difference between method overloading and overriding?
- Can you instantiate an abstract class?
- When would you use an interface over an abstract class?
