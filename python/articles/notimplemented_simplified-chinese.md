<!--
Meta Description: # Python中的NotImplemented：功能与用法详解 ## 简介 `NotImplemented`是Python中的一个特殊常量，用于表示某个方法或操作尚未实现。它常用于重载运算符时，指示当前类不支持该操作。 ## 文档 ### 目的 `NotImplemented`常量主要用于自定义类...
Meta Keywords: notimplemented, self, vector, other, __add__
-->

# Python中的NotImplemented：功能与用法详解

## 简介
`NotImplemented`是Python中的一个特殊常量，用于表示某个方法或操作尚未实现。它常用于重载运算符时，指示当前类不支持该操作。

## 文档
### 目的
`NotImplemented`常量主要用于自定义类的运算符重载，特别是在实现某些二元操作（如加法、减法等）时。当一个运算符在当前类中没有合适的实现时，返回`NotImplemented`可以告诉Python解释器去查找其他类的实现。

### 用法
在自定义类中，当你重载运算符并且该运算符不适用于当前实例时，可以返回`NotImplemented`。这样，Python就会尝试调用其他对象的相应方法。

### 细节
- `NotImplemented`是一个内置常量，类型为`NotImplementedType`。
- 它通常用于实现`__add__`、`__sub__`等特殊方法，尤其是在涉及不同类型的对象之间的运算时。
- 返回`NotImplemented`而不是抛出异常，可以使得Python更灵活地处理不同类型之间的操作。

## 示例
以下是一个简单的示例，演示如何在自定义类中使用`NotImplemented`来处理运算符重载：

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        if not isinstance(other, Vector):
            return NotImplemented
        return Vector(self.x + other.x, self.y + other.y)

    def __repr__(self):
        return f"Vector({self.x}, {self.y})"

v1 = Vector(1, 2)
v2 = Vector(3, 4)
print(v1 + v2)  # 输出: Vector(4, 6)

v3 = v1 + 5  # 返回: NotImplemented
print(v3)    # 输出: None
```

## 说明
- 在执行`v1 + 5`时，由于`5`不是`Vector`类型，`__add__`方法返回`NotImplemented`。这使得Python能够尝试查找`int`类的`__radd__`方法。
- 如果不返回`NotImplemented`而是直接抛出异常，可能会导致代码的可读性和可维护性降低。

## 一句话总结
`NotImplemented`是Python中的一个常量，用于指示某个方法或操作尚未实现，常用于运算符重载的上下文中。