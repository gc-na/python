<!--
Meta Description: # Python中的 all() 函數：完整指南 ## 摘要 `all()` 函數是Python內建的函數，用於檢查可迭代對象中的所有元素是否都為真值。如果所有元素為真，則返回 `True`；否則返回 `False`。 ## 文檔 ### 目的 `all()` 函數的主要目的是檢查可迭代對象（如列表...
Meta Keywords: all, true, result, 則返回, false
-->

# Python中的 all() 函數：完整指南

## 摘要
`all()` 函數是Python內建的函數，用於檢查可迭代對象中的所有元素是否都為真值。如果所有元素為真，則返回 `True`；否則返回 `False`。

## 文檔
### 目的
`all()` 函數的主要目的是檢查可迭代對象（如列表、元組、集合等）中的所有元素是否為真。這對於需要確保所有條件都滿足的情況非常有用。

### 用法
`all(iterable)`

- **參數**：
  - `iterable`：可以是任何可迭代對象（例如列表、元組、集合、字符串等）。

- **返回值**：
  - 若 `iterable` 中的所有元素為真值，則返回 `True`；若有任一元素為假值，則返回 `False`。
  - 若 `iterable` 為空，則返回 `True`。

### 詳細說明
`all()` 函數會遍歷提供的可迭代對象，並檢查每個元素的真值。若所有元素的真值為 `True`，則返回 `True`。如果遇到第一個假值 (如 `0`, `None`, `''`, `False` 等)，函數會立即返回 `False`，這樣能提高效率。

## 範例
以下是一些使用 `all()` 函數的基本範例：

### 範例 1：基本使用
```python
numbers = [1, 2, 3, 4, 5]
result = all(num > 0 for num in numbers)
print(result)  # 輸出: True
```

### 範例 2：包含假值
```python
numbers = [1, 2, 0, 4, 5]
result = all(num > 0 for num in numbers)
print(result)  # 輸出: False
```

### 範例 3：空可迭代對象
```python
empty_list = []
result = all(empty_list)
print(result)  # 輸出: True
```

## 解釋
### 常見陷阱
- **空可迭代對象**：`all()` 函數對於空的可迭代對象會返回 `True`，這可能會讓初學者感到困惑。
- **非布林值**：`all()` 函數檢查真值，而不僅是布林型別。如果可迭代對象中存在其他類型的數據（例如字符串或列表），Python會根據其真值進行檢查。

### 附加說明
在使用 `all()` 函數時，最好搭配生成器表達式使用，以減少內存使用，特別是在處理大型數據集時。

## 一句總結
`all()` 函數用於檢查可迭代對象中的所有元素是否為真值，並返回相應的布林結果。