<!--
Meta Description: # Python 中的 chr 函數：用於字符轉換的工具 ## 簡介 `chr` 是 Python 中的一個內建函數，用於將整數轉換為對應的 Unicode 字符。這個函數在處理字符和編碼時非常有用，特別是在需要從數字代碼生成字符的情況下。 ## 文檔 ### 目的 `chr` 函數的主要目的是將一...
Meta Keywords: chr, unicode, python, 轉換為字符, print
-->

# Python 中的 chr 函數：用於字符轉換的工具

## 簡介
`chr` 是 Python 中的一個內建函數，用於將整數轉換為對應的 Unicode 字符。這個函數在處理字符和編碼時非常有用，特別是在需要從數字代碼生成字符的情況下。

## 文檔
### 目的
`chr` 函數的主要目的是將一個整數（Unicode 編碼）轉換為其對應的字符。Unicode 是一種字符編碼標準，涵蓋了世界上大多數語言的字符。

### 使用方法
`chr` 函數的語法如下：

```python
chr(i)
```

#### 參數
- `i`：一個整數，代表 Unicode 編碼，範圍從 0 到 0x10FFFF（即 0 到 1114111）。

#### 返回值
- 返回對應於給定整數的字符。如果整數不在有效範圍內，將會引發 `ValueError`。

## 示例
以下是一些使用 `chr` 函數的基本示例：

```python
# 將 Unicode 編碼 65 轉換為字符 'A'
char_a = chr(65)
print(char_a)  # 輸出：A

# 將 Unicode 編碼 97 轉換為字符 'a'
char_a_lower = chr(97)
print(char_a_lower)  # 輸出：a

# 將 Unicode 編碼 26085 轉換為字符 '漢'
char_han = chr(26085)
print(char_han)  # 輸出：漢
```

## 解釋
使用 `chr` 函數時，開發者需要注意以下幾點：

1. **有效範圍**：確保傳入的整數在有效的 Unicode 範圍內（0 到 1114111）。如果超出此範圍，將會引發 `ValueError`。
   
2. **字符類型**：`chr` 函數返回的是一個字符串，這在 Python 3 中是 Unicode 字符串，與 Python 2 的字節字符串有所不同。

3. **編碼問題**：在某些情況下，若使用不正確的編碼，可能會導致字符顯示不正確，因此在處理多語言文本時需特別注意。

## 一句話總結
`chr` 函數是 Python 用於將整數 Unicode 編碼轉換為字符的工具，簡潔而強大。