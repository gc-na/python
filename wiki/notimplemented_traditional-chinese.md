<!--
Meta Description: # Python中的NotImplemented：作用與使用指南 ## 簡介 在Python中，`NotImplemented`是一個特殊的常量，用於表示某個操作或方法尚未被實現。它常見於需要重寫的運算子或方法中，當開發者希望在子類別中實現某些功能但尚未完成時，使用`NotImplemented`可...
Meta Keywords: notimplemented, mynumber, value, self, other
-->

# Python中的NotImplemented：作用與使用指南

## 簡介
在Python中，`NotImplemented`是一個特殊的常量，用於表示某個操作或方法尚未被實現。它常見於需要重寫的運算子或方法中，當開發者希望在子類別中實現某些功能但尚未完成時，使用`NotImplemented`可以清晰地表達這一意圖。

## 文檔
### 目的
`NotImplemented`的主要目的是在運算符重載或自定義方法時，告訴Python該操作目前不可用，這樣有助於調試和維護代碼。

### 使用方法
在自定義類別中，當某個方法需要在未來實現但目前無法執行時，可以返回`NotImplemented`。這樣，當該方法被調用時，Python會明確告知開發者該方法未被實現。

### 詳細說明
- `NotImplemented`是內置的單例對象，通常用於運算符重載。
- 當運算符的實現不在當前類中時，返回`NotImplemented`可以讓Python嘗試使用其他類的相同運算符。
- 這在多重繼承及操作符重載時特別有用，因為它允許Python自動查找其他類的方法。

## 示例
以下是使用`NotImplemented`的基本範例：

```python
class MyNumber:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        if isinstance(other, MyNumber):
            return MyNumber(self.value + other.value)
        return NotImplemented

# 使用範例
num1 = MyNumber(10)
num2 = MyNumber(20)
result = num1 + num2  # 返回 MyNumber(30)

result2 = num1 + 5  # 返回 NotImplemented
```

在這個例子中，`MyNumber`類別重載了加法運算符。如果嘗試將`MyNumber`與其他類型相加，則返回`NotImplemented`，這樣Python可以處理該情況。

## 說明
- **常見陷阱**：如果一個方法返回`NotImplemented`，確保其他類別的相應方法能夠處理該情況，否則可能會導致意外的錯誤。
- **注意事項**：不要將`NotImplemented`用於表示錯誤或異常情況，它的用途專門是用於告訴Python該操作尚未被實現。

## 一句總結
`NotImplemented`是Python中的一個特殊常量，用於表示某個方法或操作尚未實現，並能有效地協助運算符重載和類別設計。