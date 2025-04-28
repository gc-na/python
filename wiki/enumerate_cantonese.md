<!--
Meta Description: # Python Enumerate 函數：詳細說明與使用範例 ## 簡介 `enumerate` 是 Python 中的一個內建函數，主要用於在迭代序列（如列表、元組或字符串）時，提供索引和對應的值。這個函數非常適合用於需要同時獲取索引和元素的情況，讓代碼更加簡潔和易於閱讀。 ## 文檔 `enu...
Meta Keywords: enumerate, python, start, fruits, index
-->

# Python Enumerate 函數：詳細說明與使用範例

## 簡介
`enumerate` 是 Python 中的一個內建函數，主要用於在迭代序列（如列表、元組或字符串）時，提供索引和對應的值。這個函數非常適合用於需要同時獲取索引和元素的情況，讓代碼更加簡潔和易於閱讀。

## 文檔
`enumerate` 函數的主要目的是生成一個可迭代的對象，其中包含序列中每個元素的索引及其對應的值。這使得在遍歷序列時，可以輕鬆地獲取索引。

### 語法
```python
enumerate(iterable, start=0)
```

- **iterable**：任何可迭代的對象（如列表、字符串、元組等）。
- **start**：可選參數，指定索引的起始值，默認為 0。

### 返回值
返回一個 enumerate 對象，這是一個迭代器，生成的每個元素都是一個包含索引和值的元組。

## 使用範例
以下是 `enumerate` 的基本使用範例：

### 基本範例
```python
fruits = ['蘋果', '香蕉', '橙']
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
```
輸出：
```
0: 蘋果
1: 香蕉
2: 橙
```

### 自定義起始索引
```python
fruits = ['蘋果', '香蕉', '橙']
for index, fruit in enumerate(fruits, start=1):
    print(f"{index}: {fruit}")
```
輸出：
```
1: 蘋果
2: 香蕉
3: 橙
```

## 解釋
使用 `enumerate` 函數時，有幾個常見的注意事項：

1. **可迭代對象**：確保傳遞給 `enumerate` 的對象是可迭代的，否則會引發錯誤。
2. **索引起始值**：可以通過 `start` 參數指定索引的起始值，這對於某些特定需求非常有用。
3. **性能考量**：`enumerate` 函數的性能優於手動跟蹤索引，因為它是用 C 語言實現的，能夠更高效地迭代。

## 總結
`enumerate` 函數是一個強大的工具，可以方便地獲取序列元素的索引和值。它不僅使代碼更簡潔，還能提高可讀性，是 Python 開發者必備的技能之一。