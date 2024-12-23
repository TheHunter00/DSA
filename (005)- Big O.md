

# Big O Notation 

Big O is a way to describe how the time to run an algorithm changes when we increase the size of the input. It helps us understand how fast or slow an algorithm is. Let’s look at the most common Big O notations in simple words.

---

### **1. O(1) – Constant Time**
- **What it means:** The algorithm takes the same time no matter how big the input is.
- **Example in Python:**

```python
def add_to_list(linked_list, node):
    linked_list.append(node)  # This always takes the same time
    return linked_list
```

- **Real-world example:** If you add an item to your shopping cart, it takes the same time whether you have 1 item or 100 items.

---

### **2. O(n) – Linear Time**
- **What it means:** The time to complete the task grows directly with the size of the input. If you double the input, the time doubles.
- **Example in Python:**

```python
def print_list(arr):
    for item in arr:
        print(item)  # Prints each item one by one
```

- **Real-world example:** If you have a list of 10 items, it will take twice as long to print them as it would if you have 5 items.

---

### **3. O(log n) – Logarithmic Time**
- **What it means:** The time grows slowly even as the input size increases.
- **Example in Python:**

```python
def binary_search(arr, target):
    low = 0
    high = len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1
```

- **Real-world example:** Searching for a book in a library by dividing the books in half each time. It takes fewer steps than looking at every single book.

---

### **4. O(n log n) – Linearithmic Time**
- **What it means:** This is slower than O(n), but faster than O(n²). It happens when the algorithm divides the problem into smaller parts and combines them.
- **Example in Python:**

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)

def merge(left, right):
    result = []
    while left and right:
        if left[0] < right[0]:
            result.append(left.pop(0))
        else:
            result.append(right.pop(0))
    result.extend(left)
    result.extend(right)
    return result
```

- **Real-world example:** Sorting a stack of books by splitting them into smaller stacks, sorting those, and then combining them back together.

---

### **5. O(n²) – Quadratic Time**
- **What it means:** The time increases very quickly when the input size grows. This happens when there are loops inside other loops.
- **Example in Python:**

```python
def bubble_sort(arr):
    for i in range(len(arr)):
        for j in range(len(arr) - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]  # Swap elements
    return arr
```

- **Real-world example:** If you want to compare each item on your shopping list with every other item, it takes longer as the list gets bigger.

---

### **6. O(n³) – Cubic Time**
- **What it means:** The time grows even faster. This happens when there are 3 loops inside each other.
- **Example in Python:**

```python
def cubic_example(arr):
    for i in arr:
        for j in arr:
            for k in arr:
                print(i, j, k)  # This takes a lot of time!
```

- **Real-world example:** If you compare every item with every other item, but also compare groups of items together—this takes even longer.

---

### **7. O(2^n) – Exponential Time**
- **What it means:** The time doubles every time the input size increases by 1. This is very slow for large inputs.
- **Example in Python:**

```python
def exponential_example(n):
    if n <= 0:
        return
    exponential_example(n - 1)  # Calls itself twice for each number
    exponential_example(n - 1)
```

- **Real-world example:** Trying all possible combinations of a group of items. As you add more items, the number of combinations doubles each time.

---

### **8. O(n!) – Factorial Time**
- **What it means:** The time grows extremely fast. It happens when the algorithm looks at all possible orders of the input.
- **Example in Python:**

```python
import itertools

def factorial_example(arr):
    return list(itertools.permutations(arr))  # All possible orders of items
```

- **Real-world example:** If you have 3 items, there are 6 possible ways to arrange them. With 4 items, there are 24 ways. The more items you have, the faster the number of possible orders grows.

---

### **Rate of Growth Summary**

Here’s a simple table comparing how fast each Big O grows:

| Big O Notation | Time Growth      | Example                             |
|-----------------|------------------|-------------------------------------|
| **O(1)**        | Constant         | Adding an item to a list           |
| **O(log n)**    | Grows slowly     | Binary search                      |
| **O(n)**        | Grows directly   | Printing each item in a list       |
| **O(n log n)**  | Grows faster than linear | Merge sort, Quick sort           |
| **O(n²)**       | Grows quickly    | Bubble sort, Selection sort        |
| **O(n³)**       | Grows very fast  | Triple nested loops                |
| **O(2^n)**      | Doubles every time | Brute-force solutions             |
| **O(n!)**       | Grows extremely fast | Arranging all items              |

---

### **Summary:**
- **O(1)**: Takes the same time no matter the input size.
- **O(log n)**: Grows slowly as input size increases.
- **O(n)**: Takes more time as the input grows, but not too much.
- **O(n log n)**: Takes more time than O(n), but less than O(n²).
- **O(n²)**: Grows quickly, takes a lot of time for big inputs.
- **O(n³)**: Grows very fast, with 3 loops inside each other.
- **O(2^n)**: Grows very quickly, doubles with each increase in input size.
- **O(n!)**: Extremely fast growth, used for finding all possible orders of input.


```

