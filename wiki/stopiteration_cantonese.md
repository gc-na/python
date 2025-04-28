<!--
Meta Description: # Python 中的 StopIteration：用於迭代的關鍵概念 ## 簡介 `StopIteration` 是 Python 中的一個內建異常，用於指示迭代器已經到達結尾。當迭代器的 `__next__()` 方法被調用，而沒有更多元素可供返回時，將引發此異常。 ## 文檔 ### 目的 `...
Meta Keywords: stopiteration, self, python, __next__, max
-->

# Python 中的 StopIteration：用於迭代的關鍵概念

## 簡介
`StopIteration` 是 Python 中的一個內建異常，用於指示迭代器已經到達結尾。當迭代器的 `__next__()` 方法被調用，而沒有更多元素可供返回時，將引發此異常。

## 文檔
### 目的
`StopIteration` 異常是 Python 迭代協定的一部分，用於告知迭代器的使用者（通常是 `for` 循環）何時停止迭代。這是一種優雅的方式來處理迭代的結束，而不是返回 `None` 或其他標記值。

### 用法
當你使用一個迭代器時，應該使用 `for` 循環來自動處理 `StopIteration`。如果手動調用 `__next__()` 方法，則需要對 `StopIteration` 進行適當的處理。

### 詳細說明
- `StopIteration` 是一個內建的異常類別，繼承自 `Exception`。
- 當沒有更多元素時，迭代器的 `__next__()` 方法應該引發 `StopIteration`。
- 在 `for` 循環中，自動捕獲 `StopIteration`，並結束循環。

## 示例
以下是如何使用 `StopIteration` 的基本示例：

### 自定義迭代器
```python
class MyIterator:
    def __init__(self, max):
        self.max = max
        self.current = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.current < self.max:
            self.current += 1
            return self.current
        else:
            raise StopIteration

# 使用自定義迭代器
for number in MyIterator(5):
    print(number)
```

### 手動調用 `__next__()`
```python
iterator = MyIterator(3)

while True:
    try:
        print(next(iterator))
    except StopIteration:
        break
```

## 解釋
- **常見陷阱**：手動調用 `__next__()` 時未捕獲 `StopIteration` 可能導致程式崩潰。
- **額外注意**：在使用 `for` 循環時不需要擔心 `StopIteration`，因為 Python 會自動處理。

## 一句總結
`StopIteration` 是 Python 迭代器的核心異常，用於有效地指示迭代結束。