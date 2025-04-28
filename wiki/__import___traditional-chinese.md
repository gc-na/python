<!--
Meta Description: # Python 的 __import__ 函數: 動態匯入模組的強大工具 ## 概述 `__import__` 是 Python 的一個內建函數，用於動態匯入模組。它主要在需要在運行時決定要載入哪個模組的情況下使用，適合用於需要靈活性和擴展性的應用程式。 ## 文檔 ### 目的 `__impor...
Meta Keywords: __import__, python, fromlist, level, math
-->

# Python 的 __import__ 函數: 動態匯入模組的強大工具

## 概述
`__import__` 是 Python 的一個內建函數，用於動態匯入模組。它主要在需要在運行時決定要載入哪個模組的情況下使用，適合用於需要靈活性和擴展性的應用程式。

## 文檔
### 目的
`__import__` 函數使開發者能夠在運行時動態載入模組，相較於靜態的 `import` 語句，這提供了更高的靈活性。

### 語法
```python
__import__(name, globals=None, locals=None, fromlist=(), level=0)
```

### 參數
- `name`：要匯入的模組名稱（字串）。
- `globals`：一個字典，通常為 `globals()`，用於影響模組的匯入。
- `locals`：一個字典，通常為 `locals()`，同樣影響模組的匯入。
- `fromlist`：若指定為非空列表，則返回模組的指定屬性，否則返回模組本身。
- `level`：指定匯入的層級，0表示相對於當前模組，1表示相對於當前包。

### 返回值
返回被匯入的模組物件。

## 範例
### 基本用法
```python
# 動態匯入 'math' 模組
math_module = __import__('math')
print(math_module.sqrt(16))  # 輸出: 4.0
```

### 使用 fromlist
```python
# 動態匯入 'math' 模組中的 'sqrt' 函數
sqrt_function = __import__('math', fromlist=['sqrt'])
print(sqrt_function.sqrt(25))  # 輸出: 5.0
```

### 使用 level 參數
```python
# 假設有一個包結構：my_package/__init__.py 和 my_package/my_module.py
# 在 my_module.py 中動態匯入同一包中的 'my_function'
my_function = __import__('my_package.my_function', level=1)
```

## 解釋
### 常見問題
1. **模組名稱錯誤**：如果提供的模組名稱不存在，將引發 `ImportError`。
2. **使用 fromlist 時的誤解**：如果從 `fromlist` 中試圖匯入一個不存在的屬性，也會引發 `ImportError`。
3. **命名衝突**：如果模組名稱與內建名稱或其他模組名稱衝突，可能會導致意外行為。

### 附加說明
- 雖然 `__import__` 可以用來動態匯入模組，但通常建議使用 `importlib` 模組來進行更複雜的匯入操作，因為 `importlib` 提供了更清晰的 API 和功能。
- 由於`__import__` 是一個內建函數，使用時需謹慎，避免對代碼的可讀性造成影響。

## 一句話總結
`__import__` 函數是 Python 中用於動態匯入模組的強大工具，提供了在運行時靈活載入模組的能力。