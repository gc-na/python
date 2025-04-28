<!--
Meta Description: # Python 中的 NameError: 原因、用法及示例 ## 概述 在 Python 程式設計中，`NameError` 是一種常見的異常（exception），當程式嘗試使用未定義的變數或名稱時會引發此錯誤。 ## 文檔 `NameError` 的主要目的是幫助開發者識別在程式中使用未宣告...
Meta Keywords: nameerror, python, print, 將會引發, name
-->

# Python 中的 NameError: 原因、用法及示例

## 概述
在 Python 程式設計中，`NameError` 是一種常見的異常（exception），當程式嘗試使用未定義的變數或名稱時會引發此錯誤。

## 文檔
`NameError` 的主要目的是幫助開發者識別在程式中使用未宣告或未初始化的變數。這通常發生在變數名稱拼寫錯誤、作用域問題或變數尚未賦值的情況下。

### 使用方法
當 Python 解譯器發現一個名稱無法被識別時，會引發 `NameError`。開發者可以使用 `try-except` 塊來捕獲這個異常，以避免程式崩潰並提供更友好的錯誤信息。

## 示例
以下是一些簡單的示例，用以展示 `NameError` 的常見情況：

### 示例 1: 使用未定義的變數
```python
print(x)  # 將會引發 NameError
```
輸出：
```
NameError: name 'x' is not defined
```

### 示例 2: 拼寫錯誤
```python
number = 10
print(numbr)  # 將會引發 NameError
```
輸出：
```
NameError: name 'numbr' is not defined
```

### 示例 3: 在函數中使用未宣告的變數
```python
def my_function():
    print(a)  # 將會引發 NameError

my_function()
```
輸出：
```
NameError: name 'a' is not defined
```

## 說明
在處理 `NameError` 時，要注意以下幾點：

1. **作用域**: 確保變數在當前作用域內是可見的。局部變數只能在其定義的函數內使用。
2. **拼寫和大小寫**: Python 是區分大小寫的，因此 `variable` 和 `Variable` 被視為不同的名稱。
3. **初始化變數**: 在使用變數之前，必須先進行初始化。未初始化的變數將導致 `NameError`。
4. **避免全局變數的混淆**: 在函數內部使用全局變數時，需使用 `global` 關鍵字聲明。

## 一句總結
`NameError` 是 Python 中的一種異常，表示程式嘗試訪問未定義的變數或名稱。