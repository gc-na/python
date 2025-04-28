<!--
Meta Description: # Python 的例外處理 (Exception Handling) ## 概述 在 Python 中，例外處理是一種機制，用來捕獲和應對運行時錯誤，確保程式在發生錯誤時不會意外終止，並能夠優雅地處理問題。 ## 文檔 例外（Exception）是一種在程式運行時出現的錯誤情況。在 Python ...
Meta Keywords: python, try, except, finally, exception
-->

# Python 的例外處理 (Exception Handling)

## 概述
在 Python 中，例外處理是一種機制，用來捕獲和應對運行時錯誤，確保程式在發生錯誤時不會意外終止，並能夠優雅地處理問題。

## 文檔
例外（Exception）是一種在程式運行時出現的錯誤情況。在 Python 中，當發生例外時，程式的正常流程會被打斷，並轉而執行相應的例外處理代碼。這樣可以讓開發者更好地控制錯誤處理，提高程式的穩定性。

### 目的
例外處理的主要目的是捕獲錯誤，避免程式崩潰，並提供友好的錯誤提示或進行必要的清理工作。

### 用法
在 Python 中，使用 `try`、`except`、`else` 和 `finally` 語句來實現例外處理。基本語法如下：

```python
try:
    # 嘗試執行的代碼
except ExceptionType:
    # 當捕獲到特定類型的例外時執行的代碼
else:
    # 當沒有例外發生時執行的代碼
finally:
    # 無論是否發生例外，最終都會執行的代碼
```

## 範例
以下是幾個簡單的例外處理範例：

### 範例 1：捕獲零除錯誤
```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("你不能將數字除以零！")
```

### 範例 2：捕獲通用例外
```python
try:
    number = int(input("請輸入一個整數："))
except ValueError:
    print("輸入的不是有效的整數！")
```

### 範例 3：使用 finally
```python
try:
    file = open("example.txt", "r")
    content = file.read()
except FileNotFoundError:
    print("檔案未找到！")
finally:
    file.close()
```

## 解釋
在使用例外處理時，開發者應注意以下幾點：

- **捕獲特定例外**：盡量捕獲特定類型的例外，而不是使用通用的 `Exception`，這樣可以更好地控制錯誤處理的邏輯。
  
- **避免不必要的例外**：在可以避免的情況下，應避免使用例外來控制程式邏輯，這樣會影響效能。

- **清理資源**：使用 `finally` 語句來確保即使發生例外也能清理資源，例如關閉檔案或釋放網絡連接。

## 一句總結
在 Python 中，例外處理是一種有效的錯誤捕獲和處理機制，能夠提高程式的穩定性和可讀性。