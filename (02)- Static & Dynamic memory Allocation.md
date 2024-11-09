

## **1. تخصيص الذاكرة الثابتة (Static Memory Allocation)**

الـ **Static Memory Allocation** يعني إنك بتخصص الذاكرة **قبل ما البرنامج يشتغل**، يعني في وقت **الترجمة** (Compile Time). في الحالة دي، لازم **تعرف** قد إيه الذاكرة اللي هتحتاجها من الأول، ومش هتقدر تغير حجمها بعدين.

### **إزاي يعني؟**

لما تكتب برنامج، وأنت بتحدد حاجة زي **مصفوفة** (أو Array) مثلاً، لازم تحدد **عدد العناصر** اللي هتخزنها في المصفوفة دي، وده بيحصل وقت الترجمة قبل ما البرنامج يبدأ.

### **مثال على تخصيص الذاكرة الثابتة في C**:

في C، لما تعوز تعمل مصفوفة، لازم تحدد عدد العناصر اللي هتستخدمها أولًا.

```c
#include <stdio.h>

int main() {
    int arr[5];  // هنا خصصنا مصفوفة فيها 5 عناصر

    arr[0] = 10;
    arr[1] = 20;
    arr[2] = 30;
    arr[3] = 40;
    arr[4] = 50;

    for(int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);  // هنا هنطبع كل عنصر من المصفوفة
    }
    return 0;
}
```

في الكود ده:
- **المصفوفة** `arr` متخصصة بإنها تحتوي على 5 عناصر. لو حاولت تضيف أكثر من 5 عناصر هيتسبب في **مشكلة**.

### **ليه الـ Static Memory Allocation مش دايمًا كويس؟**
- **ماينفعش** تغير حجم الذاكرة بعد ما تبدأ البرنامج.
- لو احتجت حجم أكبر أو أصغر، هتواجه مشكلة لأن الحجم ثابت من الأول.

---

## **2. تخصيص الذاكرة الديناميكي (Dynamic Memory Allocation)**

الـ **Dynamic Memory Allocation** هو لما تخصيص الذاكرة بيحصل **أثناء تشغيل البرنامج** (يعني في وقت **التنفيذ**)، وبكده تقدر تخصص الذاكرة **على حسب الحاجة**، يعني تقدر تحدد الذاكرة أثناء ما البرنامج شغال.

### **إزاي يعني؟**

في التخصيص الديناميكي، مش لازم تحدد حجم الذاكرة قبل ما تشغل البرنامج. تقدر تخصص **الذاكرة** وتستخدمها لما تكون محتاجها، وتحررها لما تخلص منها.

### **مثال على تخصيص الذاكرة الديناميكي في C:**

في C، ممكن تستخدم دوال زي `malloc()` أو `calloc()` لتخصيص الذاكرة ديناميكيًا.

```c
#include <stdio.h>
#include <stdlib.h>  // لازم نضيف المكتبة دي عشان نستخدم malloc

int main() {
    int *arr;
    arr = (int*) malloc(5 * sizeof(int));  // بنخصص 5 عناصر من الذاكرة ديناميكيًا

    if(arr == NULL) {  // بنعمل check لو حصل مشكلة في تخصيص الذاكرة
        printf("Memory allocation failed\n");
        return 1;
    }

    arr[0] = 10;
    arr[1] = 20;
    arr[2] = 30;
    arr[3] = 40;
    arr[4] = 50;

    for(int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);  // هنا هنطبع كل عنصر من المصفوفة
    }

    free(arr);  // لازم نحرر الذاكرة لما نخلص منها

    return 0;
}
```

في الكود ده:
- **malloc()** بتخصص الذاكرة على حسب الحاجة أثناء تشغيل البرنامج.
- بعد ما تخلص من استخدام الذاكرة، لازم تستخدم **free()** علشان تحررها.

### **ليه الـ Dynamic Memory Allocation أحسن؟**
- تقدر تخصص الذاكرة **على حسب الحاجة**، يعني لو احتجت مساحات أكبر أو أصغر من غير ما تكون محدد مسبقًا.
- بيخليك تقدر تستخدم الذاكرة بشكل **أكثر مرونة**.

---
![image](https://github.com/user-attachments/assets/0e830749-8316-474b-9e14-4fb3ed7d6198)
---

## **الفرق بين Static و Dynamic Memory Allocation**:

| **الميزة**                     | **الـ Static Memory Allocation**                           | **الـ Dynamic Memory Allocation**                           |
|---------------------------------|-----------------------------------------------------------|------------------------------------------------------------|
| **وقت تخصيص الذاكرة**           | في وقت الترجمة (Compile Time)                              | في وقت التشغيل (Runtime)                                   |
| **حجم الذاكرة**                 | لازم تحدد حجم الذاكرة مسبقًا                              | الذاكرة بتتخصص حسب الحاجة أثناء التشغيل                    |
| **المرونة**                     | مش مرن، الحجم ثابت.                                      | مرن، تقدر تغير الحجم حسب الحاجة أثناء البرنامج بيشتغل.    |
| **السرعة**                      | أسرع لأن الذاكرة بتتخصص مرة واحدة فقط في وقت الترجمة     | أبطأ شوية لأن التخصيص بيحصل أثناء التنفيذ                 |
| **استخدام الذاكرة**             | ثابت، مش هتقدر تضيف أو تحذف عناصر بعد تخصيص الذاكرة      | تقدر تضيف وتحذف وتخصص وتحرر الذاكرة في أي وقت.           |

---

## **ملخص**:
- **Static Memory Allocation** هو تخصيص الذاكرة في وقت **الترجمة**، وحجم الذاكرة بيكون ثابت ومش ممكن تغيره بعد كده.
- **Dynamic Memory Allocation** هو تخصيص الذاكرة في وقت **التنفيذ**، وبيتيح لك تخصيص وتحرير الذاكرة حسب الحاجة.

---

![image](https://github.com/user-attachments/assets/721f7620-ad20-4606-9844-54ede08ff5e1)