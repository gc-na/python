<!--
Meta Description: # Python 中的 ExceptionGroup：多异常处理的强大工具 ## 概述 `ExceptionGroup` 是 Python 3.11 及以上版本中引入的一种新特性，用于处理多个异常的组合。这一特性使得在处理并发任务时，可以更方便地捕获和管理多个异常，提升了异常处理的灵活性和有效性。 ...
Meta Keywords: exceptiongroup, python, group, raise, occurred
-->

# Python 中的 ExceptionGroup：多异常处理的强大工具

## 概述
`ExceptionGroup` 是 Python 3.11 及以上版本中引入的一种新特性，用于处理多个异常的组合。这一特性使得在处理并发任务时，可以更方便地捕获和管理多个异常，提升了异常处理的灵活性和有效性。

## 文档
### 目的
`ExceptionGroup` 旨在简化对多个异常的处理方式，特别是在使用异步编程或多线程编程时。通过将多个异常组合为一个 `ExceptionGroup` 对象，开发者可以一次性捕获所有相关的异常，而无需逐一处理。

### 用法
在 Python 中使用 `ExceptionGroup`，你可以通过以下方式创建和处理异常组：

1. **导入模块**：
   ```python
   from exceptiongroup import ExceptionGroup
   ```

2. **创建异常组**：
   使用 `ExceptionGroup` 可以创建一个包含多个异常的对象。
   ```python
   e1 = ValueError("Value error occurred")
   e2 = TypeError("Type error occurred")
   group = ExceptionGroup("Multiple exceptions occurred", [e1, e2])
   ```

3. **处理异常组**：
   使用 `try` 和 `except` 语句捕获 `ExceptionGroup`。
   ```python
   try:
       # 可能抛出多个异常的代码
       raise group
   except ExceptionGroup as eg:
       for exc in eg.exceptions:
           print(exc)
   ```

### 细节
- `ExceptionGroup` 的构造函数接收两个参数：异常的名称和异常列表。
- 你可以通过 `exceptions` 属性访问组内的所有异常，以便逐一处理。
- 使用 `ExceptionGroup` 的主要好处是能够清晰地识别并处理多个相关异常，而不需要将每个异常单独捕获。

## 示例
以下是一个简单的使用示例：

```python
from exceptiongroup import ExceptionGroup

def task1():
    raise ValueError("Task 1 failed")

def task2():
    raise TypeError("Task 2 failed")

try:
    task1()
    task2()
except Exception as e:
    group = ExceptionGroup("Tasks failed", [e])
    raise group
```

在上述代码中，`task1` 和 `task2` 都可能引发异常，这些异常会被组合成一个 `ExceptionGroup` 对象。

## 解释
- **常见陷阱**：当处理异常组时，开发者可能会忽略对每个单独异常的具体处理，导致错误信息不明确。
- **注意事项**：确保在捕获 `ExceptionGroup` 后，正确地对每个异常进行处理，避免遗漏重要的错误信息。

## 一句话总结
`ExceptionGroup` 是 Python 3.11 中的新特性，旨在方便地处理多个异常，提高异常处理的效率和清晰度。