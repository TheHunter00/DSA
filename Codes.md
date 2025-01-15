<div align="center">
  <img src="https://github.com/user-attachments/assets/b84abbed-a43f-45a5-995e-a67437cb9ce3" alt="Centered Image">
</div>

### **1. Stack Implementation**
```python
class Stack(object):
    def __init__(self, max):
        self.stackList = [None] * max  # Create a list with a fixed size
        self.top = -1  # Start with an empty stack

    def isEmpty(self):
        return self.top < 0  # If top is -1, the stack is empty

    def push(self, item):
        if self.isFull():  # Check if the stack is full
            raise Exception("Stack Overflow")  # Show error if full
        self.top += 1  # Move top pointer up
        self.stackList[self.top] = item  # Add item to the stack

    def pop(self):
        if self.isEmpty():  # Check if the stack is empty
            raise Exception("Stack Underflow")  # Show error if empty
        top = self.stackList[self.top]  # Save the top item
        self.stackList[self.top] = None  # Remove the item
        self.top -= 1  # Move top pointer down
        return top  # Return the removed item

    def peek(self):
        if self.isEmpty():  # Check if the stack is empty
            raise Exception("Stack is empty")  # Show error if empty
        return self.stackList[self.top]  # Return the top item

    def len(self):
        return self.top + 1  # Return the number of items in the stack

    def isFull(self):
        return self.top >= len(self.stackList) - 1  # Check if the stack is full
```

---

### **2. Queue Implementation**
```python
class Queue(object):
    def __init__(self, size):
        self.maxSize = size  # Maximum size of the queue
        self.items = [None] * size  # Create a list with a fixed size
        self.front = 1  # Pointer for the first item
        self.rear = 0  # Pointer for the last item
        self.nItems = 0  # Number of items in the queue

    def enqueue(self, item):
        if self.isFull():  # Check if the queue is full
            raise Exception("Queue Overflow")  # Show error if full
        self.rear += 1  # Move rear pointer forward
        if self.rear == self.maxSize:  # Wrap around if needed
            self.rear = 0
        self.items[self.rear] = item  # Add the item to the queue
        self.nItems += 1  # Increase item count
        return True

    def dequeue(self):
        if self.isEmpty():  # Check if the queue is empty
            raise Exception("Queue Underflow")  # Show error if empty
        frontItem = self.items[self.front]  # Save the front item
        self.items[self.front] = None  # Remove the item
        self.front += 1  # Move front pointer forward
        if self.front == self.maxSize:  # Wrap around if needed
            self.front = 0
        self.nItems -= 1  # Decrease item count
        return frontItem  # Return the removed item

    def peek(self):
        if self.isEmpty():  # Check if the queue is empty
            return None  # No item to show
        else:
            return self.items[self.front]  # Show the front item

    def isEmpty(self):
        return self.nItems == 0  # True if there are no items

    def isFull(self):
        return self.nItems == self.maxSize  # True if the queue is full

    def queueLength(self):
        return self.nItems  # Return the number of items in the queue
```

---

### **3. Priority Queue Implementation**
```python
class PriorityQueue(object):
    def __init__(self, size, pri=lambda x: x):
        self.maxSize = size  # Maximum size of the queue
        self.queue = [None] * size  # Create a list with a fixed size
        self.pri = pri  # Function to get item priority
        self.nItems = 0  # Number of items in the queue

    def insert(self, item):
        if self.isFull():  # Check if the queue is full
            raise Exception("Queue Overflow")  # Show error if full
        j = self.nItems - 1  # Start checking from the last item
        while j >= 0 and (self.pri(item) >= self.pri(self.queue[j])):
            self.queue[j + 1] = self.queue[j]  # Move items to make space
            j -= 1  # Check the next item
        self.queue[j + 1] = item  # Add the new item in the right place
        self.nItems += 1  # Increase item count
        return True

    def remove(self):
        if self.isEmpty():  # Check if the queue is empty
            raise Exception("Queue Underflow")  # Show error if empty
        self.nItems -= 1  # Decrease item count
        front = self.queue[self.nItems]  # Save the first item
        self.queue[self.nItems] = None  # Remove the item
        return front  # Return the removed item

    def peek(self):
        return None if self.isEmpty() else self.queue[self.nItems - 1]  # Show the highest priority item

    def isEmpty(self):
        return self.nItems == 0  # True if no items are in the queue

    def isFull(self):
        return self.nItems == self.maxSize  # True if the queue is full

    def len(self):
        return self.nItems  # Return the number of items
```
### **4. Linked List Implementation**
```python
class Link(object):
    def __init__(self, data, next=None):
        self.data = data  # Store the data
        self.next = next  # Link to the next node

    def isLast(self):
        return self.next is None  # True if there is no next node

class LinkedList(object):
    def __init__(self):
        self.first = None  # Start with an empty list

    def isEmpty(self):
        return self.first is None  # True if there are no nodes

    def insert(self, datum):
        link = Link(datum, self.first)  # Create a new node at the start
        self.first = link  # Make the new node the first one

    def deleteFirst(self):
        if self.isEmpty():  # Check if the list is empty
            raise Exception("Cannot delete first of Empty list")  # Show error
        first = self.first  # Get the first node
        self.first = first.next  # Move to the next node
        return first.data  # Return the data of the removed node

    def traverse(self, func=print):
        link = self.first  # Start at the first node
        while link is not None:  # Go through each node
            func(link.data)  # Apply the function to the node's data
            link = link.next  # Move to the next node

    def len(self):
        count = 0  # Start with 0 nodes
        link = self.first  # Start at the first node
        while link is not None:  # Count each node
            count += 1
            link = link.next  # Move to the next node
        return count  # Return the total number of nodes
```

