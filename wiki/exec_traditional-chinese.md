<!--
Meta Description: # Python 中的 exec 函数：使用說明與範例 ## 摘要 `exec` 是 Python 中一個強大的內建函數，允許動態執行 Python 程式碼。它能夠執行多行程式碼，並且可以操作當前的命名空間，適合用於需要動態生成或執行代碼的情境。 ## 文件說明 `exec(object[, glo...
Meta Keywords: exec, python, code, globals, locals
-->

# Python 中的 exec 函数：使用說明與範例

## 摘要
`exec` 是 Python 中一個強大的內建函數，允許動態執行 Python 程式碼。它能夠執行多行程式碼，並且可以操作當前的命名空間，適合用於需要動態生成或執行代碼的情境。

## 文件說明
`exec(object[, globals[, locals]])` 函數的主要目的是執行由字符串或編譯對象組成的 Python 程式碼。這個函數可以接收三個參數：

1. **object**：要執行的字符串或編譯對象。
2. **globals**（可選）：用來指定全局命名空間的字典。
3. **locals**（可選）：用來指定局部命名空間的字典。

### 使用方式
`exec` 函數在執行時，會在指定的全局和局部命名空間中運行程式碼。若未指定 `globals` 和 `locals` 參數，則會在當前的全局和局部命名空間中執行。

### 注意事項
- 使用 `exec` 執行的程式碼會直接影響當前的命名空間，這可能導致變數意外被覆蓋。
- 執行不受信任的程式碼可能帶來安全風險，應謹慎使用。

## 範例

### 基本範例
```python
code = 'print("Hello, World!")'
exec(code)
```

### 使用全局與局部命名空間
```python
global_scope = {}
local_scope = {}

code = '''
def greet():
    return "Hello from exec!"
result = greet()
'''

exec(code, global_scope, local_scope)
print(local_scope['result'])  # 輸出: Hello from exec!
```

### 動態變數
```python
var_name = 'x'
exec(f'{var_name} = 10')
print(x)  # 輸出: 10
```

## 解釋
使用 `exec` 時，有幾個常見的陷阱需要注意：
- **安全性**：執行不受信任的代碼可能導致安全問題，應避免在不安全的環境中使用。
- **命名空間衝突**：因為 `exec` 會直接修改當前的命名空間，可能導致變數名稱衝突或意外的行為。
- **性能問題**：`exec` 的執行速度通常比直接調用函數或執行常規代碼要慢，因此應僅在必要時使用。

## 總結
`exec` 函數是一個強大且靈活的工具，適合需要動態執行代碼的場景，但需謹慎使用以避免安全風險和命名空間問題。