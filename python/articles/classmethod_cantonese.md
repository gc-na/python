<!--
Meta Description: # Python 的 classmethod: 用法與示例 ## 簡介 `classmethod` 是 Python 中的一個內置裝飾器，使得類別方法可以在類別本身上呼叫，而不是在某個實例上呼叫。這在需要存取或修改類別狀態時非常有用。 ## 文檔 ### 目的 `classmethod` 的主要目的...
Meta Keywords: classmethod, count, cls, myclass, python
-->

# Python 的 classmethod: 用法與示例

## 簡介
`classmethod` 是 Python 中的一個內置裝飾器，使得類別方法可以在類別本身上呼叫，而不是在某個實例上呼叫。這在需要存取或修改類別狀態時非常有用。

## 文檔
### 目的
`classmethod` 的主要目的是為了讓方法可以被類別本身而非實例所呼叫。這對於需要與類別相關的操作（例如工廠方法）非常方便。

### 用法
要使用 `classmethod`，你需要在方法前加上 `@classmethod` 裝飾器，並且該方法的第一個參數通常是 `cls`，表示該方法所屬的類別。

```python
class MyClass:
    @classmethod
    def my_class_method(cls):
        print(f"This is a class method of {cls.__name__}.")
```

### 詳細說明
- 當你定義一個類別方法時，它可以被類別或類別的實例呼叫。
- 這些方法通常用於需要類別層級的操作，例如創建類別的實例或修改類別屬性。
- `classmethod` 與 `staticmethod` 不同，後者不接受類別或實例的參數。

## 示例
以下是使用 `classmethod` 的基本示例：

```python
class MyClass:
    count = 0

    @classmethod
    def increment_count(cls):
        cls.count += 1
        print(f"Count is now: {cls.count}")

# 呼叫類別方法
MyClass.increment_count()  # 輸出: Count is now: 1
MyClass.increment_count()  # 輸出: Count is now: 2

# 通過實例呼叫類別方法
instance = MyClass()
instance.increment_count()  # 輸出: Count is now: 3
```

## 解釋
- **常見陷阱**: 使用 `classmethod` 時，切勿將其與 `staticmethod` 混淆。`staticmethod` 不會接收任何類別或實例的參數，這可能會導致錯誤的使用情境。
- **注意事項**: 當你在繼承的類別中重寫 `classmethod`，確保使用 `super()` 來調用父類別的方法，以避免意外的行為。

## 一句總結
`classmethod` 使得方法能夠被類別本身呼叫，從而在類別層級進行操作。