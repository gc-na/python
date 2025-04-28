<!--
Meta Description: # UnboundLocalError：Python 中的未綁定局部變數錯誤 ## 概述 `UnboundLocalError` 是 Python 中的一種異常，當試圖在函數內部使用一個局部變數，但該變數尚未被賦值時，會引發此錯誤。這通常發生在函數內部試圖讀取一個在函數內部未初始化的變數。 ## 文...
Meta Keywords: unboundlocalerror, python, global, example_function, print
-->

# UnboundLocalError：Python 中的未綁定局部變數錯誤

## 概述
`UnboundLocalError` 是 Python 中的一種異常，當試圖在函數內部使用一個局部變數，但該變數尚未被賦值時，會引發此錯誤。這通常發生在函數內部試圖讀取一個在函數內部未初始化的變數。

## 文檔
### 目的
`UnboundLocalError` 用於指示局部變數在使用前未被正確初始化。這是 Python 的一項語法規則，旨在防止使用未定義的變數。

### 使用方式
在 Python 中，變數的作用域分為全局變數和局部變數。當一個變數在函數內部被賦值時，Python 將其視為局部變數。如果嘗試在對該局部變數進行賦值之前使用它，將會引發 `UnboundLocalError`。

### 詳情
- **異常類型**：`UnboundLocalError` 繼承自 `NameError`。
- **發生情況**：當局部變數在被引用之前未賦值，或在函數內部的代碼塊中。
- **解決方法**：
  - 確保在使用變數之前進行賦值。
  - 如果需要在函數內部使用全局變數，應使用 `global` 關鍵字明確指定。

## 範例
以下是引發 `UnboundLocalError` 的基本示例：

```python
def example_function():
    print(x)  # 嘗試在賦值之前使用 x
    x = 10

example_function()  # 將引發 UnboundLocalError
```

正確的用法示例：

```python
x = 10

def example_function():
    global x  # 使用 global 關鍵字來引用全局變數
    print(x)
    x = 20

example_function()  # 輸出 10
print(x)  # 輸出 20
```

## 解釋
`UnboundLocalError` 通常會在以下情況下發生：
- 當代碼希望使用一個尚未賦值的局部變數。
- 當在函數內部意外地將全局變數的名稱重新定義為局部變數卻未進行賦值。
- 忘記在函數內部賦值就試圖訪問該變數。

### 常見陷阱
- 在條件語句中賦值但在某些情況下未執行賦值，導致在條件判斷外部使用該變數時出現 `UnboundLocalError`。
- 將變數名稱與全局變數相同，卻不使用 `global` 關鍵字，這將導致 Python 認為這是一個新的局部變數。

## 一句總結
`UnboundLocalError` 是 Python 中用來指示局部變數在使用前未被賦值的異常。