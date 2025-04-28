<!--
Meta Description: # Python 中的 chr 函數：字符轉換的利器 ## 概述 `chr` 是 Python 中的一個內建函數，用於將整數轉換為對應的 Unicode 字符。它在處理字符編碼和解碼時非常有用。 ## 文檔 ### 目的 `chr` 函數的主要作用是根據給定的整數返回對應的字符。整數必須是有效的 U...
Meta Keywords: chr, unicode, python, print, 代碼點
-->

# Python 中的 chr 函數：字符轉換的利器

## 概述
`chr` 是 Python 中的一個內建函數，用於將整數轉換為對應的 Unicode 字符。它在處理字符編碼和解碼時非常有用。

## 文檔
### 目的
`chr` 函數的主要作用是根據給定的整數返回對應的字符。整數必須是有效的 Unicode 代碼點（範圍在 0 到 1,114,111 之間）。

### 使用方式
```python
chr(i)
```
- **參數**：`i` 是一個整數，表示要轉換的 Unicode 代碼點。
- **返回值**：返回對應的字符（`str` 類型）。

### 詳細說明
- `chr` 是 Python 的內建函數，無需進行額外的導入。
- 當傳遞一個整數參數時，`chr` 函數返回該整數對應的字符。例如，`chr(65)` 返回 `'A'`。
- 這個函數非常適合用於處理字符編碼，特別是在需要生成或操作 Unicode 字符串的情況下。

## 範例
以下是一些使用 `chr` 函數的基本範例：

```python
# 示例 1：基本字符轉換
print(chr(65))  # 輸出：A

# 示例 2：轉換數字到字符
print(chr(97))  # 輸出：a

# 示例 3：Unicode 字符
print(chr(8364))  # 輸出：€ (歐元符號)

# 示例 4：遍歷 ASCII 表
for i in range(65, 91):
    print(chr(i), end=' ')  # 輸出：A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
```

## 解釋
### 常見陷阱與注意事項
- **範圍限制**：`chr` 函數的輸入必須在有效的 Unicode 代碼點範圍內（0 到 1,114,111），否則會引發 `ValueError`。
- **類型檢查**：確保傳入的參數是整數類型，否則會引發 `TypeError`。
- **Unicode 支持**：注意 Unicode 字符的多樣性，某些字符可能在特定環境下無法顯示。

## 一句總結
`chr` 函數是 Python 中用於將整數轉換為對應 Unicode 字符的重要工具，適合字符編碼和解碼的處理。