<!--
Meta Description: # Python 的 filter 函數：過濾資料的利器 ## 簡介 `filter` 函數是 Python 中一個強大的內建函數，主要用於過濾可迭代對象中的元素，根據給定的函數返回值（True 或 False）來決定哪些元素保留，哪些元素被過濾掉。 ## 文件說明 ### 目的 `filter` ...
Meta Keywords: filter, python, function, none, iterable
-->

# Python 的 filter 函數：過濾資料的利器

## 簡介
`filter` 函數是 Python 中一個強大的內建函數，主要用於過濾可迭代對象中的元素，根據給定的函數返回值（True 或 False）來決定哪些元素保留，哪些元素被過濾掉。

## 文件說明
### 目的
`filter` 函數的主要用途是從一個可迭代對象（如列表、元組等）中選擇符合特定條件的元素。這對於需要清理或處理資料的情況非常有用。

### 使用方法
`filter` 函數的語法如下：
```python
filter(function, iterable)
```
- `function`：一個函數，接受一個參數並返回布林值（True 或 False）。
- `iterable`：一個可迭代對象，如列表、元組或集合。

`filter` 返回一個過濾後的可迭代對象，通常需要轉換成列表或元組以便使用。

### 詳細說明
當你使用 `filter` 函數時，Python 會對 `iterable` 中的每個元素應用 `function`，並只保留返回 True 的元素。如果 `function` 是 `None`，則 `filter` 將過濾掉所有假值（如 `0`、`False`、`None`、空字符串等）。

## 示例
以下是一些基本的使用示例：

### 示例 1：過濾偶數
```python
def is_even(n):
    return n % 2 == 0

numbers = [1, 2, 3, 4, 5, 6]
even_numbers = list(filter(is_even, numbers))
print(even_numbers)  # 輸出: [2, 4, 6]
```

### 示例 2：過濾大於 10 的數字
```python
def is_greater_than_ten(n):
    return n > 10

numbers = [5, 10, 15, 20, 25]
filtered_numbers = list(filter(is_greater_than_ten, numbers))
print(filtered_numbers)  # 輸出: [15, 20, 25]
```

### 示例 3：過濾 None 值
```python
data = [1, None, 2, None, 3]
filtered_data = list(filter(None, data))
print(filtered_data)  # 輸出: [1, 2, 3]
```

## 解釋
使用 `filter` 時需要注意以下幾點：
- 確保 `function` 能夠正確處理 `iterable` 中的所有元素。
- 如果 `function` 返回非布林值，Python 會自動將其轉換為布林值，但這可能導致意想不到的行為。
- 如果 `function` 是 `None`，所有的假值將被過濾掉。

## 一句總結
`filter` 函數是 Python 中用於過濾可迭代對象的工具，根據指定條件選擇保留的元素。