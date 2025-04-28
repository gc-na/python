<!--
Meta Description: # __package__：Python 中的包属性详解 ## 概述 `__package__` 是 Python 中的一个特殊属性，用于指示当前模块所属的包名。它在模块的命名空间中起着重要的作用，尤其是在包的导入和模块的相对导入时。 ## 文档 ### 目的 `__package__` 属性的主要...
Meta Keywords: __package__, python, mymodule, print, mypackage
-->

# __package__：Python 中的包属性详解

## 概述
`__package__` 是 Python 中的一个特殊属性，用于指示当前模块所属的包名。它在模块的命名空间中起着重要的作用，尤其是在包的导入和模块的相对导入时。

## 文档
### 目的
`__package__` 属性的主要目的在于帮助 Python 确定模块的上下文。它为模块提供了额外的信息，使得 Python 能够在执行相对导入时正确解析模块的路径。

### 用法
在 Python 中，`__package__` 属性通常被自动设置为模块的包名。如果一个模块是顶层模块（即不在任何包中），那么 `__package__` 属性将被设置为一个空字符串。

以下是一些关键点：
- 对于直接在命令行中运行的模块，`__package__` 将是空字符串。
- 在包内部，`__package__` 将被设置为包的名称。
- 如果模块是从一个包中导入的，`__package__` 将包含该模块的包名。

### 详细信息
- `__package__` 属性是一个字符串，包含模块的包名。
- 它在模块的定义之初就被定义，并且在模块执行时不会改变。
- `__package__` 属性对于编写可移植的代码和合理组织包结构至关重要。

## 示例
以下是使用 `__package__` 的基本示例：

```python
# 在包内的模块 mymodule.py
print(__package__)  # 输出包的名称，例如 'mypackage'

# 在顶层模块
print(__package__)  # 输出 ''
```

如果你在包的上下文中使用相对导入，例如：

```python
# 在 mypackage/submodule.py 中
from . import mymodule
print(mymodule.__package__)  # 输出 'mypackage'
```

## 说明
- **常见错误**：如果在顶层脚本中使用相对导入，可能会导致 `ImportError`，因为此时 `__package__` 是空的。
- **注意事项**：在模块导入时，确保理解 `__package__` 的设置对于避免导入错误十分重要。特别是在多层包结构中，错误的 `__package__` 可能导致模块无法被正确找到。

## 一句话总结
`__package__` 是 Python 中一个指示模块所属包名的特殊属性，对于模块的导入和包管理至关重要。