# Core Java Interview Notes

## Multithreading & Concurrency

1. **Difference between `synchronized` and `ReentrantLock`?**
   - `synchronized` is a keyword that offers intrinsic locking with automatic release.
   - `ReentrantLock` provides more control (e.g., `tryLock`, fair locking) and must be manually unlocked.

2. **What is a deadlock? How do you prevent it?**
   - Deadlock occurs when two threads wait on each other to release locks.
   - Prevent using lock ordering, timeout mechanisms, or `tryLock`.

3. **What’s the purpose of `volatile`?**
   - Ensures visibility of changes to variables across threads.
   - Prevents caching of variables locally.

4. **How does `ThreadLocal` work?**
   - Maintains a separate value for each thread using a thread-local map internally.

5. **When should you use `Callable` over `Runnable`?**
   - Use `Callable` when you need a return value or want to throw checked exceptions.

---

## Collections

1. **How is `HashMap` implemented internally?**
   - Uses an array of buckets (`Node[]`), where each entry is stored via hashing.
   - Collisions handled using chaining or balanced trees in Java 8+.

2. **What’s the difference between `ArrayList` and `LinkedList`?**
   - `ArrayList` uses dynamic arrays (fast random access).
   - `LinkedList` uses nodes (efficient inserts/deletes).

3. **When to use `ConcurrentHashMap` vs `Collections.synchronizedMap()`?**
   - `ConcurrentHashMap` offers better concurrency with segment-based locking.
   - `synchronizedMap` locks the entire map.

4. **What is fail-fast vs fail-safe iterator?**
   - Fail-fast throws `ConcurrentModificationException`.
   - Fail-safe (e.g., `CopyOnWriteArrayList`) uses snapshot.

5. **How do `TreeMap` and `HashMap` differ?**
    - `TreeMap` is sorted and uses Red-Black Tree.
    - `HashMap` is unordered and uses hashing.

---

## OOP & Best Practices

1. **What are the 4 pillars of OOP in Java?**
    - Encapsulation, Abstraction, Inheritance, Polymorphism.

2. **Difference between composition and inheritance?**
    - Composition uses "has-a" while inheritance uses "is-a" relationship.

3. **What is the Liskov Substitution Principle?**
    - Subtypes must be substitutable for their base types without altering correctness.

4. **Can an interface have static methods?**
    - Yes, from Java 8 onward.

5. **What is the diamond problem? How does Java 8 handle it?**
    - Occurs with multiple inheritance of methods.
    - Java resolves it using explicit override.

---

## Memory Management

1. **What is garbage collection in Java?**
    - Automatic process of reclaiming memory from unreachable objects.

2. **Explain the Java memory model.**
    - Heap (Young, Old), Stack, Metaspace.
    - Thread-safe reads/writes governed by JMM.

3. **What is PermGen vs Metaspace?**
    - PermGen (pre-Java 8) was fixed-size.
    - Metaspace grows dynamically.

4. **How does G1GC differ from CMS?**
    - G1GC is region-based, parallel, and has predictable pause times.

5. **How can you detect and fix memory leaks?**
    - Using tools like VisualVM, JProfiler.
    - Common causes: static collections, listeners not removed.

---

## Java 8+ Features

1. **What is a functional interface?**
    - An interface with a single abstract method.
    - Enables lambda expressions.

2. **Difference between `map()` and `flatMap()` in Streams?**
    - `map()` transforms each element.
    - `flatMap()` flattens nested structures.

3. **What are method references?**
    - A shorthand for calling methods using `::` syntax.
    - E.g., `System.out::println`.

4. **What is `Optional` and how should it be used?**
    - To avoid null.
    - Use `isPresent()`, `orElse()`, `map()`.
    - Don’t misuse as container.

5. **What is the purpose of default methods in interfaces?**
    - Allows adding methods without breaking implementations.
