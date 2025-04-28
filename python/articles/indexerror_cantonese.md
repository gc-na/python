<!--
Meta Description: # Python 中的 IndexError：常見錯誤及其處理方法 ## 概要 IndexError 是 Python 中的一種常見錯誤，當嘗試訪問序列（如列表、元組或字符串）中的不存在的索引時，將引發此錯誤。 ## 文檔 ### 目的 IndexError 的主要目的是告知開發者他們正在嘗試訪問的...
Meta Keywords: indexerror, python, my_list, print, 將引發
-->

# Python 中的 IndexError：常見錯誤及其處理方法

## 概要
IndexError 是 Python 中的一種常見錯誤，當嘗試訪問序列（如列表、元組或字符串）中的不存在的索引時，將引發此錯誤。

## 文檔
### 目的
IndexError 的主要目的是告知開發者他們正在嘗試訪問的序列索引超出了範圍。這通常發生在序列的長度小於所請求的索引值時。例如，對於一個包含三個元素的列表，使用索引 3 會引發 IndexError，因為有效索引為 0、1 和 2。

### 使用方法
在 Python 中，當你對列表、元組或字符串使用索引時，必須確保所用的索引在有效範圍內。有效範圍是從 0 到 n-1，其中 n 是序列的長度。

### 詳細信息
- **引發情況**：當你使用的索引值小於 0 或大於或等於序列的長度時，將會引發 IndexError。
- **錯誤信息**：錯誤信息通常會顯示出發生錯誤的序列類型及所用的索引值。

## 範例
以下是一些示範 IndexError 的簡單範例：

```python
# 範例 1：訪問列表中的不存在索引
my_list = [1, 2, 3]
print(my_list[3])  # 將引發 IndexError

# 範例 2：訪問元組中的不存在索引
my_tuple = (5, 6, 7)
print(my_tuple[5])  # 將引發 IndexError

# 範例 3：訪問字符串中的不存在索引
my_string = "Hello"
print(my_string[10])  # 將引發 IndexError
```

## 解釋
在使用索引訪問序列時，開發者應當注意以下幾點：
- **索引範圍**：確保索引在有效範圍內，使用 `len()` 函數來獲取序列的長度。
- **負索引**：Python 允許使用負數作為索引，這意味著可以從序列的末尾開始倒數。例如，對於列表 `my_list`，`my_list[-1]` 會返回最後一個元素。然而，如果負索引超出了範圍，仍然會引發 IndexError。
- **異常處理**：可以使用 `try-except` 語句來捕捉 IndexError，從而避免程式崩潰。

```python
try:
    print(my_list[3])
except IndexError:
    print("索引超出範圍！")
```

## 一句摘要
IndexError 是指在 Python 中當訪問序列的無效索引時所引發的錯誤。