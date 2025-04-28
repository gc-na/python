<!--
Meta Description: # UnboundLocalError：Python中的局部变量未绑定错误 ## 概述 UnboundLocalError 是 Python 中的一种异常，表示在访问局部变量之前，该变量尚未被赋值。 ## 文档 ### 目的 UnboundLocalError 主要用于指示程序员在局部作用域中引用了...
Meta Keywords: unboundlocalerror, python, example_function, print, global
-->

# UnboundLocalError：Python中的局部变量未绑定错误

## 概述
UnboundLocalError 是 Python 中的一种异常，表示在访问局部变量之前，该变量尚未被赋值。

## 文档
### 目的
UnboundLocalError 主要用于指示程序员在局部作用域中引用了未初始化的变量。这通常发生在函数内部，当你试图使用一个局部变量，但该变量在使用前没有被赋值时。

### 使用
当您在函数内试图访问一个局部变量，但该变量从未被赋值时，Python 将抛出 UnboundLocalError。理解这一点对于调试程序非常重要，尤其是在处理复杂的函数时。

### 详细信息
- **作用域**：在 Python 中，变量的作用域决定了它们可以被访问的地方。局部变量是在函数内部定义的，仅在该函数内有效。
- **局部变量的赋值**：如果在函数内对一个变量进行赋值，Python 将视该变量为局部变量，直到函数结束。
- **全局与局部变量**：如果你在函数内使用一个全局变量的名称而没有先赋值给局部变量，Python 将抛出 UnboundLocalError。为了避免这种错误，可以使用 `global` 关键字。

## 示例
### 示例 1：基本用法
```python
def example_function():
    print(x)  # 尝试访问未赋值的局部变量
    x = 10
    print(x)

example_function()
```
输出：
```
UnboundLocalError: local variable 'x' referenced before assignment
```

### 示例 2：使用 global 关键字
```python
x = 5

def example_function():
    global x
    print(x)  # 访问全局变量
    x = 10
    print(x)

example_function()
```
输出：
```
5
10
```

## 解释
- **常见陷阱**：在函数内部使用与全局变量同名的变量，通常会导致 UnboundLocalError。确保在函数内使用全局变量时，需明确声明。
- **调试建议**：当遇到 UnboundLocalError 时，检查变量的赋值顺序以及作用域是解决问题的关键。
- **其他注意事项**：在复杂的函数中使用多个变量时，建议使用调试工具，帮助追踪变量状态，避免这种错误。

## 一句话总结
UnboundLocalError 是 Python 中的一种错误，指示在局部作用域内引用了未赋值的变量。