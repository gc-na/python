<!--
Meta Description: # Python 中的 GeneratorExit：了解生成器的結束信號 ## 概要 `GeneratorExit` 是 Python 中一種特殊的異常，用於在生成器被關閉時通知生成器進行清理操作。當生成器接收到這個異常時，應該進行必要的清理工作，如釋放資源或保存狀態。 ## 文檔 ### 目的 `...
Meta Keywords: generatorexit, python, close, finally, print
-->

# Python 中的 GeneratorExit：了解生成器的結束信號

## 概要
`GeneratorExit` 是 Python 中一種特殊的異常，用於在生成器被關閉時通知生成器進行清理操作。當生成器接收到這個異常時，應該進行必要的清理工作，如釋放資源或保存狀態。

## 文檔
### 目的
`GeneratorExit` 異常的主要目的是提供一種機制，以便在生成器被關閉時能夠進行適當的清理操作。這通常是透過 `close()` 方法觸發的，當你希望顯式地關閉生成器的時候。

### 使用方法
在生成器中，你可以使用 `try ... except` 結構來捕獲 `GeneratorExit` 異常，並進行相應的處理。當生成器被關閉時，Python 會自動觸發這個異常。

### 詳情
- 當調用生成器的 `close()` 方法時，生成器會引發 `GeneratorExit` 異常。
- 如果生成器內部沒有捕獲此異常，則會導致生成器立即終止。
- 捕獲 `GeneratorExit` 的最佳實踐是在生成器的 `finally` 塊中，這樣可以確保無論生成器如何終止，清理代碼都會被執行。

## 範例
以下是一個簡單的範例，展示了如何使用 `GeneratorExit`：

```python
def my_generator():
    try:
        yield "開始生成"
    except GeneratorExit:
        print("生成器被關閉，執行清理代碼")
    finally:
        print("這是 finally 塊中的代碼")

gen = my_generator()
print(next(gen))  # 輸出: 開始生成
gen.close()       # 輸出: 生成器被關閉，執行清理代碼
                  # 輸出: 這是 finally 塊中的代碼
```

## 解釋
### 常見問題
- **未捕獲的 `GeneratorExit`**：如果在生成器內部未捕獲此異常，生成器將會終止且不會執行 `finally` 塊中的代碼。
- **不當使用 `close()`**：在不需要關閉生成器的情況下調用 `close()` 可能會導致不必要的異常拋出，因此應謹慎使用。

### 附加說明
在設計生成器時，考慮到如何處理 `GeneratorExit` 是非常重要的，尤其是在涉及資源管理時。這將確保生成器能夠安全且有效地釋放資源。

## 一句總結
`GeneratorExit` 是 Python 中的異常，用於通知生成器進行清理操作，當生成器被關閉時會自動引發此異常。