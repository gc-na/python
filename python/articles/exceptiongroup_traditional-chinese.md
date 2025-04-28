<!--
Meta Description: # ExceptionGroup: Python中的異常群組處理 ## 摘要 `ExceptionGroup` 是 Python 3.11 及以後版本引入的功能，旨在簡化異常處理，特別是在處理多個異常時。它允許將相關的異常打包在一起，使得錯誤處理更加清晰和有組織。 ## 文檔 `ExceptionG...
Meta Keywords: exceptiongroup, error, python, try, except
-->

# ExceptionGroup: Python中的異常群組處理

## 摘要
`ExceptionGroup` 是 Python 3.11 及以後版本引入的功能，旨在簡化異常處理，特別是在處理多個異常時。它允許將相關的異常打包在一起，使得錯誤處理更加清晰和有組織。

## 文檔
`ExceptionGroup` 是一個新的異常類型，用於組合多個異常。這在異步編程或多線程環境中特別有用，因為在這些情境中，可能會同時發生多個異常。使用 `ExceptionGroup`，開發者可以將這些異常打包在一起，並在一個地方進行處理。

### 目的
`ExceptionGroup` 的主要目的是讓開發者能夠更有效率地處理多個異常，而不必逐一捕獲和處理每個異常。它提供了一種結構化的方式來管理異常，使得代碼更加可讀和可維護。

### 使用
要使用 `ExceptionGroup`，只需將多個異常實例作為參數傳遞給 `ExceptionGroup` 類別的構造函數。然後，可以使用 `try...except` 塊來捕獲和處理這些異常。

### 詳細信息
- **初始化**: `ExceptionGroup` 的初始化方法接收一個異常的列表，並將其存儲在一個屬性中，以便後續訪問。
- **屬性**: `ExceptionGroup` 提供了一個 `exceptions` 屬性，返回所有被包裝的異常。
- **繼承**: `ExceptionGroup` 繼承自 `BaseException`，這使得它可以與其他異常類型一起使用。

## 範例
以下是一個簡單的使用範例：

```python
class CustomError1(Exception):
    pass

class CustomError2(Exception):
    pass

try:
    raise ExceptionGroup("Multiple errors occurred", [CustomError1("Error 1"), CustomError2("Error 2")])
except ExceptionGroup as eg:
    for error in eg.exceptions:
        print(f"Caught an error: {error}")
```

在這個範例中，兩個自定義異常被打包在一個 `ExceptionGroup` 中，然後在捕獲後逐一列印。

## 解釋
使用 `ExceptionGroup` 時，開發者需注意以下幾點：
- **版本要求**: `ExceptionGroup` 只在 Python 3.11 及以後版本可用，舊版本將無法使用此功能。
- **異常類型**: 確保傳遞給 `ExceptionGroup` 的都是異常實例，否則會引發錯誤。

## 一句總結
`ExceptionGroup` 是 Python 3.11 中引入的一種異常處理機制，旨在簡化多異常的捕獲和處理。