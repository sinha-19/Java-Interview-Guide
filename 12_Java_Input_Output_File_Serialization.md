# 12. File I/O and Serialization

---

## File I/O (Input and Output)

- Java handles file reading/writing using classes from `java.io` and `java.nio.file`.

### Reading a Text File (Old Way)

```java
BufferedReader reader = new BufferedReader(new FileReader("input.txt"));
String line;
while ((line = reader.readLine()) != null) {
    System.out.println(line);
}
reader.close();
```

### Writing to a File

```java
BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"));
writer.write("Hello, world!");
writer.newLine();
writer.close();
```

### Java 7+ (NIO) for Simpler File Operations

```java
import java.nio.file.*;
List<String> lines = Files.readAllLines(Paths.get("input.txt"));
Files.write(Paths.get("output.txt"), lines);
```

---

## Object Serialization

- **Serialization:** Converting an object into a byte stream for storage or transmission.
- **Deserialization:** Reconstructing the object from the byte stream.

### Serializable Interface

- A class must implement `java.io.Serializable` to be serializable.

```java
class Student implements Serializable {
    private String name;
    private int age;
}
```

### Serializing an Object

```java
ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("student.ser"));
out.writeObject(student);
out.close();
```

### Deserializing an Object

```java
ObjectInputStream in = new ObjectInputStream(new FileInputStream("student.ser"));
Student s = (Student) in.readObject();
in.close();
```

---

## Transient Keyword

- `transient` fields are **not** serialized.

```java
transient int temp; // This field won't be saved
```

---

## Common Pitfalls

- Not closing streams (use try-with-resources in modern Java).
- Forgetting to implement `Serializable`.
- Changing class structure after serialization (can cause `InvalidClassException`).
- Serializing non-serializable fields (causes `NotSerializableException`).

---

## Interview Tips

- Be able to read and write text files using Java I/O.
- Understand when and how to use serialization.
- Know the use of `transient` and `serialVersionUID`.

---

## Possible Follow-Up Questions

- What is the difference between `FileReader` and `BufferedReader`?
- What happens if a class does not implement `Serializable`?
- How do you handle exceptions during file I/O?
- Why is `serialVersionUID` important?
