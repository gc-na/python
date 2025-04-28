<!--
Meta Description: # Python FileNotFoundError 錯誤詳解 ## 簡介 `FileNotFoundError` 係 Python 中一種常見的異常錯誤，當你嘗試打開一個不存在的文件時，就會引發呢個錯誤。 ## 文檔 `FileNotFoundError` 係 Python 的內建異常類型之一，主...
Meta Keywords: filenotfounderror, python, file, file_path, open
-->

# Python FileNotFoundError 錯誤詳解

## 簡介
`FileNotFoundError` 係 Python 中一種常見的異常錯誤，當你嘗試打開一個不存在的文件時，就會引發呢個錯誤。

## 文檔
`FileNotFoundError` 係 Python 的內建異常類型之一，主要用於處理文件操作時發生的錯誤。當你使用 `open()` 函數或者其他文件操作函數（例如 `os` 模組）嘗試訪問一個不存在的文件或目錄，Python 會引發這個錯誤，並提供相關的信息。

### 用法
當你嘗試打開一個文件時，如果指定的路徑不正確或文件不存在，則會引發 `FileNotFoundError`。例如：

```python
file_path = '不存在的文件.txt'
with open(file_path, 'r') as file:
    content = file.read()
```

執行以上代碼會引發 `FileNotFoundError`，因為文件 `不存在的文件.txt` 無法找到。

## 範例
### 基本使用範例
```python
try:
    with open('example.txt', 'r') as file:
        content = file.read()
except FileNotFoundError:
    print("文件未找到！請檢查文件路徑。")
```

### 另一個範例
```python
import os

file_path = '另一個文件.txt'

if os.path.exists(file_path):
    with open(file_path, 'r') as file:
        print(file.read())
else:
    print("文件不存在，請確認文件路徑是否正確。")
```

## 解釋
`FileNotFoundError` 可能由於多種原因引起，包括：
- 文件名或路徑拼寫錯誤。
- 文件未正確創建或已被刪除。
- 使用了相對路徑而該路徑不正確。

要避免這個錯誤，建議在打開文件之前使用 `os.path.exists()` 檢查文件是否存在，或者確保正確的路徑和文件名。

## 總結
`FileNotFoundError` 係用於指示一個文件未找到的異常，通常由於路徑錯誤或文件不存在引起。