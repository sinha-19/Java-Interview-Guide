# 11. Multithreading and Concurrency

---

## What is Multithreading?

- **Multithreading:** Running multiple threads (lightweight processes) in parallel to maximize CPU utilization and program efficiency.
- **Thread:** An independent path of execution within a program.

---

## Creating Threads

### 1. Extending `Thread` class

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running...");
    }
}
MyThread t = new MyThread();
t.start();
```

### 2. Implementing `Runnable` interface

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Runnable running...");
    }
}
Thread t = new Thread(new MyRunnable());
t.start();
```

---

## Thread Lifecycle

```
New → Runnable → Running → Blocked/Waiting/Sleeping → Dead
```

---

## Thread Methods

| Method            | Description                                               |
|-------------------|----------------------------------------------------------|
| `start()`         | Starts thread, calls `run()`                             |
| `run()`           | Code executed by thread                                  |
| `sleep(ms)`       | Pauses thread for ms milliseconds                        |
| `join()`          | Waits for thread to finish                               |
| `interrupt()`     | Interrupts thread                                        |
| `setPriority()`   | Sets thread priority                                     |
| `isAlive()`       | Checks if thread is alive                                |

---

## Synchronization

- Ensures only one thread accesses a critical section at a time (solves race conditions).
- **synchronized keyword:** Used on methods/blocks.

```java
synchronized void increment() {
    count++;
}
```

---

## Inter-Thread Communication

- **wait()**, **notify()**, **notifyAll()** methods (used inside synchronized blocks).
- Used for producer-consumer and similar problems.

---

## Volatile Keyword

- Ensures visibility of variable updates to all threads.

```java
volatile boolean running = true;
```

---

## Thread Safety & Concurrency Utilities (java.util.concurrent)

- **Executors:** Manage thread pools (`ExecutorService`)
- **Locks:** Fine-grained locking (`ReentrantLock`)
- **Concurrent Collections:** `ConcurrentHashMap`, `CopyOnWriteArrayList`
- **Atomic Variables:** `AtomicInteger`, `AtomicBoolean`, etc.
- **CountDownLatch, Semaphore, CyclicBarrier**

---

## Example: Thread Pool

```java
ExecutorService executor = Executors.newFixedThreadPool(2);
executor.submit(() -> System.out.println("Task 1"));
executor.shutdown();
```

---

## Common Pitfalls

- Race conditions and inconsistent state
- Deadlocks (threads waiting forever)
- Forgetting to release locks
- Not handling InterruptedException

---

## Interview Tips

- Know the difference between process and thread
- Understand synchronization and inter-thread communication
- Be familiar with `java.util.concurrent` utilities
- Able to spot and explain deadlocks and race conditions

---

## Possible Follow-Up Questions

- What is the difference between `synchronized` and `Lock`?
- How does `volatile` differ from `synchronized`?
- What is a deadlock and how can you avoid it?
- How do thread pools improve performance?
