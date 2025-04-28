<!--
Meta Description: # NotImplementedError：Python 中的未實現錯誤 ## 摘要 `NotImplementedError` 是 Python 中的一種內建異常，通常用於表示某個方法或操作尚未實現，特別是在抽象基類或子類中。 ## 文檔 ### 目的 `NotImplementedError` ...
Meta Keywords: notimplementederror, python, my_method, mybaseclass, class
-->

# NotImplementedError：Python 中的未實現錯誤

## 摘要
`NotImplementedError` 是 Python 中的一種內建異常，通常用於表示某個方法或操作尚未實現，特別是在抽象基類或子類中。

## 文檔
### 目的
`NotImplementedError` 異常用來指出當前代碼的功能尚未實現。這是一種明確的方式，告訴開發者或使用者，某個方法或功能需要進一步的實現。

### 使用
在 Python 中，當一個方法應該被實現但尚未提供具體實現時，可以選擇引發 `NotImplementedError`。這通常發生在抽象基類中，當子類別需要覆寫此方法但尚未實現時。

### 詳細說明
- `NotImplementedError` 是 `RuntimeError` 的一個子類。
- 當你看到這個錯誤時，意味著該方法在當前上下文中不可用，開發者需要提供具體的實現。
- 這種異常通常在開發過程中使用，幫助開發者記錄尚未完成的工作。

## 範例
### 基本用法
以下是引發 `NotImplementedError` 的簡單範例：

```python
class MyBaseClass:
    def my_method(self):
        raise NotImplementedError("此方法尚未實現")

class MyDerivedClass(MyBaseClass):
    def my_method(self):
        return "這是我的實現"

# 使用範例
try:
    base_instance = MyBaseClass()
    base_instance.my_method()
except NotImplementedError as e:
    print(e)  # 輸出：此方法尚未實現

derived_instance = MyDerivedClass()
print(derived_instance.my_method())  # 輸出：這是我的實現
```

## 解釋
### 常見陷阱
- **抽象類別未實現方法**：如果在抽象類別中定義了一個方法，但子類別未覆寫該方法，就會引發 `NotImplementedError`。
- **測試期間**：開發者可能在測試過程中暫時使用 `NotImplementedError`，但在部署代碼時忘記實現，這會導致運行時錯誤。

### 額外說明
- 建議在引發 `NotImplementedError` 時，提供具體的錯誤訊息，這樣在調試時能夠更容易找到問題所在。
- `NotImplementedError` 主要用於開發階段，應該在最終版本中被實現的功能替代。

## 一句總結
`NotImplementedError` 是 Python 中用於表示某個方法尚未實現的異常，幫助開發者識別未完成的功能。