<!--
Meta Description: # Python 的 NotImplementedError：用途、示例及注意事項 ## 概述 `NotImplementedError` 是 Python 中的一種異常，通常用於表示某個方法或功能尚未實現。這個異常的主要用途是在基類中定義抽象方法，提示子類需覆寫該方法。 ## 文檔 ### 目的 ...
Meta Keywords: notimplementederror, python, self, shape, area
-->

# Python 的 NotImplementedError：用途、示例及注意事項

## 概述
`NotImplementedError` 是 Python 中的一種異常，通常用於表示某個方法或功能尚未實現。這個異常的主要用途是在基類中定義抽象方法，提示子類需覆寫該方法。

## 文檔
### 目的
`NotImplementedError` 主要用於開發過程中，當你定義了某個方法但尚未實現其具體功能時，可以使用此異常來提醒開發者。這樣做能夠提高代碼的可讀性和可維護性。

### 使用
在 Python 中，`NotImplementedError` 可以通過 `raise` 語句來引發。例如，當你在基類中聲明了一個方法，但不打算在該類中提供具體實現時，可以這樣做：

```python
class BaseClass:
    def some_method(self):
        raise NotImplementedError("子類需要實現這個方法")
```

當你嘗試調用 `some_method` 而未在子類中覆寫時，將會引發 `NotImplementedError`。

### 詳細信息
- `NotImplementedError` 是 `RuntimeError` 的一個子類。
- 當捕獲到 `NotImplementedError` 時，開發者應該檢查是否在子類中正確實現了相應的方法。
- 此異常主要用於類的設計階段，幫助開發者明確哪些功能尚待實現。

## 示例
以下是使用 `NotImplementedError` 的基本示例：

```python
class Shape:
    def area(self):
        raise NotImplementedError("必須在子類中實現 area 方法")

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * (self.radius ** 2)

# 嘗試調用未實現的方法
shape = Shape()
# 這裡會引發 NotImplementedError
# shape.area()

circle = Circle(5)
print(circle.area())  # 輸出: 78.5
```

## 解釋
### 常見陷阱
1. **未覆寫方法**：如果子類忘記覆寫基類中的方法，調用該方法時將引發 `NotImplementedError`。
2. **錯誤的使用場景**：不應在普通函數中使用 `NotImplementedError`，這個異常主要用於類的抽象方法中。

### 注意事項
- 過度使用 `NotImplementedError` 可能會導致代碼難以理解，應該謹慎使用。
- 為每個引發此異常的地方添加清晰的錯誤消息，能夠幫助開發者更快定位問題。

## 一句總結
`NotImplementedError` 是 Python 中用於標誌尚未實現的方法的異常，能夠提高代碼的可讀性和可維護性。