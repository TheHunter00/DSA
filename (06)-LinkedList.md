
---

### **1. Disadvantages of Arrays** (عيوب المصفوفات)

المصفوفات هي هياكل بيانات بتخزن مجموعة من العناصر، زي الأرقام أو الحروف، في أماكن متجاورة في الذاكرة. لكن ليها بعض العيوب:

- **Fixed Size (الحجم الثابت)**: 
  المصفوفة لازم يكون ليها حجم ثابت عند بداية تعريفها. يعني لو حددت حجم المصفوفة بـ 5 عناصر، مش هتقدر تضيف أكتر من كده بعد ما تملأها.

  - **مثال**: لو عندك مصفوفة بتخزن 5 أرقام:
  ```python
  arr = [1, 2, 3, 4, 5]
  ```
  لو حبيت تضيف رقم تاني بعد ما المصفوفة اتملت، هتضطر تكبر حجم المصفوفة يدويًا.

- **Memory Waste (هدر الذاكرة)**:
  لو عملت مصفوفة وحجزت فيها مساحة كبيرة جدًا، لكن في الآخر ما استخدمتش كل الأماكن فيها، يبقى الجزء المتبقي ده راح هدر.

- **Expensive Insertion/Deletion (إضافة وحذف مكلف)**: 
  لو عاوز تضيف أو تحذف عنصر في مكان معين في المصفوفة، هتضطر تحرك باقي العناصر علشان تفضي مكان. ده بياخد وقت طويل.

  - **مثال**: لو عاوز تحذف العنصر رقم 3، هتضطر تحرك كل العناصر بعده.

---

### **2. What is a Linked List?** (إيه هي الـ Linked List؟)

الـ **Linked List** هي هيكل بيانات مختلف عن المصفوفة. بدل ما تخزن البيانات في أماكن متجاورة في الذاكرة، بتخزنها في **عقد** (Nodes). كل عقدة بتحتوي على:

- **Data (بيانات)**: اللي هو العنصر نفسه.
- **Pointer (مؤشر)**: مؤشر يشير على العنصر اللي بعده في القائمة.

مثلاً، لو عندك **Linked List** فيها 3 عناصر، هتبقى زي كده:

```plaintext
[10] -> [20] -> [30] -> None
```

الـ **None** في الآخر ده بيدل على إن مفيش عنصر تاني بعد العنصر الأخير.

---

### **3. Why Linked List?** (ليه نستخدم الـ Linked List؟)

الـ **Linked List** ليه مزايا كتير مقارنة بالمصفوفات:

- **Dynamic Size (حجم متغير)**:
  ممكن تضيف أو تحذف عناصر بسهولة، والـ **Linked List** بتغير حجمها تلقائيًا على حسب الحاجة.

- **Efficient Insertion/Deletion (إضافة وحذف بكفاءة)**:
  لو عاوز تضيف أو تحذف عنصر في أي مكان، تقدر تعمل ده بسهولة لأنك مش هتحتاج تحرك باقي العناصر.

- **No Memory Waste (مفيش هدر في الذاكرة)**:
  كل عنصر في الـ **Linked List** بيتم تخصيص له مكان في الذاكرة فقط لما تحتاجه، فمفيش حاجة تروح هدر.

---

### **4. Insertion and Deletion in Arrays vs Linked List** (الإضافة والحذف في المصفوفات مقارنة بـ Linked List)

- **Insertion in Arrays (إضافة في المصفوفات)**:
  لو حبيت تضيف عنصر في مكان معين في المصفوفة، هتضطر تحرك العناصر اللي بعده عشان تفضي مكان. ده بياخد وقت كبير جدًا.

  - **مثال**: لو عندك مصفوفة زي دي:
  ```python
  arr = [1, 2, 3, 5]
  ```
  لو عاوز تضيف 4 بين 3 و 5، هتضطر تحرك العنصر 5 عشان تفضي مكان للـ 4.

