<!--
Meta Description: # Python 字典（dict）: 完整指南與實用範例 ## 簡介 在 Python 中，`dict` 是一種用於存儲鍵值對的可變資料結構。它是 Python 中最常用的內建資料類型之一，提供快速查找、插入和刪除操作。 ## 文檔 ### 目的 `dict`（字典）是一種無序的集合資料類型，允許以...
Meta Keywords: dict, python, student, name, age
-->

# Python 字典（dict）: 完整指南與實用範例

## 簡介
在 Python 中，`dict` 是一種用於存儲鍵值對的可變資料結構。它是 Python 中最常用的內建資料類型之一，提供快速查找、插入和刪除操作。

## 文檔
### 目的
`dict`（字典）是一種無序的集合資料類型，允許以鍵（key）來存取對應的值（value）。這使得字典非常適合用於需要快速查詢的情境。

### 使用方式
要創建一個字典，可以使用大括號 `{}` 或者 `dict()` 函數。字典的鍵必須是不可變類型（如字符串、數字或元組），而值則可以是任意資料類型。

#### 語法
```python
# 使用大括號創建字典
my_dict = {'name': 'Alice', 'age': 25}

# 使用 dict() 函數創建字典
my_dict = dict(name='Alice', age=25)
```

### 主要功能
- **查詢**: 使用鍵來快速獲取相對應的值。
- **更新**: 可以隨時修改已有的鍵的值或新增鍵值對。
- **刪除**: 可以根據鍵刪除對應的項目。

## 範例
以下是一些 `dict` 的基本使用範例：

```python
# 創建字典
student = {'name': 'Bob', 'age': 22, 'major': 'Computer Science'}

# 查詢
print(student['name'])  # 輸出: Bob

# 更新
student['age'] = 23

# 新增鍵值對
student['graduation_year'] = 2025

# 刪除鍵值對
del student['major']

print(student)  # 輸出: {'name': 'Bob', 'age': 23, 'graduation_year': 2025}
```

## 解釋
在使用 `dict` 時，開發者需要注意以下幾點：
- 鍵必須是唯一的，如果重複定義，後面的鍵值會覆蓋前面的。
- 字典是無序的，這意味著鍵值對的順序不固定，特別是在 Python 3.6 之前的版本中。
- 使用不當的鍵類型（例如可變類型如列表）會導致 `TypeError`。

## 一句總結
`dict` 是 Python 中一種強大且靈活的資料結構，用於儲存和操作鍵值對資料。