<!--
Meta Description: # Python中的StopIteration异常 ## 概述 `StopIteration`是Python中一个重要的内置异常，它用于指示迭代器已经没有更多的项目可供迭代。在使用for循环或其他迭代上下文时，`StopIteration`异常通常会被自动处理。 ## 文档 ### 目的 `Stop...
Meta Keywords: stopiteration, self, __next__, max, current
-->

# Python中的StopIteration异常

## 概述
`StopIteration`是Python中一个重要的内置异常，它用于指示迭代器已经没有更多的项目可供迭代。在使用for循环或其他迭代上下文时，`StopIteration`异常通常会被自动处理。

## 文档
### 目的
`StopIteration`异常的主要目的是在自定义迭代器时，通知调用者迭代已经结束。这使得循环能够优雅地终止，而不必手动检查每次迭代的结果。

### 使用
在Python中，当你实现一个迭代器时，需要定义`__iter__()`和`__next__()`方法。在`__next__()`方法中，当没有更多项目可供返回时，必须抛出`StopIteration`异常。这样，Python的迭代机制能够识别并停止迭代。

### 细节
- `StopIteration`异常是内置异常，在`builtins`模块中定义。
- 你可以在自定义迭代器的`__next__()`方法中抛出此异常。
- 在for循环中，Python会自动捕获并处理`StopIteration`异常，因此用户通常不需要手动处理它。

## 示例
以下是使用`StopIteration`的基本示例：

```python
class MyIterator:
    def __init__(self, max):
        self.max = max
        self.current = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.current < self.max:
            value = self.current
            self.current += 1
            return value
        else:
            raise StopIteration

# 使用自定义迭代器
for number in MyIterator(5):
    print(number)
```

输出：
```
0
1
2
3
4
```

## 解释
- **常见陷阱**：在自定义迭代器时，如果忘记在达到迭代末尾时抛出`StopIteration`异常，会导致无限循环或错误的结果。
- **注意事项**：`StopIteration`异常不仅在自定义迭代器中使用，Python的内置迭代器（如列表、元组等）也会在没有更多元素时抛出此异常。
- **与生成器的关系**：生成器会自动处理`StopIteration`异常，因此在大多数情况下，你不需要手动抛出它，生成器会在没有更多值时自动停止迭代。

## 一句话总结
`StopIteration`异常用于指示迭代器已完成迭代，确保循环能够优雅地停止。