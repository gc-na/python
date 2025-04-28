<!--
Meta Description: # Python 中的布林值（bool）：用法與範例 ## 摘要 在 Python 中，`bool` 是一種內建的數據類型，用於表示真（True）和假（False）兩個邏輯值。`bool` 類型在控制程式流程和進行邏輯運算時至關重要。 ## 文檔 ### 目的 `bool` 類型的主要目的是表示 B...
Meta Keywords: bool, true, false, python, print
-->

# Python 中的布林值（bool）：用法與範例

## 摘要
在 Python 中，`bool` 是一種內建的數據類型，用於表示真（True）和假（False）兩個邏輯值。`bool` 類型在控制程式流程和進行邏輯運算時至關重要。

## 文檔
### 目的
`bool` 類型的主要目的是表示 Boolean 邏輯中的真偽值。在許多程式設計場景中，如條件判斷和迴圈控制，`bool` 值是決定程式執行路徑的關鍵。

### 用法
在 Python 中，`bool` 類型只有兩個有效的值：`True` 和 `False`。這兩個值的類型均為 `bool`，並且可以用於條件語句、邏輯運算和函數返回值等情況。

#### 轉換
除了直接使用 `True` 和 `False`，你還可以使用 `bool()` 函數將其他數據類型轉換為布林值。轉換規則如下：
- 數字：非零數字會轉換為 `True`，零會轉換為 `False`。
- 字串：非空字串會轉換為 `True`，空字串會轉換為 `False`。
- 集合：非空集合會轉換為 `True`，空集合會轉換為 `False`。

### 詳細說明
- **布林運算**：Python 支援多種布林運算符，例如 `and`、`or` 和 `not`，可用於對布林值進行操作。
- **條件語句**：`if` 語句使用布林值來決定是否執行特定代碼塊。
- **迴圈控制**：`while` 迴圈的條件判斷也依賴於布林值，其條件為 `True` 時持續執行。

## 範例
```python
# 創建布林值
is_active = True
is_finished = False

# 使用布林值進行條件判斷
if is_active:
    print("活動正在進行中")
else:
    print("活動已結束")

# 使用 bool() 函數轉換
print(bool(1))       # 輸出: True
print(bool(0))       # 輸出: False
print(bool("Hello")) # 輸出: True
print(bool(""))      # 輸出: False
```

## 解釋
在使用布林值時，開發者應注意以下幾點：
- 不同類型的數據轉換可能會導致意外結果，特別是當依賴於某些條件時。
- 在進行邏輯運算時，要確保使用正確的運算符，以免導致邏輯錯誤。
- Python 中的 `True` 和 `False` 是區分大小寫的，因此 `true` 和 `false` 會引發錯誤。

## 一行總結
在 Python 中，`bool` 類型用於表示邏輯值，並在條件判斷和邏輯運算中扮演重要角色。