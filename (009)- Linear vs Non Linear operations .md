### **1. Arrays**  
Arrays are a **linear** data structure where elements are stored in a contiguous block of memory.

#### Operations:
- **Accessing an element**:  
  - **Operation**: Accessing an element by index (e.g., `arr[i]`).
  - **Time Complexity**: **O(1)** (constant time).
  - **Linear or Non-linear**: **Linear**.

- **Insertion at the end**:  
  - **Operation**: Inserting an element at the last position.
  - **Time Complexity**: **O(1)** (amortized time for dynamic arrays).
  - **Linear or Non-linear**: **Linear**.

- **Insertion at a specific position**:  
  - **Operation**: Inserting an element at a specific index.
  - **Time Complexity**: **O(n)**. Elements need to be shifted.
  - **Linear or Non-linear**: **Linear**.

- **Deletion**:  
  - **Operation**: Deleting an element.
  - **Time Complexity**: **O(n)**. Elements after the deleted one are shifted.
  - **Linear or Non-linear**: **Linear**.

- **Searching**:  
  - **Operation**: Searching for an element by value.
  - **Time Complexity**: **O(n)** (linear search).
  - **Linear or Non-linear**: **Linear**.

---

### **2. Stacks**  
A **stack** follows the **Last In, First Out (LIFO)** principle.

#### Operations:
- **Push (insert an element)**:  
  - **Operation**: Add an element to the top of the stack.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Pop (remove the top element)**:  
  - **Operation**: Remove the top element from the stack.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Peek (get the top element without removing it)**:  
  - **Operation**: View the top element of the stack.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Check if empty**:  
  - **Operation**: Checking if the stack is empty.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Size**:  
  - **Operation**: Getting the number of elements in the stack.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Top**:  
  - **Operation**: Get the top element without removing it (this is the same as **peek**).
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

---

### **3. Queues**  
A **queue** follows the **First In, First Out (FIFO)** principle.

#### Operations:
- **Enqueue (insert an element)**:  
  - **Operation**: Add an element to the end of the queue.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Dequeue (remove the front element)**:  
  - **Operation**: Remove the front element from the queue.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Peek (get the front element without removing it)**:  
  - **Operation**: View the front element of the queue.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Check if empty**:  
  - **Operation**: Checking if the queue is empty.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Size**:  
  - **Operation**: Getting the number of elements in the queue.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Search**:  
  - **Operation**: Search for a specific element in the queue.
  - **Time Complexity**: **O(n)**. You may need to traverse the entire queue.
  - **Linear or Non-linear**: **Linear**.

---

### **4. Linked Lists**  
A **linked list** is a linear data structure where each element (node) points to the next element.

#### Operations:
- **Insertion at the beginning**:  
  - **Operation**: Insert a node at the start of the list.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Insertion at the end**:  
  - **Operation**: Insert a node at the end of the list.
  - **Time Complexity**: **O(n)**. You may need to traverse the entire list.
  - **Linear or Non-linear**: **Linear**.

- **Insertion at a specific position**:  
  - **Operation**: Insert a node at a specific index.
  - **Time Complexity**: **O(n)**. You have to traverse the list to find the desired position.
  - **Linear or Non-linear**: **Linear**.

- **Deletion at the beginning**:  
  - **Operation**: Remove the first node.
  - **Time Complexity**: **O(1)**.
  - **Linear or Non-linear**: **Linear**.

- **Deletion at the end**:  
  - **Operation**: Remove the last node.
  - **Time Complexity**: **O(n)**.
  - **Linear or Non-linear**: **Linear**.

- **Searching**:  
  - **Operation**: Search for a specific node by value.
  - **Time Complexity**: **O(n)**. You may need to traverse the entire list.
  - **Linear or Non-linear**: **Linear**.

- **Top**:  
  - **Operation**: View the first element (similar to peek in a stack or queue).
  - **Time Complexity**: **O(1)**. You just need to check the first node.
  - **Linear or Non-linear**: **Linear**.

---

### **5. Trees**  
A **tree** is a **non-linear** data structure with nodes connected by edges.

