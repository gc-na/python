<!--
Meta Description: # Python 的 NotImplemented：用途、示例及常見問題 ## 簡介 `NotImplemented` 是 Python 中的一個內建常量，通常用於指示某個操作在當前上下文中未被實現。這個常量多用於運算符重載及與其他方法的交互中，幫助開發者明確地表達出某個功能尚未完成。 ## 文檔 ...
Meta Keywords: notimplemented, python, value, mynumber, self
-->

# Python 的 NotImplemented：用途、示例及常見問題

## 簡介
`NotImplemented` 是 Python 中的一個內建常量，通常用於指示某個操作在當前上下文中未被實現。這個常量多用於運算符重載及與其他方法的交互中，幫助開發者明確地表達出某個功能尚未完成。

## 文檔
### 目的
`NotImplemented` 的主要目的是幫助開發者在定義某個方法或操作時，表明此操作不支持或尚未實現，特別是在類別或函數中實現運算符重載的時候。

### 使用
當你在實現一個類時，如果某個運算符或方法並不適用於該類的實例，則可以返回 `NotImplemented`。這樣，Python 解釋器能夠知道該操作無法進行，並且可以嘗試其他可用的運算符或方法。

### 詳細信息
`NotImplemented` 是一個特殊的單例對象，屬於內建類型。它並不是一個錯誤或異常，而是一個特殊的返回值，用於告訴 Python 該操作無法處理。對於運算符重載，當返回 `NotImplemented` 時，Python 會自動尋找其他可能的替代方案或操作。

## 示例
以下是 `NotImplemented` 的基本用法示例：

```python
class MyNumber:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        if isinstance(other, MyNumber):
            return MyNumber(self.value + other.value)
        return NotImplemented

num1 = MyNumber(5)
num2 = MyNumber(10)

result = num1 + num2  # 正常運算
print(result.value)  # 輸出：15

result = num1 + 10  # 返回 NotImplemented
print(result)  # 輸出：NotImplemented
```

## 解釋
使用 `NotImplemented` 時，有一些常見的陷阱和注意事項：

- **未處理的返回值**：如果在類中返回 `NotImplemented`，確保調用者能夠處理這種情況，否則可能導致錯誤。
- **運算符的替代方案**：當返回 `NotImplemented` 時，Python 會自動嘗試使用其他方法，這可能導致意外的行為，特別是對於不同類型的運算符。

## 一句總結
`NotImplemented` 是用於指示某個操作未實現的特殊常量，幫助開發者在運算符重載中清晰地處理不支持的操作。