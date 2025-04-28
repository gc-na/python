<!--
Meta Description: # Python 中的格式化字符串（format）用法详解 ## 摘要 `format` 是 Python 中一个强大的字符串格式化方法，用于创建灵活且可读性强的字符串。它允许在字符串中嵌入变量，以实现动态内容的生成。 ## 文档 ### 目的 `format` 方法用于格式化字符串，使得在输出字符...
Meta Keywords: format, python, quantity, name, age
-->

# Python 中的格式化字符串（format）用法详解

## 摘要
`format` 是 Python 中一个强大的字符串格式化方法，用于创建灵活且可读性强的字符串。它允许在字符串中嵌入变量，以实现动态内容的生成。

## 文档
### 目的
`format` 方法用于格式化字符串，使得在输出字符串时可以插入变量或表达式的值。它支持多种格式化选项，可以满足不同的需求。

### 用法
`format` 方法是字符串对象的一个方法，基本语法为：

```python
str.format(*args, **kwargs)
```

- `*args`：位置参数，按顺序插入到字符串中的占位符 `{}`。
- `**kwargs`：关键字参数，通过关键字插入到字符串中的占位符 `{}`。

### 详细说明
- **占位符**：在字符串中使用 `{}` 作为占位符。
- **格式说明符**：可以在占位符中指定格式，例如 `{0:.2f}` 表示保留两位小数。
- **位置和关键字**：可以通过位置或关键字来引用变量，提供更大的灵活性。

## 示例
### 基本用法
```python
name = "Alice"
age = 30
greeting = "你好, {0}，你今年 {1} 岁。".format(name, age)
print(greeting)  # 输出: 你好, Alice，你今年 30 岁。
```

### 使用关键字参数
```python
info = "姓名: {name}, 年龄: {age}".format(name="Bob", age=25)
print(info)  # 输出: 姓名: Bob, 年龄: 25
```

### 格式化数字
```python
value = 123.456789
formatted_value = "格式化后的值: {:.2f}".format(value)
print(formatted_value)  # 输出: 格式化后的值: 123.46
```

### 多重格式化
```python
item = "苹果"
quantity = 5
price = 1.5
message = "我买了 {quantity} 个 {item}，总价是 {total:.2f}".format(quantity=quantity, item=item, total=quantity * price)
print(message)  # 输出: 我买了 5 个 苹果，总价是 7.50
```

## 说明
- **常见陷阱**：使用 `format` 时，字符串中占位符的数量与提供的参数数量不匹配会导致 `IndexError`。
- **替代方法**：从 Python 3.6 开始，Python 引入了 f-string（格式化字符串字面量），可以更直观地实现字符串格式化。
- **性能考虑**：在高性能场景下，`format` 可能比 f-string 慢，但在大多数情况下可以接受。

## 一句话总结
`format` 方法是 Python 提供的字符串格式化工具，可以灵活地插入变量并控制输出格式。