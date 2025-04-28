<!--
Meta Description: # Python中的AssertionError：用於斷言檢查的例外 ## 摘要 AssertionError 是 Python 中用於表示斷言語句失敗的例外。當程序中使用 `assert` 語句檢查條件時，如果條件為假，則會引發此錯誤。 ## 文檔 ### 目的 AssertionError 的主...
Meta Keywords: assertionerror, python, assert, print, divide
-->

# Python中的AssertionError：用於斷言檢查的例外

## 摘要
AssertionError 是 Python 中用於表示斷言語句失敗的例外。當程序中使用 `assert` 語句檢查條件時，如果條件為假，則會引發此錯誤。

## 文檔
### 目的
AssertionError 的主要目的是在程式開發過程中進行錯誤檢查。通過斷言，開發者可以在程式執行時驗證某些條件是否為真，這有助於及早發現邏輯錯誤。

### 用法
在 Python 中，使用 `assert` 關鍵字來進行斷言檢查。其基本語法為：
```python
assert <condition>, <optional message>
```
- `<condition>`：要檢查的布林表達式。如果此表達式為假，將引發 AssertionError。
- `<optional message>`：可選的錯誤訊息，當斷言失敗時將顯示該訊息。

### 詳細說明
1. **基本原理**：當執行 `assert` 語句時，Python 會評估指定的條件。如果條件為假，將引發 AssertionError，並且程序的執行會被終止。
2. **環境**：在正常運行模式下（例如在生產環境中），斷言通常會被禁用（可以使用 `-O` 參數運行 Python）。因此，這種機制主要用於開發和測試階段。
3. **錯誤處理**：可以通過捕獲 AssertionError 來處理錯誤，這樣可以在發生錯誤時執行一些清理或日誌記錄操作。

## 範例
### 基本用法範例
```python
def divide(a, b):
    assert b != 0, "除數不能為零"
    return a / b

print(divide(10, 2))  # 輸出: 5.0
print(divide(10, 0))  # 引發 AssertionError: 除數不能為零
```

### 使用帶有錯誤訊息的斷言
```python
def check_age(age):
    assert age >= 18, "年齡必須大於或等於 18"
    return "通過年齡檢查"

print(check_age(20))  # 輸出: 通過年齡檢查
print(check_age(15))  # 引發 AssertionError: 年齡必須大於或等於 18
```

## 解釋
- **常見陷阱**：使用斷言進行輸入檢查並不總是最佳做法，因為斷言在生產環境中可能會被禁用。因此，對於用戶輸入的有效性檢查，應使用常規的錯誤處理機制。
- **性能考量**：在性能敏感的情況下，過多的斷言可能會影響程式執行效率，因為每個斷言都會在運行時進行評估。
- **調試工具**：AssertionError 的錯誤訊息對於調試非常有用，因為它可以幫助開發者迅速定位問題。

## 一句總結
AssertionError 是 Python 中用於檢查斷言條件是否為真的例外，通常用於開發和測試過程中。