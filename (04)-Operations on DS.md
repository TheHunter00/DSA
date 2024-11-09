

## **Operations on Data Structures:**

### 1. **Traversing (التصفح)**

**التصفح** يعني إنك تمر على كل عنصر في هيكل البيانات بشكل مرتب. الهدف من التصفح هو إنهاء كل العناصر في الهيكل، زي مثلاً لما تعمل **طباعة** لكل العناصر.

#### **Example in Python**:

**For an Array**:
```python
arr = [10, 20, 30, 40, 50]
for item in arr:
    print(item)  # ده هيتطبع كل عنصر في المصفوفة واحد واحد
```

**For a Linked List**:
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def traverse(self):
        current = self.head
        while current:
            print(current.data)
            current = current.next

# Example usage
ll = LinkedList()
ll.head = Node(10)
ll.head.next = Node(20)
ll.head.next.next = Node(30)

ll.traverse()  # هيتطبع 10, 20, 30
```

---

### 2. **Searching (البحث)**

**البحث** هو العملية اللي بتدور فيها على عنصر معين داخل هيكل البيانات. فيه طرق مختلفة للبحث، زي **البحث الخطي** و **البحث الثنائي**.

#### **Example in Python**:

**For an Array** (Linear Search):
```python
arr = [10, 20, 30, 40, 50]
key = 30

def linear_search(arr, key):
    for i in range(len(arr)):
        if arr[i] == key:
            return i  # رجع الفهرس اللي فيه العنصر
    return -1  # لو مش لاقي العنصر

index = linear_search(arr, key)
print(f'Element found at index: {index}')  # هيتطبع فهرس العنصر
```

**For a Sorted Array** (Binary Search):
```python
arr = [10, 20, 30, 40, 50]
key = 30

def binary_search(arr, key):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == key:
            return mid  # العنصر اتلاقى
        elif arr[mid] < key:
            low = mid + 1
        else:
            high = mid - 1
    return -1  # العنصر مش موجود

index = binary_search(arr, key)
print(f'Element found at index: {index}')
```

---

### 3. **Insertion (الإدخال)**

**الإدخال** هو عملية إضافة عنصر جديد إلى هيكل البيانات في مكان معين. الإضافة دي ممكن تكون في أول، في وسط، أو في آخر الهيكل.

#### **Example in Python**:

**For an Array**:
```python
arr = [10, 20, 30, 40, 50]
arr.append(60)  # إضافة العنصر في آخر المصفوفة
print(arr)  # هيتطبع [10, 20, 30, 40, 50, 60]
```

**For a Linked List**:
```python
class LinkedList:
    def __init__(self):
        self.head = None

    def insert(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

ll = LinkedList()
ll.insert(10)
ll.insert(20)
ll.insert(30)
ll.traverse()  # هيتطبع 30, 20, 10
```

---

### 4. **Deletion (الحذف)**

**الحذف** هو عملية إزالة عنصر من هيكل البيانات. زي مثلاً لما تحذف عنصر من **المصفوفة** أو **القائمة المترابطة**.

#### **Example in Python**:

**For an Array**:
```python
arr = [10, 20, 30, 40, 50]
arr.remove(30)  # هيمسح العنصر 30
print(arr)  # هيتطبع [10, 20, 40, 50]
```

**For a Linked List**:
```python
class LinkedList:
    def __init__(self):
        self.head = None

    def delete(self, key):
        current = self.head
        if current and current.data == key:
            self.head = current.next
            current = None
            return
        prev = None
        while current and current.data != key:
            prev = current
            current = current.next
        if current is None:
            return
        prev.next = current.next
        current = None

ll = LinkedList()
ll.insert(10)
ll.insert(20)
ll.insert(30)
ll.delete(20)  # هيمسح العنصر 20
ll.traverse()  # هيتطبع 30, 10
```

---

### 5. **Sorting (الترتيب)**

**الترتيب** هو عملية ترتيب العناصر في هيكل البيانات بناءً على ترتيب معين (زي تصاعدي أو تنازلي).

#### **Example in Python**:

**For an Array** (using Python's built-in sort function):
```python
arr = [10, 40, 20, 50, 30]
arr.sort()  # ترتيب المصفوفة تصاعدي
print(arr)  # هيتطبع [10, 20, 30, 40, 50]
```

**For a Linked List** (using Bubble Sort):
```python
class LinkedList:
    def __init__(self):
        self.head = None

    def sort(self):
        if not self.head:
            return
        current = self.head
        while current:
            index = current.next
            while index:
                if current.data > index.data:
                    current.data, index.data = index.data, current.data
                index = index.next
            current = current.next

ll = LinkedList()
ll.insert(30)
ll.insert(10)
ll.insert(50)
ll.insert(20)
ll.sort()
ll.traverse()  # هيتطبع 10, 20, 30, 50
```

---

### 6. **Merging (الدمج)**

**الدمج** هو عملية دمج أكثر من هيكل بيانات في هيكل واحد، وعادة بيتم ترتيب العناصر أثناء الدمج.

#### **Example in Python**:

**Merging two Sorted Arrays**:
```python
arr1 = [10, 20, 30]
arr2 = [5, 15, 25, 35]

def merge(arr1, arr2):
    merged = []
    i = j = 0
    while i < len(arr1) and j < len(arr2):
        if arr1[i] < arr2[j]:
            merged.append(arr1[i])
            i += 1
        else:
            merged.append(arr2[j])
            j += 1
    merged.extend(arr1[i:])
    merged.extend(arr2[j:])
    return merged

merged_arr = merge(arr1, arr2)
print(merged_arr)  # هيتطبع [5, 10, 15, 20, 25, 30, 35]
```

---

## **Quick Recap**:

- **Traversing**: زي لما تمر على كل العناصر وتطبعها.
- **Searching**: زي البحث عن عنصر معين في الهيكل باستخدام **البحث الخطي** أو **البحث الثنائي**.
- **Insertion**: إضافة عنصر جديد في الهيكل.
- **Deletion**: حذف عنصر من الهيكل.
- **Sorting**: ترتيب العناصر في الهيكل حسب ترتيب معين.
- **Merging**: دمج هياكل بيانات مختلفة في هيكل واحد.

---

