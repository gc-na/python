<!--
Meta Description: # Python 中的 ASCII 字符處理 ## 簡介 在 Python 中，ASCII（美國標準信息交換碼）是一種字符編碼標準，用於表示文本中所使用的字符。它涵蓋了從數字、英文字母到一些基本符號的編碼。Python 提供了多種工具來處理 ASCII 字符，以便開發者能夠輕鬆地進行字符的編碼和解碼...
Meta Keywords: ascii, python, ord, chr, 127
-->

# Python 中的 ASCII 字符處理

## 簡介
在 Python 中，ASCII（美國標準信息交換碼）是一種字符編碼標準，用於表示文本中所使用的字符。它涵蓋了從數字、英文字母到一些基本符號的編碼。Python 提供了多種工具來處理 ASCII 字符，以便開發者能夠輕鬆地進行字符的編碼和解碼。

## 文檔
ASCII 是一種使用 7 位元（即 0 到 127 的數字範圍）來表示字符的編碼系統。它是許多後來字符編碼標準的基礎，例如 UTF-8。Python 為處理 ASCII 字符提供了內建函數和方法，主要包括 `ord()` 和 `chr()` 函數，這些函數可以用於字符的轉換和編碼。

### 用法
- `ord()` 函數：接受一個字符作為參數，並返回其對應的 ASCII 整數值。
- `chr()` 函數：接受一個整數作為參數，並返回其對應的 ASCII 字符。

#### 語法
```python
ord(character)
chr(integer)
```

### 詳細說明
- `ord()`：如果傳入的字符不是 ASCII 字符，將引發 `TypeError`。
- `chr()`：傳入的整數必須在 0 到 127 的範圍內，否則將引發 `ValueError`。

## 範例
以下是一些基本的使用範例：

### 使用 `ord()`
```python
# 獲取字符 'A' 的 ASCII 值
ascii_value = ord('A')
print(ascii_value)  # 輸出: 65
```

### 使用 `chr()`
```python
# 獲取 ASCII 值 97 對應的字符
character = chr(97)
print(character)  # 輸出: 'a'
```

### 結合使用
```python
# 將字符轉換為 ASCII，再轉回字符
original_char = 'B'
ascii_val = ord(original_char)
converted_char = chr(ascii_val)
print(converted_char)  # 輸出: 'B'
```

## 解釋
在使用 ASCII 相關的函數時，開發者需要注意以下幾點：
- 確保傳入 `ord()` 的參數是單一字符，否則會引發 `TypeError`。
- 確保傳入 `chr()` 的整數在有效範圍內（0 至 127），否則會引發 `ValueError`。
- 與其他字符編碼標準相比，ASCII 只能表示基本的英文字母和符號，無法處理其他語言的字符。

## 一句總結
在 Python 中，ASCII 字符處理可通過 `ord()` 和 `chr()` 函數進行字符的編碼和解碼操作。