# 2-D Arrays

هي مصفوفات بتتكون من صفوف وأعمدة. يعني بتخزن البيانات في شكل جدول. مثلاً، لو عايز تخزن درجات الطلاب، تقدر تعمل كده:

### مثال:
```python
grades = [
    [85, 90, 78],
    [88, 92, 80],
    [75, 85, 95]
]
```

## الوصول للعناصر

لما تحب توصل لعناصر في الـ 2-D Array، بتستخدم الـ index كده:

```python
element = grades[1][2]  # هتاخد العنصر في الصف 1 والعمود 2، يعني 80
```

### مثال:
```python
print(grades[0][1])  # هتطبع 90
```

## استخدامات الـ 2-D Arrays

المصفوفات ذات الأبعاد المتعددة مش مدعومة بشكل مباشر في الهاردوير، بس معظم لغات البرمجة بتوفر طرق لتسهيل التعامل معها. 

### أهمية الـ 2-D Arrays

الـ 2-D Arrays مهمة جداً في مجالات زي معالجة الصور أو تخزين بيانات جداول. يعني تقدر تستخدمها في أي حاجة محتاجة تنظيم بيانات بشكل مرتب.

## تعريف 2-D Array

الـ 2-D Array عبارة عن مجموعة عناصر مرتبة في صفوف وأعمدة. ممكن تعرف مصفوفة جديدة كده:

```python
def Array2D(n_rows, n_cols):
    return [[0] * n_cols for _ in range(n_rows)]
```

### مثال:
لو عايز مصفوفة 3 صفوف و4 أعمدة:

```python
my_array = Array2D(3, 4)
```

## مثال لحساب المتوسط

تخيل عندك ملف فيه درجات الطلاب. هتعمل الآتي:

1. تستخرج الدرجات.
2. تخزنها في 2-D Array.
3. تحسب المتوسط.

### مثال:
```python
grades = [
    [85, 90, 78],
    [88, 92, 80],
    [75, 85, 95]
]

average = sum(sum(row) for row in grades) / (len(grades) * len(grades[0]))
print(f"Average grade: {average}")  # هيطبع المتوسط
```

## تنفيذ الـ 2-D Array

فيه طرق مختلفة لتنفيذ 2-D Array:

1. **استخدام 1-D Array**: العناصر تكون مرتبة إما بالصف أو العمود.
2. **استخدام Array من Arrays**: كل صف يخزن في 1-D Array خاص به.

### تنفيذ Array من Arrays

كل صف هيتخزن في 1-D Array خاص به، وتستخدم 1-D Array لتخزين المراجع لكل صف:

```python
rows = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

### مثال:
```python
# الوصول للعنصر في الصف 2 والعمود 1
value = rows[2][1]  # هيكون 8
```

## أخطاء شائعة في تنفيذ 2-D Array

لو حصل أي خطأ في تنفيذ الـ 2-D Array، اتأكد إنك بتستخدم الصيغة الصحيحة. مثلاً:

```python
# إذا كانت المصفوفة مش متعرفة صح
y = x[r, c]  # تأكد إن x متعرفة كـ 2-D Array
```

## طريقة الوصول للعناصر

تقدر توصل للعناصر كده:

```python
y = x[r, c]
x[r, c] = z
```

### ملاحظات:
- الـ subscripts لازم تكون في شكل tuple.
- اتأكد من حجم الـ tuple قبل ما تستخدمه.

### مثال:
```python
def get_item(array, r, c):
    return array[r][c]

# استخدام
item = get_item(grades, 1, 2)  # هيكون 80
```

---
