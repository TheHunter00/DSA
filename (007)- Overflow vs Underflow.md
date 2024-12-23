

### **What is Overflow?**  
**Overflow** happens when you try to add (insert) an item to a data structure, but there is **no more space** left.  

#### Example in Real Life:  
Imagine a glass of water:  
- If you pour more water than the glass can hold, the extra water spills out.  
- This is like overflow in a data structure.  

#### Example in a Stack:  
- A stack has a fixed size (e.g., it can hold 5 items).  
- If you try to push a 6th item, you will get an **overflow error** because the stack is full.  

---

### **What is Underflow?**  
**Underflow** happens when you try to remove (delete) an item from a data structure, but the structure is **already empty**.  

#### Example in Real Life:  
Imagine a jar of cookies:  
- If the jar is empty and you try to take a cookie, there is nothing to take.  
- This is like underflow in a data structure.  

#### Example in a Stack:  
- If a stack has no items and you try to pop an item, you will get an **underflow error** because the stack is empty.  

---

### **Comparison Between Overflow and Underflow:**  

| **Feature**        | **Overflow**                              | **Underflow**                            |
|---------------------|-------------------------------------------|------------------------------------------|
| **When It Happens** | When you try to add to a full structure   | When you try to remove from an empty one |
| **Cause**           | No more space in the data structure       | No items left in the data structure      |
| **Example**         | Pushing an item to a full stack           | Popping an item from an empty stack      |

---

### **How to Prevent Overflow and Underflow:**  
1. **For Overflow:**  
   - Check if the data structure is full before adding an item.  
   - Example: In a stack, check the size before calling `push()`.  

2. **For Underflow:**  
   - Check if the data structure is empty before removing an item.  
   - Example: In a stack, check if it’s empty before calling `pop()`.  
