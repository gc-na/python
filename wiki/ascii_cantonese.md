<!--
Meta Description: # 在 Python 中使用 ASCII 的完整指南 ## 概述 在 Python 中，ASCII 是一種字符編碼標準，用於表示文本中的字母、數字和符號。它是用於計算機系統中的基本字符集，並在編程中廣泛使用。 ## 文檔 ### 目的 ASCII（美國信息交換標準碼）包含 128 個字符，包括英文字...
Meta Keywords: ascii, python, ord, chr, 整數值
-->

# 在 Python 中使用 ASCII 的完整指南

## 概述
在 Python 中，ASCII 是一種字符編碼標準，用於表示文本中的字母、數字和符號。它是用於計算機系統中的基本字符集，並在編程中廣泛使用。

## 文檔
### 目的
ASCII（美國信息交換標準碼）包含 128 個字符，包括英文字母、數字、標點符號和控制字符。Python 提供了內建函數來處理 ASCII 編碼，這些函數讓開發者能夠輕鬆地將字符轉換為其對應的 ASCII 整數值，或者從整數值恢復字符。

### 使用方式
在 Python 中，主要使用 `ord()` 和 `chr()` 來處理 ASCII 字符：
- `ord(char)`：返回字符 `char` 的 ASCII 整數值。
- `chr(int)`：返回整數 `int` 對應的字符。

### 詳細信息
- ASCII 範圍從 0 到 127，包括控制字符（如換行符）和可顯示字符（如字母和數字）。
- 對於超出 ASCII 範圍的字符，使用 Unicode 標準，Python 支持多種字符編碼。

## 示例
```python
# 將字符轉換為 ASCII 編碼
ascii_value = ord('A')  # 返回 65
print(ascii_value)

# 將 ASCII 編碼轉換為字符
character = chr(65)  # 返回 'A'
print(character)

# 使用 ASCII 編碼的範圍
for i in range(65, 91):  # 打印大寫字母 A 到 Z
    print(chr(i), end=' ')
```

## 解釋
- **常見陷阱**：使用 `ord()` 函數時，確保傳入的字符是單個字符，否則會引發錯誤。
- **注意事項**：如果嘗試將超出 ASCII 範圍的字符傳遞給 `ord()`，將返回對應的 Unicode 整數值，而非 ASCII 值。
- 使用 `chr()` 時，請確保傳入的整數在 0 到 1114111 的範圍內，以避免引發錯誤。

## 一句總結
在 Python 中，使用 `ord()` 和 `chr()` 函數可以方便地進行 ASCII 字符與其整數值之間的轉換。