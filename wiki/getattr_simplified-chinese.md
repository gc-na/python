<!--
Meta Description: # Python中的getattr函数详解 ## 摘要 `getattr`是Python内置的一个函数，用于动态获取对象的属性或方法。它允许开发者在运行时根据字符串名称访问对象的属性，极大地增强了代码的灵活性。 ## 文档 `getattr(object, name[, default])`是Pyt...
Meta Keywords: getattr, name, person, age, height
-->

# Python中的getattr函数详解

## 摘要
`getattr`是Python内置的一个函数，用于动态获取对象的属性或方法。它允许开发者在运行时根据字符串名称访问对象的属性，极大地增强了代码的灵活性。

## 文档
`getattr(object, name[, default])`是Python的一个内置函数，用于获取对象的属性。其参数如下：
- **object**：要获取属性的对象。
- **name**：一个字符串，表示所需的属性名称。
- **default**（可选）：如果属性不存在时返回的默认值。如果不提供该参数，且属性不存在，将引发`AttributeError`。

### 用途
`getattr`常用于需要动态访问属性的场景，例如在处理JSON数据或创建插件系统时。它可以避免直接使用点操作符访问属性时可能遇到的错误。

### 使用示例
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person("Alice", 30)

# 正常获取属性
name = getattr(person, 'name')
print(name)  # 输出: Alice

# 尝试获取不存在的属性
# age = getattr(person, 'height')  # 这将引发 AttributeError

# 使用默认值获取不存在的属性
height = getattr(person, 'height', 170)
print(height)  # 输出: 170
```

## 解释
使用`getattr`时，需要注意以下几点：
1. **属性不存在**：如果请求的属性不存在且没有提供默认值，将会抛出`AttributeError`。因此，为了避免程序崩溃，建议总是使用默认值，尤其是在不确定属性是否存在的情况下。
2. **动态属性访问**：`getattr`允许使用变量来指定属性名称，这在处理动态数据时非常有用。
3. **性能考虑**：虽然`getattr`提供了灵活性，但频繁使用会影响性能，因此在性能敏感的场合应谨慎使用。

## 一句话总结
`getattr`是Python中用于动态获取对象属性的内置函数，提供了灵活的属性访问方式。