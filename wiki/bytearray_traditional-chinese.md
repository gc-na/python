<!--
Meta Description: # Python 的 bytearray：可變的位元組序列 ## 概述 `bytearray` 是 Python 中一種可變的位元組序列類型，允許用戶在操作二進位資料時對其進行修改。它在處理需要更改的位元組數據時非常有用，並提供了比不可變的 `bytes` 類型更高的靈活性。 ## 文檔 `byte...
Meta Keywords: bytearray, python, hello, source, print
-->

# Python 的 bytearray：可變的位元組序列

## 概述
`bytearray` 是 Python 中一種可變的位元組序列類型，允許用戶在操作二進位資料時對其進行修改。它在處理需要更改的位元組數據時非常有用，並提供了比不可變的 `bytes` 類型更高的靈活性。

## 文檔
`bytearray` 類型的主要目的是創建一個可變的二進位數據序列。它可以通過多種方式初始化，包括從字串、列表或其他 `bytes` 或 `bytearray` 對象。其語法如下：

```python
bytearray([source[, encoding[, errors]]])
```

- **source**: 可選參數，可以是可迭代對象（如字串、列表等），或者是整數，表示要創建的 `bytearray` 長度。
- **encoding**: 當 source 是字串時，指定字串的編碼方式。
- **errors**: 當 source 是字串時，指定錯誤處理的策略。

### 主要特性
- **可變性**: 與 `bytes` 不同，`bytearray` 可以就地修改其內容。
- **支持切片**: 可以使用切片操作來獲取或修改 `bytearray` 的部分內容。
- **支持多種編碼**: 可以從字串創建 `bytearray`，並使用不同的編碼。

## 示例
以下是一些 `bytearray` 的基本用法示例：

```python
# 從字符串創建 bytearray
b = bytearray("Hello", "utf-8")
print(b)  # 輸出: bytearray(b'Hello')

# 修改 bytearray 的內容
b[0] = 104  # 將 'H' 修改為 'h'
print(b)  # 輸出: bytearray(b'hello')

# 追加新內容
b.extend(bytearray(b' World'))
print(b)  # 輸出: bytearray(b'hello World')

# 切片操作
sliced = b[0:5]
print(sliced)  # 輸出: bytearray(b'hello')
```

## 解釋
使用 `bytearray` 時需要注意幾個常見的陷阱：

1. **類型不兼容**: 當從不可迭代的對象（如整數）創建 `bytearray` 時，必須明確指定其長度。無法直接從整數創建，必須使用像 `bytearray(5)` 這樣的初始化方式。
   
2. **編碼問題**: 當從字串創建 `bytearray` 時，必須確保使用正確的編碼，否則將會引發 `UnicodeEncodeError`。

3. **內存使用**: 由於 `bytearray` 是可變的，對其進行多次修改可能會導致額外的內存分配，從而影響性能。

## 總結
`bytearray` 是 Python 中一種靈活且可變的位元組序列，適合用於需要修改二進位數據的場景。