---

### **5. Doubly Linked List Implementation**
```python
class Link(LinkedList.Link):
    def __init__(self, datum, next=None, previous=None):
        self.data = datum  # Store the data
        self.next = next  # Link to the next node
        self.previous = previous  # Link to the previous node

    def getPrevious(self):
        return self.previous  # Return the previous node

    def setPrevious(self, link):
        if link is None or isinstance(link, Link):  # Check if valid link
            self.previous = link  # Set the previous link
        else:
            raise Exception("Previous link must be Link or None")  # Show error

class DoublyLinkedList(LinkedList):
    def __init__(self):
        self.first = None  # Start with no nodes
        self.last = None  # Keep track of the last node

    def insertFirst(self, datum):
        link = Link(datum, next=self.first)  # Create a new node at the start
        if self.isEmpty():  # If the list is empty
            self.last = link  # Make this node the last one too
        else:
            self.first.setPrevious(link)  # Link the old first node to the new one
        self.first = link  # Make the new node the first one

    def insertLast(self, datum):
        link = Link(datum, previous=self.last)  # Create a new node at the end
        if self.isEmpty():  # If the list is empty
            self.first = link  # Make this node the first one too
        else:
            self.last.setNext(link)  # Link the old last node to the new one
        self.last = link  # Make the new node the last one
```

---

### **6. Binary Search Tree (BST) Implementation**
```python
class BinarySearchTree(object):
    class __Node(object):
        def __init__(self, key, data, left=None, right=None):
            self.key = key  # Key to compare nodes
            self.data = data  # Data to store
            self.leftChild = left  # Left child
            self.rightChild = right  # Right child

        def __str__(self):
            return "{" + str(self.key) + ", " + str(self.data) + "}"  # For easy printing

    def __init__(self):
        self.__root = None  # Start with an empty tree

    def isEmpty(self):
        return self.__root is None  # True if there are no nodes

    def insert(self, key, data):
        node, parent = self.__find(key)  # Find where to insert
        if node:  # If the key already exists
            node.data = data  # Update its data
            return False  # No new node added
        if parent is None:  # If the tree is empty
            self.__root = self.__Node(key, data)  # Create the root node
        elif key < parent.key:  # If key is smaller, go left
            parent.leftChild = self.__Node(key, data)
        else:  # If key is larger, go right
            parent.rightChild = self.__Node(key, data)
        return True

    def inOrderTraverse(self, function=print):
        self.__inOrderTraverse(self.__root, function=function)  # Start traversal

    def __inOrderTraverse(self, node, function):
        if node:  # If there is a node
            self.__inOrderTraverse(node.leftChild, function)  # Go left
            function(node)  # Process the node
            self.__inOrderTraverse(node.rightChild, function)  # Go right
```

---

### **7. Graph Implementation**
```python
class Graph(object):
    def __init__(self):
        self.__vertices = []  # List of all vertices
        self.__adjList = {}  # Dictionary for adjacency list

    def addVertex(self, vertex):
        self.__vertices.append(vertex)  # Add a vertex
        self.__adjList[vertex] = []  # Initialize its adjacency list

    def addEdge(self, A, B):
        self.__adjList[A].append(B)  # Add B to A's adjacency list
        self.__adjList[B].append(A)  # Add A to B's adjacency list (undirected)

    def getAdjacentVertices(self, vertex):
        return self.__adjList.get(vertex, [])  # Return the list of neighbors
```
