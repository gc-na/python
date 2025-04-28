<!--
Meta Description: # التعامل مع StopAsyncIteration في بايثون: مفهوم وأمثلة ## ملخص `StopAsyncIteration` هو استثناء في بايثون يُستخدم في سياق المولدات غير المتزامنة (asyn...
Meta Keywords: stopasynciteration, غير, self, async, المولدات
-->

# التعامل مع StopAsyncIteration في بايثون: مفهوم وأمثلة

## ملخص
`StopAsyncIteration` هو استثناء في بايثون يُستخدم في سياق المولدات غير المتزامنة (asynchronous generators) لإبطال عمليات التكرار. يُعتبر هذا الاستثناء جزءًا أساسيًا من إدارة تدفق البيانات في البرمجة غير المتزامنة.

## الوثائق
### الغرض
يُستخدم `StopAsyncIteration` للإشارة إلى نهاية التكرار في المولدات غير المتزامنة. عندما يصل المولد إلى حالة لا يمكن فيها إنتاج المزيد من القيم، يقوم بإطلاق هذا الاستثناء، مما يسمح للمستهلك بفهم أنه لا توجد المزيد من البيانات المتاحة.

### الاستخدام
يُستخدم `StopAsyncIteration` في مجموعة من التطبيقات، خاصةً في التطبيقات التي تعتمد على البرمجة غير المتزامنة، مثل التعامل مع الشبكات أو إدخال البيانات من مصادر متعددة. يتم تعريفه في `async for` و`async iterators`.

### التفاصيل
- **الإصدار:** تم تقديم `StopAsyncIteration` في بايثون 3.6.
- **السياق:** يتم استخدامه فقط داخل المولدات غير المتزامنة ولا يمكن استخدامه في المولدات التقليدية.
- **المكان:** يجب استخدامه داخل دالة مولد غير متزامن.

## الأمثلة
### مثال 1: مولد غير متزامن بسيط
```python
import asyncio

class AsyncCounter:
    def __init__(self, max):
        self.max = max
        self.count = 0

    def __aiter__(self):
        return self

    async def __anext__(self):
        if self.count < self.max:
            self.count += 1
            return self.count
        else:
            raise StopAsyncIteration

async def main():
    async for number in AsyncCounter(3):
        print(number)

asyncio.run(main())
```

### مثال 2: التعامل مع الاستثناء
```python
async def async_gen():
    yield 1
    yield 2
    raise StopAsyncIteration

async def main():
    try:
        async for value in async_gen():
            print(value)
    except StopAsyncIteration:
        print("تم إنهاء التكرار.")

asyncio.run(main())
```

## الشرح
### الأخطاء الشائعة والملاحظات
- **عدم استخدام `StopAsyncIteration` في المولدات التقليدية:** حاول استخدامه في المولدات التقليدية سيسبب أخطاء، لذا تأكد من استخدامه في السياقات الصحيحة.
- **تجاهل الاستثناء:** في حال تم تجاهل `StopAsyncIteration`، قد يؤدي ذلك إلى حلقات لا نهائية أو أخطاء غير متوقعة في الكود.

## ملخص جملة واحدة
`StopAsyncIteration` هو استثناء يُستخدم في بايثون لإنهاء التكرار في المولدات غير المتزامنة، مما يسهل إدارة تدفق البيانات في التطبيقات غير المتزامنة.