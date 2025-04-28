<!--
Meta Description: # Python 中的 __import__ 函數：靈活的模組導入工具 ## 簡介 `__import__` 是 Python 中一個內建函數，主要用於動態導入模組。對於需要在運行時決定導入哪些模組的情況，`__import__` 提供了一個靈活的解決方案。 ## 文檔 `__import__(na...
Meta Keywords: __import__, python, none, fromlist, mod_name
-->

# Python 中的 __import__ 函數：靈活的模組導入工具

## 簡介
`__import__` 是 Python 中一個內建函數，主要用於動態導入模組。對於需要在運行時決定導入哪些模組的情況，`__import__` 提供了一個靈活的解決方案。

## 文檔
`__import__(name, globals=None, locals=None, fromlist=(), level=0)`

### 目的
`__import__` 函數允許用戶在運行時導入模組。這對於需要根據條件或變數動態加載模組的情況特別有用。

### 用法
- **name**: 要導入的模組名稱（字符串類型）。
- **globals**: 可選，指定模組的全局變量，默認為 `None`。
- **locals**: 可選，指定模組的局部變量，默認為 `None`。
- **fromlist**: 可選，指定從模組中導入的對象的名稱列表，默認為空元組。
- **level**: 可選，指定導入的層級，0 表示相對導入，1 表示同級導入，2 表示上級導入，依此類推。

### 詳細說明
使用 `__import__` 可以在代碼中動態加載模組，這對於插件系統或某些需要根據用戶輸入選擇模組的應用情景非常有用。需要注意的是，這個函數返回的是模組對象，可以直接調用其屬性和方法。

## 範例
### 基本使用範例
```python
# 動態導入模組
mod_name = 'math'
math_module = __import__(mod_name)

# 使用導入的模組
result = math_module.sqrt(16)
print(result)  # 輸出: 4.0
```

### 從模組中導入特定對象
```python
# 導入特定函數
mod_name = 'math'
sqrt_function = __import__(mod_name, fromlist=['sqrt']).sqrt

# 使用導入的函數
result = sqrt_function(25)
print(result)  # 輸出: 5.0
```

## 解釋
使用 `__import__` 時需注意以下幾點：
- 當 `fromlist` 參數不為空時，返回的是指定的對象，而不是模組本身。
- 使用 `level` 進行相對導入時，必須確保導入的路徑正確。
- `__import__` 通常不建議在日常編程中使用，因為它的可讀性較差，且可能會導致代碼難以維護。對於一般情況，建議使用 `import` 語句。

## 總結
`__import__` 函數為 Python 提供了一種靈活的模組導入方式，尤其在動態導入模組的情況下極為有用。