- **Insertion in Linked List (إضافة في Linked List)**:
  في **Linked List**، لو عاوز تضيف عنصر، كل اللي عليك تعمله هو تغيير المؤشر اللي في العقدة السابقة عشان يشاور على العقدة الجديدة.

  - **مثال**: لو عندك **Linked List** زي كده:
  ```plaintext
  [10] -> [20] -> [30] -> None
  ```
  لو حبيت تضيف العنصر 15 بين 10 و 20، هتضيف **Node** جديدة وتربطها بـ **Pointer**.

- **Deletion in Arrays (حذف في المصفوفات)**:
  لو حبيت تحذف عنصر من المصفوفة في مكان معين، هتضطر تحرك باقي العناصر بعده عشان تسد الفراغ اللي هيبقى بعد ما تشيل العنصر.

- **Deletion in Linked List (حذف في Linked List)**:
  في **Linked List**، لو حبيت تحذف عنصر، كل اللي عليك تعمله هو تغيير المؤشر في العقدة اللي قبل العنصر اللي عاوز تحذفه علشان يشاور على العقدة اللي بعده.

---

### **5. Drawbacks in Linked Lists** (عيوب الـ Linked List)

- **Memory Overhead (زيادة استهلاك الذاكرة)**:
  كل **Node** في الـ **Linked List** فيها **Pointer** بالإضافة للبيانات، يعني ده بيزود استهلاك الذاكرة.

- **No Random Access (مفيش وصول عشوائي)**:
  في المصفوفات، تقدر توصل لأي عنصر بسهولة باستخدام **Index** (الفهرس). لكن في الـ **Linked List**، لو عاوز توصل لعنصر معين، لازم تمشي من العقدة الأولى لحد ما توصل له.

- **Complexity (التعقيد)**:
  الـ **Linked List** بتحتاج عناية أكتر في التعامل مع **Pointers**. لو ما كنتش حريص، ممكن يحصل **Memory Leaks** أو أخطاء تانية.

---

### **6. Linked List Operations** (عمليات الـ Linked List)

#### **Create (إنشاء)**
لما تبدأ، بتعمل **Linked List** فارغة أو تبتدي تضيف **Nodes** فيها.

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None  # Pointer للعقدة التالية

class LinkedList:
    def __init__(self):
        self.head = None  # رأس الـ Linked List
```

#### **Insert (إضافة)**
- **Insert at Beginning (إضافة في البداية)**:
  ده معناه إنك تضيف العنصر الجديد في أول الـ **Linked List**.

  ```python
  def insert_at_beginning(self, data):
      new_node = Node(data)
      new_node.next = self.head
      self.head = new_node
  ```

- **Insert at End (إضافة في النهاية)**:
  ده معناه إضافة العنصر في آخر الـ **Linked List**.

  ```python
  def insert_at_end(self, data):
      new_node = Node(data)
      if self.head is None:
          self.head = new_node
          return
      last = self.head
      while last.next:
          last = last.next
      last.next = new_node
  ```

#### **Delete (حذف)**
- **Delete at Beginning (حذف من البداية)**:
  لو حبيت تشيل العنصر الأول.

  ```python
  def delete_at_beginning(self):
      if self.head is None:
          print("The list is empty.")
          return
      self.head = self.head.next
  ```

- **Delete at End (حذف من النهاية)**:
  لو حبيت تشيل العنصر الأخير.

  ```python
  def delete_at_end(self):
      if self.head is None:
          print("The list is empty.")
          return
      temp = self.head
      while temp.next and temp.next.next:
          temp = temp.next
      temp.next = None
  ```

#### **Display (عرض)**
ده لعرض كل العناصر في الـ **Linked List**.

```python
def display(self):
    temp = self.head
    while temp:
        print(temp.data, end=" -> ")
        temp = temp.next
    print("None")
```

---

### **Summary** (ملخص)

- **Arrays**: سريعة في الوصول للعناصر ولكن محدودة الحجم وصعب تضيف أو تحذف عناصر بسهولة.
- **Linked List**: أفضل في إضافة وحذف العناصر بسهولة وحجم متغير، ولكن بتستهلك ذاكرة أكثر وصعب الوصول عشوائيًا للعناصر.

