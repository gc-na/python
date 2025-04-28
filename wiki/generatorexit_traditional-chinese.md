<!--
Meta Description: # GeneratorExit：Python 中的生成器退出異常 ## 簡介 `GeneratorExit` 是 Python 中的一種異常，用於終止生成器的運行。當生成器的 `close()` 方法被調用時，會引發此異常。這個異常主要用於清理資源，確保生成器在終止之前可以妥善處理任何必要的操作。 ...
Meta Keywords: generatorexit, close, python, print, gen
-->

# GeneratorExit：Python 中的生成器退出異常

## 簡介
`GeneratorExit` 是 Python 中的一種異常，用於終止生成器的運行。當生成器的 `close()` 方法被調用時，會引發此異常。這個異常主要用於清理資源，確保生成器在終止之前可以妥善處理任何必要的操作。

## 文檔
### 目的
`GeneratorExit` 的主要目的在於提供一種方式，讓生成器能夠在被關閉時進行清理工作，例如釋放資源或完成未完成的任務。這一異常是在生成器內部使用的，通常不會直接由用戶引發。

### 使用方法
當調用生成器的 `close()` 方法時，生成器內部會引發 `GeneratorExit` 異常，這使得生成器可以捕獲該異常來執行必要的清理工作。若生成器在處理 `GeneratorExit` 時不進行捕獲，則異常會被向上傳遞，最終導致生成器的終止。

### 詳細信息
- `GeneratorExit` 是 `BaseException` 的子類，因此無法被 `except Exception` 捕獲。
- 當生成器因為 `close()` 被關閉時，會自動引發 `GeneratorExit`，而用戶無需手動處理。
- 在生成器中捕獲此異常時，應確保執行必要的清理代碼，然後可以選擇重新引發異常或正常終止。

## 範例
以下是一個簡單的生成器示例，展示了如何處理 `GeneratorExit` 異常：

```python
def my_generator():
    try:
        yield 1
        yield 2
    except GeneratorExit:
        print("Generator is being closed. Cleaning up resources.")
    finally:
        print("Final cleanup.")

gen = my_generator()
print(next(gen))  # 輸出: 1
gen.close()       # 輸出: Generator is being closed. Cleaning up resources.
                  # 輸出: Final cleanup.
```

## 解釋
在使用生成器時，開發者需要注意以下事項：
- 確保在生成器中處理 `GeneratorExit` 異常，以便在生成器被關閉時進行必要的清理。
- 如果生成器沒有適當處理 `GeneratorExit`，可能會導致未釋放的資源或意外的行為。
- 使用 `finally` 塊可以確保即使在異常情況下也能執行清理代碼。

## 總結
`GeneratorExit` 是一個用於終止生成器的異常，允許開發者在生成器關閉時進行必要的清理工作。