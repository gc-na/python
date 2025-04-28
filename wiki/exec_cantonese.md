<!--
Meta Description: # Python 中的 exec 函數：用法、範例與注意事項 ## 簡介 `exec` 是 Python 中的一個內建函數，允許用戶執行動態生成的 Python 代碼。此函數可用於執行字符串形式的 Python 程式碼，並可用於改變當前的命名空間。 ## 文檔 ### 目的 `exec` 函數的主要...
Meta Keywords: exec, python, globals, locals, locals_dict
-->

# Python 中的 exec 函數：用法、範例與注意事項

## 簡介
`exec` 是 Python 中的一個內建函數，允許用戶執行動態生成的 Python 代碼。此函數可用於執行字符串形式的 Python 程式碼，並可用於改變當前的命名空間。

## 文檔
### 目的
`exec` 函數的主要目的是執行包含 Python 代碼的字符串，並且可以選擇在特定的全局和局部命名空間中執行。

### 用法
```python
exec(object[, globals[, locals]])
```
- **object**: 要執行的字符串或代碼物件。
- **globals**: 可選，指定全局命名空間的字典。
- **locals**: 可選，指定局部命名空間的字典。

### 詳細說明
- `exec` 函數執行的代碼必須是有效的 Python 語法。
- 如果未提供 `globals` 和 `locals`，則使用調用 `exec` 的上下文中的命名空間。
- 如果提供 `globals`，則它必須是一個字典，表示全局命名空間。
- `locals` 也可以是字典，但如果不提供，則默認使用 `globals`。

## 範例
### 基本用法
```python
# 使用 exec 執行一行代碼
code = "print('Hello, World!')"
exec(code)
```
輸出：
```
Hello, World!
```

### 使用全局和局部命名空間
```python
# 定義全局變量
globals_dict = {"x": 10}
locals_dict = {}

# 使用 exec 在特定命名空間中執行代碼
exec("y = x + 5", globals_dict, locals_dict)

# 查看結果
print(locals_dict['y'])  # 輸出：15
```

## 解釋
### 常見陷阱
- 由於 `exec` 允許執行任意代碼，因此在使用時必須小心，避免執行來自不可信來源的代碼，這可能導致安全問題。
- 使用 `exec` 可能會使代碼難以閱讀和維護，應該謹慎使用。

### 附加說明
- `exec` 允許動態生成和執行代碼，但在大多數情況下，建議使用更安全和明確的編程方式來實現相同的功能。

## 一句話總結
`exec` 是 Python 中的一個強大工具，用於執行字符串形式的代碼，但必須謹慎使用以避免安全風險。