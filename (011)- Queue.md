![image](https://github.com/user-attachments/assets/96c87401-79f5-4cf4-a805-bcaa08709ce9)

### **What is a Queue?**  
A **queue** is a way to organize data. It is like a line of people waiting for a service. You can only add items at the **end** of the queue and remove items from the **front**.

A queue follows the **First In, First Out (FIFO)** rule:
- The first item you put in is the first item you take out.

---

### **How Does a Queue Work?**  
1. You can only add items to the **end** of the queue.
2. You can only remove items from the **front** of the queue.
3. The order in which items are added and removed is important.

---

### **Important Features of a Queue:**
- **FIFO Rule:** The first item added is the first one removed.
- **Front and Rear:** You add items at the rear and remove them from the front.
- **Restricted Access:** You cannot remove items from the middle of the queue.

---

### **Real-Life Examples of a Queue:**
1. **Queue at a Bank:**  
   - People join the queue at the rear and are served in order from the front.

2. **Printer Queue:**  
   - Print jobs are processed in the order they are added to the queue.

3. **Customer Service:**  
   - Requests are handled in the order they are received.


---

### **Front and Rear of a Queue:**

- **Front**: The **front** of the queue is where the first item is. When we perform a **dequeue** operation, we remove the item from the front.
- **Rear**: The **rear** of the queue is where new items are added. When we perform an **enqueue** operation, we add an item to the rear.

This means that the **front** is where items are removed, and the **rear** is where items are added, maintaining the FIFO (First In, First Out) rule.

---


### **What Can You Do with a Queue?**
A queue has several actions you can perform:
1. **`enqueue(item):`** Add an item to the end of the queue.
2. **`dequeue():`** Remove and return the item from the front of the queue.
3. **`peek():`** Look at the front item without removing it.
4. **`is_empty():`** Check if the queue is empty.
5. **`size():`** Find out how many items are in the queue.

---

### **Python Example of a Queue:**

Here’s an example to create and use a queue in Python:

```python
class Queue:
    def __init__(self):
        self.items = []  # Create an empty list for the queue

    def enqueue(self, item):
        """Add an item to the end of the queue."""
        self.items.append(item)

    def dequeue(self):
        """Remove and return the item from the front of the queue."""
        if not self.is_empty():
            return self.items.pop(0)
        else:
            return "The queue is empty."

    def peek(self):
        """Look at the front item without removing it."""
        if not self.is_empty():
            return self.items[0]
        else:
            return "The queue is empty."

    def is_empty(self):
        """Check if the queue is empty."""
        return len(self.items) == 0

    def size(self):
        """Find out how many items are in the queue."""
        return len(self.items)
```

---

### **Using the Queue Class:**

```python
# Create a new queue
my_queue = Queue()

# Add items to the queue
my_queue.enqueue("A")
my_queue.enqueue("B")
my_queue.enqueue("C")

# Check the front item
print("Front item:", my_queue.peek())  # Output: A

# Remove items from the queue
print("Removed:", my_queue.dequeue())   # Output: A
print("Removed:", my_queue.dequeue())   # Output: B

# Check the size of the queue
print("Queue size:", my_queue.size())  # Output: 1

# Check if the queue is empty
print("Is queue empty?", my_queue.is_empty())  # Output: False
```

---

### **Summary:**
- **Queue:** A FIFO structure, where you add items at the rear and remove them from the front.
- **Real-life examples:** Bank lines, printer queues, customer service lines.
- **Python Example:** Shows how to add, remove, and check items in a queue using simple methods.

