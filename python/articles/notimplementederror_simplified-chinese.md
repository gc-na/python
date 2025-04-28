<!--
Meta Description: # Python中的NotImplementedError：用法与示例 ## 概述 `NotImplementedError`是Python中的一个内置异常，用于指示抽象方法尚未实现或功能缺失。它通常用于类或方法中，标识某个特性或功能在当前上下文中不应被调用。 ## 文档 `NotImplement...
Meta Keywords: notimplementederror, self, class, def, shape
-->

# Python中的NotImplementedError：用法与示例

## 概述
`NotImplementedError`是Python中的一个内置异常，用于指示抽象方法尚未实现或功能缺失。它通常用于类或方法中，标识某个特性或功能在当前上下文中不应被调用。

## 文档
`NotImplementedError`是`Exception`的一个子类。它的主要目的是在子类中重写父类的方法时，提醒开发者该方法尚未被实现。该异常通常在抽象基类（Abstract Base Class）中使用，以强制派生类实现特定方法。

### 用法
在定义一个类时，可以使用`NotImplementedError`来确保未实现的方法在调用时会引发异常，从而帮助开发者识别代码中的未完成部分。例如：

```python
class MyBaseClass:
    def my_method(self):
        raise NotImplementedError("子类必须实现这个方法")
```

在这个示例中，如果调用`my_method`而不在子类中实现它，将会引发`NotImplementedError`。

## 示例
下面是一些使用`NotImplementedError`的基本示例。

### 示例1：基本使用
```python
class Shape:
    def area(self):
        raise NotImplementedError("子类必须实现这个方法")

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

# 正确用法
circle = Circle(5)
print(circle.area())  # 输出: 78.5

# 错误用法
shape = Shape()
print(shape.area())  # 抛出 NotImplementedError
```

### 示例2：抽象基类
```python
from abc import ABC, abstractmethod

class AbstractClass(ABC):
    @abstractmethod
    def do_something(self):
        raise NotImplementedError("必须实现该方法")

class ConcreteClass(AbstractClass):
    def do_something(self):
        return "完成任务"

# 正确用法
concrete = ConcreteClass()
print(concrete.do_something())  # 输出: 完成任务

# 错误用法
abstract = AbstractClass()  # 抛出 TypeError，因为抽象类不能被实例化
```

## 解释
使用`NotImplementedError`时，有几点需要注意：

1. **明确性**：抛出`NotImplementedError`时，建议提供清晰的错误信息，以便其他开发者了解需要实现的内容。
2. **抽象类**：当使用抽象基类时，确保所有派生类都实现了抽象方法，以避免运行时错误。
3. **调试**：在开发过程中，`NotImplementedError`是一个有效的调试工具，可以帮助识别未完成的功能。

## 一句话总结
`NotImplementedError`是Python中的异常，用于指示某个方法在子类中尚未实现，确保开发者在使用时获得清晰的反馈。