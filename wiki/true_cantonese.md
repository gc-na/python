<!--
Meta Description: # Python 中的 True：布爾類型的核心 ## 概述 在 Python 中，`True` 是布爾類型（Boolean type）的一部分，用於表示邏輯值「真」。它是 Python 中的內建常數之一，與 `False` 相對應，常用於條件判斷和邏輯運算。 ## 文檔 ### 目的 `True`...
Meta Keywords: true, python, false, print, 的整數值為
-->

# Python 中的 True：布爾類型的核心

## 概述
在 Python 中，`True` 是布爾類型（Boolean type）的一部分，用於表示邏輯值「真」。它是 Python 中的內建常數之一，與 `False` 相對應，常用於條件判斷和邏輯運算。

## 文檔
### 目的
`True` 確保我們可以進行邏輯運算和條件控制，並且在許多情況下用於判斷某些狀態是否為真。

### 用法
- `True` 是一個關鍵字，無需導入其他模組即可使用。
- 在條件語句（如 `if` 和 `while`）中，`True` 可作為條件判斷的基礎。
- `True` 也可以與其他數據類型進行比較和運算。

### 詳情
- 在 Python 3 中，`True` 是一個內建的常數，屬於 `bool` 類型。
- `True` 的整數值為 1，而 `False` 的整數值為 0。
- 使用布爾運算符（如 `and`, `or`, `not`）時，`True` 可與其他布爾值進行組合運算。

## 示例
### 基本用法
```python
# 使用 True 進行條件判斷
if True:
    print("這條語句會被執行")

# 使用 True 和 False 進行邏輯運算
a = True
b = False
print(a and b)  # 輸出: False
print(a or b)   # 輸出: True
print(not a)    # 輸出: False
```

## 解釋
- 一個常見的誤解是將 `True` 和整數混淆。雖然 `True` 的整數值為 1，但在邏輯運算中應該保持布爾語境。
- 當進行比較時，注意 `True` 與非布爾值的比較會返回布爾結果。
- 在 Python 中，`True` 的大小寫是敏感的，必須始終以大寫字母開頭。

## 一句總結
`True` 是 Python 中用於表示邏輯真值的內建常數，廣泛應用於條件判斷和邏輯運算。