<!--
Meta Description: # Python 中的 getattr 函數：用於動態屬性訪問 ## 概述 `getattr` 是 Python 中的一個內建函數，用於動態地訪問對象的屬性。這個函數可以根據提供的屬性名稱來獲取對象的屬性值，並且支持默認值的設定，是進行靈活編程的有力工具。 ## 文檔 ### 目的 `getattr...
Meta Keywords: getattr, name, person, python, attributeerror
-->

# Python 中的 getattr 函數：用於動態屬性訪問

## 概述
`getattr` 是 Python 中的一個內建函數，用於動態地訪問對象的屬性。這個函數可以根據提供的屬性名稱來獲取對象的屬性值，並且支持默認值的設定，是進行靈活編程的有力工具。

## 文檔
### 目的
`getattr` 的主要目的是讓開發者在不知道屬性名稱的情況下，仍然能夠安全地訪問對象的屬性。這在處理動態數據時特別有用。

### 用法
`getattr(object, name[, default])`

- **object**: 要訪問屬性的對象。
- **name**: 要訪問的屬性名稱，以字符串形式提供。
- **default**: 可選參數。如果指定的屬性不存在，則返回該默認值，否則會引發 AttributeError。

### 詳細說明
- 當 `getattr` 被調用時，它首先檢查對象上是否存在指定的屬性。如果存在，則返回該屬性的值；如果不存在且提供了默認值，則返回默認值；如果不存在且未提供默認值，則拋出 AttributeError。
- 此函數對於實現動態屬性訪問和處理不確定的對象結構特別有用。

## 示例
以下是 `getattr` 的基本用法示例：

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person("Alice", 30)

# 正常使用
name = getattr(person, 'name')
print(name)  # 輸出: Alice

# 使用默認值
height = getattr(person, 'height', '未知')
print(height)  # 輸出: 未知

# 嘗試訪問不存在的屬性，會引發錯誤
# weight = getattr(person, 'weight')  # 這將引發 AttributeError
```

## 解釋
- 使用 `getattr` 時要特別注意屬性名稱的正確性。如果屬性不存在且未提供默認值，將會引發 `AttributeError`，這可能會導致程序崩潰。
- 在多層對象訪問時，可以將 `getattr` 與其他內建函數結合使用，但要小心處理每一層的返回值，以避免錯誤。

## 一句總結
`getattr` 函數使得 Python 開發者能夠動態安全地訪問對象屬性，並提供了處理不存在屬性的靈活性。