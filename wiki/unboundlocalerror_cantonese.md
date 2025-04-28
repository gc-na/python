<!--
Meta Description: # UnboundLocalError：Python 本地變量錯誤的全面指南 ## 概要 `UnboundLocalError` 是 Python 中一種常見的錯誤，當試圖訪問一個本地變量，但該變量在其使用之前沒有被賦值時，會引發此錯誤。 ## 文檔 ### 目的 `UnboundLocalErro...
Meta Keywords: unboundlocalerror, python, example_function, print, def
-->

# UnboundLocalError：Python 本地變量錯誤的全面指南

## 概要
`UnboundLocalError` 是 Python 中一種常見的錯誤，當試圖訪問一個本地變量，但該變量在其使用之前沒有被賦值時，會引發此錯誤。

## 文檔
### 目的
`UnboundLocalError` 的主要目的是幫助開發者識別在函數或方法中未正確初始化的本地變量。這意味著在使用變量之前，必須先對其進行賦值。

### 使用
當你在一個函數中定義了一個變量，並試圖在該函數內部訪問它，但未對其進行賦值而直接使用，就會引發 `UnboundLocalError`。

### 詳細信息
在 Python 中，變量的作用域分為全局變量和本地變量。當你在函數內部使用一個變量時，Python 會將其視為本地變量。如果本地變量沒有被賦值就被引用，則會引發 `UnboundLocalError`。這個錯誤通常是由於變量的作用域和賦值順序不當造成的。

## 示例
以下是一個簡單的示例，演示如何觸發 `UnboundLocalError`：

```python
def example_function():
    print(x)  # 嘗試訪問本地變量 x
    x = 10    # 對 x 進行賦值

example_function()
```

運行上面的代碼會引發 `UnboundLocalError`，因為在 `print(x)` 語句中，`x` 尚未被賦值。

### 正確用法
以下是正確使用本地變量的示例：

```python
def example_function():
    x = 10  # 在使用之前賦值
    print(x)

example_function()  # 輸出 10
```

## 解釋
`UnboundLocalError` 常見的陷阱包括：
- 混淆全局變量和本地變量：如果函數內部有與全局變量同名的變量，Python 將視其為本地變量。
- 在賦值之前使用變量：確保在使用變量之前對其進行賦值。

另外，使用 `global` 關鍵字可以告訴 Python 使用全局變量而非創建本地變量：

```python
x = 5

def example_function():
    global x  # 使用全局變量 x
    print(x)
    x = 10    # 修改全局變量 x

example_function()  # 輸出 5
print(x)            # 輸出 10
```

## 一句總結
`UnboundLocalError` 是當你在函數中使用未賦值的本地變量時引發的錯誤。