<!--
Meta Description: # ModuleNotFoundError：Python 中常見的模塊未找到錯誤 ## 概述 `ModuleNotFoundError` 是 Python 中的一種錯誤，當 Python 解譯器無法找到指定的模塊時就會引發此錯誤。這通常發生在導入不正確的模塊名稱或模塊未安裝的情況下。 ## 文檔 #...
Meta Keywords: modulenotfounderror, python, import, numpy, importerror
-->

# ModuleNotFoundError：Python 中常見的模塊未找到錯誤

## 概述
`ModuleNotFoundError` 是 Python 中的一種錯誤，當 Python 解譯器無法找到指定的模塊時就會引發此錯誤。這通常發生在導入不正確的模塊名稱或模塊未安裝的情況下。

## 文檔
### 目的
`ModuleNotFoundError` 主要用於指示程序在導入模塊時遇到問題。這是一個子類別的 `ImportError`，專門處理找不到模塊的情況。

### 使用方法
在 Python 中，當您使用 `import` 語句導入模塊時，如果該模塊不存在，則會引發 `ModuleNotFoundError`。這是一個預設的異常，開發者可以通過捕獲這個異常來處理模塊未找到的情況。

### 詳細信息
- **異常類型**：`ModuleNotFoundError` 是 `ImportError` 的一種。
- **引發條件**：當模塊名稱拼寫錯誤、模塊不在 Python 的模塊搜尋路徑中，或模塊根本未安裝時，會引發此錯誤。

## 示例
以下是導入模塊時可能出現 `ModuleNotFoundError` 的一些示例：

### 示例 1：錯誤的模塊名稱
```python
try:
    import non_existent_module
except ModuleNotFoundError as e:
    print(f"錯誤：{e}")  # 這裡會顯示模塊未找到的錯誤信息
```

### 示例 2：未安裝的模塊
如果嘗試導入一個未安裝的第三方模塊，例如 `numpy`，則會遇到 `ModuleNotFoundError`。
```python
try:
    import numpy
except ModuleNotFoundError as e:
    print(f"錯誤：{e}")  # 如果 numpy 未安裝，會顯示相應的錯誤信息
```

## 解釋
### 常見問題
1. **模塊拼寫錯誤**：確保模塊名正確無誤，包括大小寫。
2. **模塊未安裝**：使用 `pip` 安裝所需的模塊。例如，使用 `pip install module_name` 來安裝。
3. **PYTHONPATH**：檢查環境變量 `PYTHONPATH` 是否包含模塊的路徑。
4. **虛擬環境**：如果使用虛擬環境，確保已在正確的環境中安裝模塊。

## 一句總結
`ModuleNotFoundError` 是 Python 中用於指示無法找到所需模塊的錯誤，通常與模塊名稱拼寫錯誤或未安裝模塊有關。