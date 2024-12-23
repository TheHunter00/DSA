### **What is a Stack?**  
A **stack** is a way to organize data. It is like a real-life stack of plates or books. You can add items to the top of the stack, and you can take items from the top of the stack.  

A stack follows a rule called **Last In, First Out (LIFO)**:  
- The last item you put in is the first item you take out.  
- For example, if you add books to a stack in this order: **Book A, Book B, Book C**, you will remove them in the opposite order: **Book C, Book B, Book A**.  

---

### **How Does a Stack Work?**  
1. You can only add or remove items from the **top** of the stack.  
2. The first item you add will stay at the **bottom** of the stack until all the other items are removed.  
3. You cannot take an item from the middle or the bottom.

---

### **Important Features of a Stack:**  
- **LIFO Rule:** The last thing you add is the first thing you take out.  
- **Top Item:** You can only work with the item at the top of the stack.  
- **Restricted Access:** You cannot directly access items in the middle or at the bottom.

---

### **Real-Life Examples of a Stack:**  
1. **Stack of Plates:**  
   - When you add plates, you place them on top.  
   - When you take a plate, you take the top one first.  

2. **Web Browsers:**  
   - When you visit a page, it is added to a stack.  
   - Clicking the “Back” button removes the last page from the stack.  

3. **Undo in Text Editors:**  
   - The last change you made is stored in a stack.  
   - You can undo changes one by one, starting with the last one.

---

### **What Can You Do with a Stack?**  
A stack has several actions you can perform:  
1. **`push(item):`** Add an item to the top of the stack.  
2. **`pop():`** Remove the top item from the stack and return it.  
3. **`peek():`** Look at the top item without removing it.  
4. **`is_empty():`** Check if the stack is empty.  
5. **`size():`** Find out how many items are in the stack.

---

### **Python Example of a Stack:**

Here is a simple example to create and use a stack in Python:  

```python
class Stack:
    def __init__(self):
        self.items = []  # Create an empty list for the stack

    def push(self, item):
        """Add an item to the top of the stack."""
        self.items.append(item)

    def pop(self):
        """Remove and return the top item from the stack."""
        if not self.is_empty():
            return self.items.pop()
        else:
            return "The stack is empty."

    def peek(self):
        """Look at the top item without removing it."""
        if not self.is_empty():
            return self.items[-1]
        else:
            return "The stack is empty."

    def is_empty(self):
        """Check if the stack is empty."""
        return len(self.items) == 0

    def size(self):
        """Find out how many items are in the stack."""
        return len(self.items)
```

---

### **Using the Stack Class:**

```python
# Create a new stack
my_stack = Stack()

# Add items to the stack
my_stack.push("A")
my_stack.push("B")
my_stack.push("C")

# Check the top item
print("Top item:", my_stack.peek())  # Output: C

# Remove items from the stack
print("Removed:", my_stack.pop())   # Output: C
print("Removed:", my_stack.pop())   # Output: B

# Check the size of the stack
print("Stack size:", my_stack.size())  # Output: 1

# Check if the stack is empty
print("Is stack empty?", my_stack.is_empty())  # Output: False
```

