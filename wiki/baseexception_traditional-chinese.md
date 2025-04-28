<!--
Meta Description: # BaseException：Python 中的基礎異常類型 ## 簡介 `BaseException` 是 Python 中所有異常的基礎類型。所有自訂的異常類別和內建異常類別均繼承自此類別。了解 `BaseException` 的運作方式對於異常處理與自訂異常類別至關重要。 ## 文件說明 `...
Meta Keywords: baseexception, python, exception, args, with_traceback
-->

# BaseException：Python 中的基礎異常類型

## 簡介
`BaseException` 是 Python 中所有異常的基礎類型。所有自訂的異常類別和內建異常類別均繼承自此類別。了解 `BaseException` 的運作方式對於異常處理與自訂異常類別至關重要。

## 文件說明
`BaseException` 是 Python 的內建異常類，作為所有異常的基礎。它定義了兩個重要的屬性：`args` 和 `with_traceback`。當一個異常被拋出時，`args` 會包含傳遞給異常的參數，而 `with_traceback` 方法則允許用戶將異常與其追蹤堆疊信息關聯起來。

```python
class BaseException(Exception):
    """所有異常的基類"""
    def __init__(self, *args: Any) -> None: ...
    def with_traceback(self, tb: Optional[TracebackType]) -> BaseException: ...
```

### 使用方式
`BaseException` 通常不應直接使用，而是應該擴展其子類別來創建特定的異常類型。常見的子類包括 `Exception`、`SystemExit`、`KeyboardInterrupt` 等。

## 範例
### 基本範例
以下是一個使用 `BaseException` 來自訂異常的範例：

```python
class MyCustomError(BaseException):
    pass

try:
    raise MyCustomError("這是一個自訂的異常")
except MyCustomError as e:
    print(f"捕獲到異常: {e}")
```

### 異常處理
在異常處理中，通常不會直接捕獲 `BaseException`，而是使用 `Exception`。這是因為 `BaseException` 包含了系統退出和鍵盤中斷等重要事件。

```python
try:
    raise BaseException("這是一個基礎異常")
except Exception as e:  # 此處不建議直接捕獲 BaseException
    print(f"捕獲到異常: {e}")
```

## 解釋
使用 `BaseException` 時需要注意以下幾點：
1. **避免直接捕獲**：直接捕獲 `BaseException` 可能導致無法正常處理程序的退出或中斷事件。
2. **使用子類別**：在自訂異常時，應該繼承自 `Exception` 而非 `BaseException`，以確保異常處理的正常運作。
3. **異常鏈**：使用 `raise ... from ...` 語法可以在異常之間建立鏈接，便於追蹤問題。

## 一句總結
`BaseException` 是 Python 的所有異常的基礎類型，通常不應直接使用，而是應透過其子類別來處理異常。