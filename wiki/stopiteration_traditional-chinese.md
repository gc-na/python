<!--
Meta Description: # Python中的StopIteration：深入了解迭代終止的機制 ## 簡介 在Python編程中，`StopIteration`是一個重要的異常，用於指示迭代器已經達到其結束。了解這種異常對於編寫自定義迭代器和使用內建迭代協議至關重要。 ## 文檔 ### 目的 `StopIteration...
Meta Keywords: self, stopiteration, current, def, __next__
-->

# Python中的StopIteration：深入了解迭代終止的機制

## 簡介
在Python編程中，`StopIteration`是一個重要的異常，用於指示迭代器已經達到其結束。了解這種異常對於編寫自定義迭代器和使用內建迭代協議至關重要。

## 文檔
### 目的
`StopIteration`異常是Python內建的異常之一，主要用於控制迭代器的行為。當一個迭代器完成其所有元素的迭代時，必須引發`StopIteration`異常來通知使用者或調用者迭代已結束。

### 使用
在自定義迭代器時，`StopIteration`通常在`__next__()`方法中被引發。當迭代器沒有更多項目可供返回時，必須引發此異常，以便停止迭代。

```python
class MyIterator:
    def __init__(self, limit):
        self.limit = limit
        self.current = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.current < self.limit:
            value = self.current
            self.current += 1
            return value
        else:
            raise StopIteration  # 當沒有更多項目時引發 StopIteration
```

### 詳細說明
當使用`for`循環或其他迭代上下文時，Python自動處理`StopIteration`，因此使用者無需顯式捕獲此異常。然而，在自定義迭代器時，開發者需要明確引發這個異常以正確地結束迭代。

## 範例
以下是使用`StopIteration`的基本範例：

```python
# 自定義一個簡單的迭代器
class Countdown:
    def __init__(self, start):
        self.current = start

    def __iter__(self):
        return self

    def __next__(self):
        if self.current <= 0:
            raise StopIteration
        else:
            self.current -= 1
            return self.current + 1

# 使用迭代器
for number in Countdown(5):
    print(number)
```

輸出：
```
5
4
3
2
1
```

## 解釋
在使用`StopIteration`時，有一些常見的陷阱和注意事項：
- **自動處理**：在大多數情況下，`for`循環會自動捕獲`StopIteration`並停止迭代，因此開發者無需手動處理此異常。
- **不正確的引發**：如果在`__next__()`方法中未正確引發`StopIteration`，將導致無限迴圈或其他未定義行為。
- **使用生成器**：在使用生成器函數時，Python會自動處理`StopIteration`，開發者無需顯式引發。

## 一句話總結
`StopIteration`是Python中用於指示迭代器完成的異常，對於自定義迭代器的正確實現至關重要。