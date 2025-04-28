<!--
Meta Description: # NotImplemented في بايثون: مفهوم وأمثلة ## الملخص `NotImplemented` هو قيمة خاصة في بايثون تُستخدم للإشارة إلى أن دالة أو عملية معينة غير مُنفذة أو غي...
Meta Keywords: notimplemented, value, استخدام, self, بايثون
-->

# NotImplemented في بايثون: مفهوم وأمثلة

## الملخص
`NotImplemented` هو قيمة خاصة في بايثون تُستخدم للإشارة إلى أن دالة أو عملية معينة غير مُنفذة أو غير متاحة. تُعتبر هذه القيمة مهمة في سياقات متعددة، خاصة عند التعامل مع الدوال التي تتطلب تنفيذًا مخصصًا.

## التوثيق
### الغرض
تُستخدم `NotImplemented` عادةً في الدوال التي تُعرَّف في الكلاسات المخصصة، خاصةً عند تنفيذ العمليات الرياضية أو المقارنات. عند استخدام `NotImplemented`، يُظهر للمستخدم أن العملية غير مُنفذة، مما يشير إلى ضرورة إعادة تعريفها في الكلاسات الفرعية.

### الاستخدام
يمكن استخدام `NotImplemented` في الكلاسات الخاصة بك عندما تريد أن تخبر بايثون بأنه لا يمكن تنفيذ عملية معينة في سياق الكائنات الحالية. على سبيل المثال، عند تعريف دالة `__add__` لجمع كائنين، يمكنك إرجاع `NotImplemented` إذا لم تكن العملية ممكنة.

### التفاصيل
- `NotImplemented` هو كائن وحيد (singleton) في بايثون، مما يعني أنه لا يوجد منه سوى نسخة واحدة في الذاكرة.
- عادةً ما تُستخدم مع الدوال الخاصة مثل `__eq__` (للمقارنة) و`__add__` (للجمع).
- إرجاع `NotImplemented` بدلاً من `None` أو رفع استثناء يمكن أن يسمح لبايثون بمحاولة استخدام عمليات بديلة أو دوال أخرى.

## الأمثلة
### مثال 1: استخدام `NotImplemented` في دالة جمع
```python
class MyNumber:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        if isinstance(other, MyNumber):
            return MyNumber(self.value + other.value)
        return NotImplemented

num1 = MyNumber(5)
num2 = MyNumber(10)
result = num1 + num2  # يعمل بشكل صحيح
print(result.value)  # 15

result = num1 + 10  # غير مُنفذ
print(result)  # NotImplemented
```

### مثال 2: استخدام `NotImplemented` في دالة مقارنة
```python
class MyString:
    def __init__(self, value):
        self.value = value

    def __eq__(self, other):
        if isinstance(other, MyString):
            return self.value == other.value
        return NotImplemented

str1 = MyString("hello")
str2 = MyString("hello")
str3 = "hello"

print(str1 == str2)  # True
print(str1 == str3)  # NotImplemented
```

## الشرح
### الأخطاء الشائعة
- **إرجاع None بدلاً من NotImplemented:** إذا قمت بإرجاع `None` بدلاً من `NotImplemented`، فلن يتمكن بايثون من محاولة استخدام دوال بديلة، مما قد يؤدي إلى أخطاء في وقت التشغيل.
- **عدم معالجة الأنواع المختلفة:** عند استخدام `NotImplemented`، تأكد من أنك تعالج الأنواع المتاحة بطريقة صحيحة لتجنب السلوك غير المتوقع.

### ملاحظات إضافية
- عند استخدام `NotImplemented`، تأكد من أنك توضح للمستخدمين كيفية استخدام الكلاسات الخاصة بك بشكل صحيح.
- يجب أن تدرك أن `NotImplemented` لا يُعتبر استثناءً، لذا تأكد من استخدامه في السياقات الصحيحة.

## ملخص بجملة واحدة
`NotImplemented` في بايثون هو قيمة خاصة تُستخدم للإشارة إلى أن دالة أو عملية معينة غير مُنفذة، مما يعزز من إمكانية إعادة تعريف العمليات في الكلاسات الفرعية.