# Sorting Algorithms Comparison

## 1. Why Compare Algorithms?

### 1.1 Time:
- The faster an algorithm sorts the data, the better it is.

### 1.2 Memory:
- The less memory an algorithm uses, the better it is.

---

## 2. Sorting Algorithms

### 2.1 Selection Sort

**How it Works:**
- Start with the first element. Find the smallest element in the list and swap it with the first one.
- Repeat this for the remaining elements until the list is sorted.

**Example:**
Given the list `[33, 27, 14, 10]`:
- **Step 1:** Compare 33 with the other elements. The smallest is 14, so swap 33 and 14.  
  Now the list looks like this: `[14, 27, 33, 10]`.
- **Step 2:** Now, compare 27 with the remaining elements. The smallest is 10, so swap 27 and 10.  
  The list is now: `[14, 10, 33, 27]`.
- **Step 3:** Compare 33 with 27, and swap them.  
  The final sorted list is: `[10, 14, 27, 33]`.

**Time Complexity:**
- **Best Case:** O(n²)
- **Average Case:** O(n²)
- **Worst Case:** O(n²)
- **Space Complexity:** O(1)

---

### 2.2 Bubble Sort

**How it Works:**
- Compare two adjacent elements. If the first is bigger than the second, swap them.
- Continue doing this until the list is sorted.

**Example:**
Given the list `[5, 1, 4, 2, 8]`:
- **Step 1:** Compare 5 and 1. Since 5 > 1, swap them → `[1, 5, 4, 2, 8]`.
- **Step 2:** Compare 5 and 4. Since 5 > 4, swap them → `[1, 4, 5, 2, 8]`.
- **Step 3:** Compare 5 and 2. Since 5 > 2, swap them → `[1, 4, 2, 5, 8]`.
- **Step 4:** Compare 5 and 8. Since 5 < 8, do nothing.
- **Step 5:** The list is not fully sorted yet, so repeat the process until the entire list is sorted:
  The sorted list is: `[1, 2, 4, 5, 8]`.

**Time Complexity:**
- **Best Case:** O(n)
- **Average Case:** O(n²)
- **Worst Case:** O(n²)
- **Space Complexity:** O(1)

---

### 2.3 Insertion Sort

**How it Works:**
- Start with the second element. Compare it with the first element and place it in the correct position.
- Repeat this for all elements.

**Example:**
Given the list `[3, 4, 2, 1]`:
- **Step 1:** Start with the second element (4). Compare it with the first element (3). 4 is greater, so leave it.  
  The list is still: `[3, 4, 2, 1]`.
- **Step 2:** Move to the next element (2). Compare 2 with 4 and move 4 to the right → `[3, 4, 4, 1]`.  
  Now, compare 2 with 3, and move 3 to the right → `[3, 3, 4, 1]`.  
  Place 2 in the first position → `[2, 3, 4, 1]`.
- **Step 3:** Move to the next element (1). Compare 1 with 4, move 4 to the right → `[2, 3, 4, 4]`.  
  Then compare 1 with 3, move 3 to the right → `[2, 3, 3, 4]`.  
  Finally, compare 1 with 2, move 2 to the right → `[2, 2, 3, 4]`.  
  Place 1 in the first position → `[1, 2, 3, 4]`.

**Time Complexity:**
- **Best Case:** O(n)
- **Average Case:** O(n²)
- **Worst Case:** O(n²)
- **Space Complexity:** O(1)

---

### 2.4 Merge Sort

**How it Works:**
- Divide the list into two smaller lists, then divide them again.
- Once each list has one element, merge the lists back in order.

**Example:**
Given the list `[38, 27, 43, 3, 9, 82, 10]`:
- **Step 1:** Divide the list into two halves:  
  Left half: `[38, 27, 43]`  
  Right half: `[3, 9, 82, 10]`
- **Step 2:** Divide these halves into smaller lists:  
  Left half: `[38]`, `[27]`, `[43]`  
  Right half: `[3]`, `[9]`, `[82]`, `[10]`
- **Step 3:** Merge the smallest lists into ordered pairs:  
  Left half: `[27, 38, 43]`  
  Right half: `[3, 9, 10, 82]`
- **Step 4:** Merge the two ordered halves into one sorted list:  
  The final sorted list is: `[3, 9, 10, 27, 38, 43, 82]`.

**Time Complexity:**
- **Best Case:** O(n log n)
- **Average Case:** O(n log n)
- **Worst Case:** O(n log n)
- **Space Complexity:** O(n)

---

## 3. Summary Table: Time Complexity Comparison

| **Algorithm**       | **Best Case**   | **Average Case** | **Worst Case**   | **Space Complexity** |
|---------------------|-----------------|------------------|------------------|----------------------|
| **Selection Sort**   | O(n²)           | O(n²)            | O(n²)            | O(1)                 |
| **Bubble Sort**      | O(n)            | O(n²)            | O(n²)            | O(1)                 |
| **Insertion Sort**   | O(n)            | O(n²)            | O(n²)            | O(1)                 |
| **Merge Sort**       | O(n log n)      | O(n log n)       | O(n log n)       | O(n)                 |

---

## 4. Summary in Main Points

- **Selection Sort:**  
  - Simple to understand but inefficient (O(n²) time complexity).
  - Uses very little extra memory (O(1)).

- **Bubble Sort:**  
  - Simple and works by comparing adjacent elements.
  - Best case can be O(n) when the list is already sorted, but worst case is O(n²).

- **Insertion Sort:**  
  - Efficient for small or nearly sorted lists.
  - Time complexity can be O(n) for best cases and O(n²) for worst cases.

- **Merge Sort:**  
  - Efficient and divides the list into smaller parts before merging them in order.
  - Always has O(n log n) time complexity and needs extra space (O(n)).

