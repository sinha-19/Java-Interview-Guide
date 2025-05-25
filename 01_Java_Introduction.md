# 1. Introduction to Java

---

## What is Java?

Java is a high-level, class-based, object-oriented programming language designed to have as few implementation dependencies as possible. It is widely used for building cross-platform, robust, and secure applications.

---

## Key Features

- **Platform Independent:** Write Once, Run Anywhere (WORA) via the Java Virtual Machine (JVM).
- **Object-Oriented:** Everything is an object (almost).
- **Robust & Secure:** Strong memory management, exception handling, and security features.
- **Rich API:** Extensive standard libraries.
- **Multithreaded:** Built-in support for concurrent programming.
- **Automatic Garbage Collection:** No need for manual memory management.

---

## Java Program Flow

1. **Write source code** in `.java` files.
2. **Compile** with `javac` to produce bytecode (`.class` files).
3. **Run** via the Java Virtual Machine (`java` command).

**Diagram:**
```
[.java code] --(javac)--> [.class bytecode] --(JVM)--> [Execution]
```

---

## Hello World Example

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

---

## Java Editions

- **SE (Standard Edition):** Core language and libraries.
- **EE (Enterprise Edition):** Web, server, and enterprise features.
- **ME (Micro Edition):** Embedded and mobile devices.

---

## Interview Tips

- Be able to explain “Write Once, Run Anywhere.”
- Know the Java compilation and execution process.
- Understand the role of the JVM.

---

## Possible Follow-Up Questions

- What is bytecode?
- How does Java achieve platform independence?
- What is the difference between JDK, JRE, and JVM?
- What is garbage collection?
