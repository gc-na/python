<!--
Meta Description: # Python 字典 (dict) 使用指南 ## 概述 在 Python 中，字典（dict）是一種內建的數據結構，用於存儲鍵值對（key-value pairs）。它是一種無序的、可變的集合，能夠快速地檢索、添加和更新數據。 ## 文檔 字典的主要目的是提供一種靈活且高效的方式來組織和存取數據...
Meta Keywords: python, my_dict, age, dict, name
-->

# Python 字典 (dict) 使用指南

## 概述
在 Python 中，字典（dict）是一種內建的數據結構，用於存儲鍵值對（key-value pairs）。它是一種無序的、可變的集合，能夠快速地檢索、添加和更新數據。

## 文檔
字典的主要目的是提供一種靈活且高效的方式來組織和存取數據。字典中的每個鍵必須是唯一的，並且可以是任何不可變的數據類型，例如字符串、數字或元組。字典的值則可以是任意數據類型，包括列表或其他字典。

### 使用方法
要創建一個字典，可以使用大括號 `{}` 或者內建函數 `dict()`。以下是基本的語法：

```python
# 使用大括號創建字典
my_dict = {
    'name': 'Alice',
    'age': 30,
    'city': 'Hong Kong'
}

# 使用 dict() 創建字典
my_dict = dict(name='Alice', age=30, city='Hong Kong')
```

### 訪問和修改字典
可以通過鍵來訪問和修改字典中的值：

```python
# 訪問值
print(my_dict['name'])  # 輸出: Alice

# 修改值
my_dict['age'] = 31

# 添加新鍵值對
my_dict['country'] = 'China'
```

### 刪除鍵值對
可以使用 `del` 關鍵字或 `pop()` 方法來刪除鍵值對：

```python
# 使用 del
del my_dict['city']

# 使用 pop()
age = my_dict.pop('age')
```

## 示例
以下是一些基本的字典使用示例：

```python
# 創建字典
student = {
    'name': 'Bob',
    'age': 22,
    'major': 'Computer Science'
}

# 訪問字典
print(student['major'])  # 輸出: Computer Science

# 更新字典
student['age'] = 23

# 添加新項
student['GPA'] = 3.8

# 刪除項
del student['name']
```

## 解釋
在使用字典時，常見的陷阱包括：

- **鍵的唯一性**：如果你嘗試使用相同的鍵來添加數據，原有的值會被覆蓋，而不是添加新值。
- **不可變鍵**：只可使用不可變類型作為鍵，像是字符串和元組，列表則不能作為鍵。
- **字典的順序**：在 Python 3.7 及以後版本中，字典保持插入順序，但在早期版本中則不是如此。

## 一句總結
Python 的字典（dict）是一種高效且靈活的數據結構，用於存儲和管理鍵值對。