# 🧠 LRU Cache Implementation in Java

A simple and efficient implementation of a **Least Recently Used (LRU) Cache** in Java using a custom Doubly Linked List and a HashMap. The cache supports constant-time \(O(1)\) lookup, insertion, updating, and eviction operations.

## 📌 Overview

An LRU (Least Recently Used) Cache is a data structure that stores a limited number of key-value pairs. When the cache reaches its capacity, it removes the **least recently used entry** to make room for new data.

LRU caching is commonly used in memory management, database systems, and application performance optimization.

## ✨ Features

- ⚡ **O(1) operations:** Efficient lookup, insertion, and updates.
- 🗺️ **HashMap-based lookup:** Provides direct access to cache entries.
- 🔗 **Custom Doubly Linked List:** Maintains the order of recently used entries.
- 🎯 **Automatic eviction:** Removes the least recently used entry when capacity is reached.
- 🔄 **Usage tracking:** Moves accessed or updated entries to the most recently used position.
- 🧩 **Dummy head and tail nodes:** Simplifies list operations and reduces edge cases.
- ☕ **Pure Java implementation:** Uses standard Java data structures without external dependencies.

## 🛠️ Tech Stack

- **Language:** Java
- **Data Structures:** HashMap, Doubly Linked List
- **Concepts:** Object-Oriented Programming, Cache Eviction, Time Complexity Analysis

## ⚙️ How It Works

The implementation combines two data structures:

1. **HashMap:** Maps each key to its corresponding linked-list node for fast access.
2. **Doubly Linked List:** Maintains entries in order of usage, from most recently used to least recently used.

### Cache Structure

```text
HEAD ⇄ Most Recently Used ⇄ ... ⇄ Least Recently Used ⇄ TAIL
```

- **Access an existing key:** Retrieve its value and move its node to the front.
- **Insert a new key:** Add its node immediately after the head.
- **Update an existing key:** Update its value and move it to the front.
- **Exceed capacity:** Remove the node immediately before the tail and delete its key from the HashMap.

The dummy head and tail nodes simplify insertion and removal by avoiding special handling for the first and last actual nodes.

## ⏱️ Time and Space Complexity

| Operation | Time Complexity |
|---|---|
| `getValue(key)` | O(1) |
| `insertKeyValue(key, value)` | O(1) |
| `removeNode(node)` | O(1) |
| `addToFront(node)` | O(1) |
| `mostRecentKey()` | O(1) |

**Space Complexity:** O(C), where C is the cache capacity.

*These complexities assume standard HashMap operations take expected O(1) time.*

## 💻 Example Usage

```java
LRUCache lru = new LRUCache(3);

lru.insertKeyValue("mango", 10);
lru.insertKeyValue("apple", 20);
lru.insertKeyValue("banana", 30);

System.out.println(lru.mostRecentKey()); // banana

lru.insertKeyValue("mango", 40);
System.out.println(lru.mostRecentKey()); // mango

Integer value = lru.getValue("mango");
if (value != null) {
    System.out.println("Order of Mango " + value); // 40
}

lru.insertKeyValue("guava", 20);

if (lru.getValue("apple") == null) {
    System.out.println("apple doesn't exist");
}
```

### Expected Output

```text
banana
mango
Order of Mango 40
apple doesn't exist
```

## 🚀 Getting Started

### Prerequisites

- Java Development Kit (JDK) 8 or higher
- Any Java IDE or editor, such as IntelliJ IDEA, Eclipse, or VS Code

### Installation and Execution

**1. Clone the repository**

```bash
git clone https://github.com/Sahirahmad-12/LRU-Cache-in-Java.git
```

**2. Navigate to the project directory**

```bash
cd LRU-Cache-in-Java
```

**3. Navigate to the directory containing `LRUCache.java`**

The Java source file is inside the `LRU-Cache-in-java` folder in this repository.

```bash
cd LRU-Cache-in-java
```

**4. Compile the program**

```bash
javac LRUCache.java
```

**5. Run the program**

```bash
java LRUCache
```

*Note: If the class containing `main()` has a different name or the source file is located elsewhere, adjust the commands accordingly.*

## 📚 Concepts Demonstrated

- HashMap and linked-list integration
- Doubly linked list pointer manipulation
- Least Recently Used (LRU) eviction policy
- Object-Oriented Programming (OOP)
- Efficient memory and cache management
- Time and space complexity analysis

## 🎯 Learning Outcomes

This project demonstrates how combining a HashMap with a Doubly Linked List can achieve efficient cache operations. It also provides practical experience with pointer manipulation, data structure design, and performance optimization in Java.

## 👨‍💻 Author

**Sahir Ahmad**

GitHub: [@Sahirahmad-12](https://github.com/Sahirahmad-12)

---

⭐ If you find this project useful, consider giving it a star!
