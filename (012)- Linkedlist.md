![image](https://github.com/user-attachments/assets/bd097b87-32b4-4e6c-a521-a186a8bd2703)

### **What is a Linked List?**
A **linked list** is a linear data structure where each element (node) contains:
- **Data**: The value or content.
- **Next/Prev**: A reference to the next (and sometimes previous) node.

This structure allows efficient memory allocation since nodes aren’t stored in contiguous memory locations.

---

### **Types of Linked Lists:**

#### **1. Singly Linked List:**
- **Structure**:  
  ```
  [Data | Next] -> [Data | Next] -> [Data | Next] -> null
  ```
- **Operations**: Insertion and deletion at the beginning are O(1). Traversing and operations at the middle or end take O(n).

#### **2. Doubly Linked List:**
- **Structure**:  
  ```
  null <- [Prev | Data | Next] <-> [Prev | Data | Next] <-> [Prev | Data | Next] -> null
  ```
- **Operations**: Efficient for insertion/deletion at both ends due to the additional **Prev** pointer.

---

### **Advantages of Linked Lists:**
- **Dynamic Size**: Can grow or shrink as needed.
- **Efficient Insertions/Deletions**: Especially at the beginning or middle.

### **Disadvantages of Linked Lists:**
- **Memory Overhead**: Extra memory required for pointers.
- **No Random Access**: Must traverse the list for access.

---

### **When to Use Linked Lists:**
- Frequent insertion/deletion, especially from the beginning or middle.
- When memory usage is dynamic and flexible.

---

### **Python Code Examples:**

#### **Singly Linked List Operations:**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

    def display(self):
        current = self.head
        while current:
            print(current.data, end=" -> ")
            current = current.next
        print("None")

    def addAtBeginning(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    def removeAtBeginning(self):
        if self.head:
            self.head = self.head.next

    def removeAtEnd(self):
        if self.head:
            if not self.head.next:
                self.head = None
            else:
                current = self.head
                while current.next:
                    if not current.next.next:
                        current.next = None
                        break
                    current = current.next
```

---

#### **Doubly Linked List Operations:**

```python
class DNode:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = DNode(data)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node
            new_node.prev = current

    def display_forward(self):
        current = self.head
        while current:
            print(current.data, end=" <-> ")
            current = current.next
        print("None")

    def display_backward(self):
        current = self.head
        while current and current.next:
            current = current.next
        while current:
            print(current.data, end=" <-> ")
            current = current.prev
        print("None")

    def removeAtBeginning(self):
        if self.head:
            if self.head.next:
                self.head.next.prev = None
            self.head = self.head.next

    def removeAtEnd(self):
        if self.head:
            if not self.head.next:
                self.head = None
            else:
                current = self.head
                while current.next:
                    current = current.next
                current.prev.next = None
```

---

### **Linked List Operations Recap:**
- **add(item)**: Adds a new node with the given item.
- **remove()**: Removes a node from the list.
- **search(item)**: Searches for an item in the list, returns `True` if found, otherwise `False`.
- **is_empty()**: Checks if the list is empty, returns `True` or `False`.
- **size()**: Returns the number of elements in the list.
- **addAtBeginning(item)**: Adds a new node at the start of the list.
- **addAtEnd(item)**: Adds a new node at the end of the list.
- **add(item, pos)**: Adds a node at a specified position.
- **removeAtBeginning()**: Removes the first node.
- **removeAtEnd()**: Removes the last node.
- **removeAt(pos)**: Removes a node at a specific position.

---

