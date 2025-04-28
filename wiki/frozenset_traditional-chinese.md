<!--
Meta Description: # Python frozenset：不可變集合的詳細介紹 ## 簡介 `frozenset` 是 Python 的一種內建資料型別，代表一個不可變的集合。這意味著一旦創建，`frozenset` 中的元素無法改變，這使得它在某些情況下非常有用，例如作為字典的鍵或存儲在其他集合中。 ## 文檔 `f...
Meta Keywords: frozenset, python, print, fs1, fs2
-->

# Python frozenset：不可變集合的詳細介紹

## 簡介
`frozenset` 是 Python 的一種內建資料型別，代表一個不可變的集合。這意味著一旦創建，`frozenset` 中的元素無法改變，這使得它在某些情況下非常有用，例如作為字典的鍵或存儲在其他集合中。

## 文檔
`frozenset` 的主要目的是提供一種不可變的集合類型，其基本語法為：

```python
frozenset(iterable)
```

### 參數：
- `iterable`：任何可迭代的物件，例如列表、元組或其他集合。

### 返回值：
- 返回一個新的 `frozenset` 物件。

### 特性：
1. **不可變性**：創建後，`frozenset` 中的元素無法被增刪改，這保證了數據的完整性。
2. **哈希性**：因為 `frozenset` 是不可變的，它可以作為字典的鍵或存儲在另一個集合中。
3. **支持集合操作**：`frozenset` 支持集合的基本操作，例如聯集、交集和差集等。

## 範例
以下是使用 `frozenset` 的一些基本範例：

### 範例 1：創建 `frozenset`
```python
# 從列表創建 frozenset
my_frozenset = frozenset([1, 2, 3, 4])
print(my_frozenset)  # 輸出：frozenset({1, 2, 3, 4})
```

### 範例 2：使用 `frozenset` 作為字典鍵
```python
# 使用 frozenset 作為字典的鍵
my_dict = {frozenset([1, 2]): "value1", frozenset([3, 4]): "value2"}
print(my_dict[frozenset([1, 2])])  # 輸出：value1
```

### 範例 3：集合操作
```python
# frozenset 的集合操作
fs1 = frozenset([1, 2, 3])
fs2 = frozenset([3, 4, 5])

# 聯集
print(fs1 | fs2)  # 輸出：frozenset({1, 2, 3, 4, 5})

# 交集
print(fs1 & fs2)  # 輸出：frozenset({3})

# 差集
print(fs1 - fs2)  # 輸出：frozenset({1, 2})
```

## 解釋
雖然 `frozenset` 在 Python 中非常有用，但使用時需注意以下幾點：

1. **不可變性**：因為 `frozenset` 是不可變的，試圖修改其內容會引發錯誤。
2. **元素類型**：`frozenset` 的元素必須是可哈希的，這意味著不能包含可變類型如列表或其他集合。
3. **性能考量**：在需要頻繁查詢但不需要修改的情況下，使用 `frozenset` 是一個合適的選擇，但不適合需要經常增刪改的場景。

## 一句摘要
`frozenset` 是 Python 中的一種不可變集合，適合用於需要數據不變性和哈希性的場景。