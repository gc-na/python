<!--
Meta Description: # Python 中的 `getattr` 函數：屬性獲取的靈活工具 ## 簡介 Python 的 `getattr` 函數是一個內建函數，用於獲取對象的屬性值。這個函數提供了一種動態訪問對象屬性的方法，並且能夠在屬性不存在時返回默認值，這使得它在處理不確定性時非常有用。 ## 文件說明 `geta...
Meta Keywords: getattr, name, john, age, python
-->

# Python 中的 `getattr` 函數：屬性獲取的靈活工具

## 簡介
Python 的 `getattr` 函數是一個內建函數，用於獲取對象的屬性值。這個函數提供了一種動態訪問對象屬性的方法，並且能夠在屬性不存在時返回默認值，這使得它在處理不確定性時非常有用。

## 文件說明
`getattr(object, name[, default])`

### 參數
- **object**: 需要獲取屬性的對象。
- **name**: 一個字符串，指定要獲取的屬性名稱。
- **default**: （可選）如果指定的屬性不存在時返回的默認值。如果未提供此參數，則會引發 `AttributeError`。

### 功能
`getattr` 函數的主要目的是允許動態獲取對象的屬性。這在需要根據用戶輸入或其他變量來決定使用哪個屬性時特別有用。通過提供一個默認值，開發者可以避免因屬性不存在而導致的錯誤。

### 使用範例
以下是 `getattr` 函數的基本使用範例：

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

john = Person("John", 30)

# 獲取屬性
name = getattr(john, 'name')  # 返回 'John'
age = getattr(john, 'age')    # 返回 30

# 獲取不存在的屬性，使用默認值
gender = getattr(john, 'gender', 'N/A')  # 返回 'N/A'
```

## 解釋
在使用 `getattr` 時，開發者可能會遇到一些常見的問題：

1. **屬性名稱錯誤**: 若提供的屬性名稱不存在且未提供默認值，將引發 `AttributeError`。這需要開發者確保所使用的屬性名稱正確。
   
2. **使用默認值**: 在許多情況下，提供默認值可以有效避免程序崩潰。開發者應根據需求合理選擇默認返回值。

3. **性能考量**: 雖然 `getattr` 提供了靈活性，但在性能敏感的場景中，過度使用可能會影響速度，特別是在大量對象上。

## 一句總結
`getattr` 函數是一個強大的工具，可以靈活地獲取 Python 對象的屬性並提供默認值，以避免屬性不存在的錯誤。