#### Operations:
- **Insertion**:  
  - **Operation**: Add a node to the tree.
  - **Time Complexity**: **O(log n)** for balanced trees, **O(n)** for unbalanced trees.
  - **Linear or Non-linear**: **Non-linear**.

- **Deletion**:  
  - **Operation**: Remove a node from the tree.
  - **Time Complexity**: **O(log n)** for balanced trees, **O(n)** for unbalanced trees.
  - **Linear or Non-linear**: **Non-linear**.

- **Traversal (In-order, Pre-order, Post-order)**:  
  - **Operation**: Visit all nodes in the tree.
  - **Time Complexity**: **O(n)**.
  - **Linear or Non-linear**: **Non-linear**.

- **Searching**:  
  - **Operation**: Search for a node by value.
  - **Time Complexity**: **O(log n)** for balanced trees, **O(n)** for unbalanced trees.
  - **Linear or Non-linear**: **Non-linear**.

- **Top**:  
  - **Operation**: Get the root element (top node).
  - **Time Complexity**: **O(1)**. The root is directly accessible.
  - **Linear or Non-linear**: **Non-linear**.

---

### **6. Graphs**  
A **graph** is a **non-linear** data structure where nodes (vertices) are connected by edges.

#### Operations:
- **Insertion (nodes and edges)**:  
  - **Operation**: Add a node or edge to the graph.
  - **Time Complexity**: **O(1)** for adding a node, **O(1)** or **O(V)** (where V is the number of vertices) for adding an edge depending on representation (adjacency list vs adjacency matrix).
  - **Linear or Non-linear**: **Non-linear**.

- **Deletion (nodes and edges)**:  
  - **Operation**: Remove a node or edge.
  - **Time Complexity**: **O(1)** for adjacency list (deleting an edge), **O(V + E)** for adjacency matrix (where E is the number of edges).
  - **Linear or Non-linear**: **Non-linear**.

- **Traversal (BFS, DFS)**:  
  - **Operation**: Visit all nodes in the graph.
  - **Time Complexity**: **O(V + E)**, where V is the number of vertices and E is the number of edges.
  - **Linear or Non-linear**: **Non-linear**.

- **Searching**:  
  - **Operation**: Find a specific node or path.
  - **Time Complexity**: **O(V + E)**, using DFS or BFS.
  - **Linear or Non-linear**: **Non-linear**.

- **Top**:  
  - **Operation**: In a directed acyclic graph (DAG), you might want to get the top-most element (a node with no incoming edges).
  - **Time Complexity**: **O(1)** if you already know the top node (e.g., the source node in a topological order).
  - **Linear or Non-linear**: **Non-linear**.

---

### **Summary Table of Operations, Time Complexities, and Added Operations:**

| **Operation**                      | **Array** | **Stack** | **Queue** | **Linked List** | **Tree**   | **Graph**  |
|-------------------------------------|-----------|-----------|-----------|-----------------|------------|------------|
| **Access**                          | O(1)      | O(1)      | O(1)      | O(n)            | O(n)       | O(n)       |
| **Insertion at beginning**          | O(n)      | O(1)      | O(1)      | O(1)            | O(log n)   | O(1)       |
| **Insertion at end**                | O(1)      | O(1)      | O(1)      | O(n)            | O(log n)   | O(1)       |
| **Insertion at specific position**  | O(n)      | O(1)      | O(1)      | O(n)            | O(log n)   | O(1)       |
| **Deletion at beginning**           | O(n)      | O(1)      | O(1)      | O(1)            | O(log n)   | O(V+E)     |
| **Deletion at end**                 | O(n)      | O(1)      | O(1)      | O(n)            | O(log n)   | O(V+E)     |
| **Searching**                       | O(n)      | O(n)      | O(n)      | O(n)            | O(log n)   | O(V+E)     |
| **Traversal**                       | O(n)      | O(n)      | O(n)      | O(n)            | O(n)       | O(V+E)     |
| **Top**                             | O(1)      | O(1)      | O(1)      | O(1)            | O(1)       | O(1)       |

---  
