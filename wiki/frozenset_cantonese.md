<!--
Meta Description: # Python frozenset：不可變集合的完整指南 ## 概要 `frozenset` 是 Python 中的一種內建數據類型，用於創建不可變的集合。它提供了與普通集合類似的功能，但一旦創建後，其內容無法更改。 ## 文檔 ### 目的 `frozenset` 的主要目的是提供一種不可變的集...
Meta Keywords: frozenset, frozen_set, python, print, add
-->

# Python frozenset：不可變集合的完整指南

## 概要
`frozenset` 是 Python 中的一種內建數據類型，用於創建不可變的集合。它提供了與普通集合類似的功能，但一旦創建後，其內容無法更改。

## 文檔
### 目的
`frozenset` 的主要目的是提供一種不可變的集合，這在需要集合作為字典鍵或在其他需要不可變對象的情況下特別有用。

### 用法
要創建一個 `frozenset`，可以使用 `frozenset()` 函數，並將可迭代對象（如列表、元組或其他集合）作為參數傳入。

```python
frozen_set = frozenset([1, 2, 3, 4])
```

### 詳情
- `frozenset` 內部實現與 `set` 類似，但它是不可變的。
- 一旦創建，不能添加或刪除元素。
- 你可以使用 `frozenset` 進行常見集合操作，如並集、交集和差集。

## 例子
### 基本用法
```python
# 創建一個 frozenset
frozen_set = frozenset([1, 2, 3, 4])
print(frozen_set)  # 輸出：frozenset({1, 2, 3, 4})

# 嘗試添加元素（將拋出錯誤）
try:
    frozen_set.add(5)
except AttributeError as e:
    print(e)  # 輸出：'frozenset' object has no attribute 'add'

# frozenset 操作示例
frozen_set2 = frozenset([3, 4, 5, 6])
print(frozen_set.union(frozen_set2))  # 輸出：frozenset({1, 2, 3, 4, 5, 6})
print(frozen_set.intersection(frozen_set2))  # 輸出：frozenset({3, 4})
```

## 解釋
在使用 `frozenset` 時，有一些常見的陷阱：
- **不可變性**：一旦創建，`frozenset` 無法修改，這意味著不能使用 `add()`、`remove()` 或 `discard()` 方法。
- **容器類型**：雖然 `frozenset` 是不可變的，但它可以包含可變對象，例如列表或字典，但這些可變對象本身仍然可以被修改。
- **性能考量**：由於 `frozenset` 是不可變的，這使得它在某些情況下比可變集合更高效，特別是在作為字典鍵時。

## 一行總結
`frozenset` 是 Python 中一種不可變的集合類型，適合用於需要不可變對象的情境。