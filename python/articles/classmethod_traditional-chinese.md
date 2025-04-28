<!--
Meta Description: # Python 的 classmethod: 用途與範例 ## 摘要 `classmethod` 是 Python 中一種用於定義類別方法的裝飾器，允許方法訪問類別本身而非實例。這使得在類別層級上操作數據變得更加方便。 ## 文檔 `classmethod` 裝飾器將一個方法轉換為類別方法，這意味...
Meta Keywords: classmethod, myclass, python, cls, def
-->

# Python 的 classmethod: 用途與範例

## 摘要
`classmethod` 是 Python 中一種用於定義類別方法的裝飾器，允許方法訪問類別本身而非實例。這使得在類別層級上操作數據變得更加方便。

## 文檔
`classmethod` 裝飾器將一個方法轉換為類別方法，這意味著這個方法的第一個參數是類別本身，而不是實例。這樣的方法可以用來創建工廠方法或操作與類別相關的數據。

### 語法
```python
class ClassName:
    @classmethod
    def method_name(cls, args):
        # 方法內容
```

### 參數
- `cls`: 代表當前類別的引用，類似於實例方法中的 `self`。

### 用途
- 用於創建工廠方法，生成類別的實例。
- 能夠在類別層面上操作類別的屬性或方法。

## 範例
```python
class MyClass:
    count = 0

    def __init__(self):
        MyClass.count += 1

    @classmethod
    def get_count(cls):
        return cls.count

# 創建實例
obj1 = MyClass()
obj2 = MyClass()

# 使用類別方法
print(MyClass.get_count())  # 輸出: 2
```

## 解釋
使用 `classmethod` 時，應注意以下幾點：
- `classmethod` 不能訪問實例屬性（例如 `self`），它只能訪問類別屬性。
- 由於 `classmethod` 是綁定到類別的，因此可以通過類別名稱或類別的實例來調用它。
- 避免在類別方法中使用實例特有的行為，因為這可能會導致代碼的混淆。

## 一句總結
`classmethod` 是一種裝飾器，用於將方法定義為類別方法，使其能夠訪問類別而非實例。