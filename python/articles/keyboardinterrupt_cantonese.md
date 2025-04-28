<!--
Meta Description: # Python 中的 KeyboardInterrupt：中止程序的關鍵指令 ## 簡介 在 Python 程式中，`KeyboardInterrupt` 是一個用來處理用戶中止程式執行的例外情況。當用戶按下 Ctrl+C 時，Python 會引發這個例外，允許開發者進行相應的錯誤處理。 ## 文...
Meta Keywords: keyboardinterrupt, python, except, print, try
-->

# Python 中的 KeyboardInterrupt：中止程序的關鍵指令

## 簡介
在 Python 程式中，`KeyboardInterrupt` 是一個用來處理用戶中止程式執行的例外情況。當用戶按下 Ctrl+C 時，Python 會引發這個例外，允許開發者進行相應的錯誤處理。

## 文檔
`KeyboardInterrupt` 是內置的例外類型，當用戶希望終止正在執行的 Python 程式時，會引發此例外。它的主要目的是讓開發者能夠在程式中捕獲用戶的中止請求，從而進行適當的清理或狀態保存操作。

### 用法
在 Python 中，可以使用 `try...except` 語句來捕獲 `KeyboardInterrupt`。當程式執行到引發此例外的時候，控制權將轉移到相應的 `except` 區塊。

```python
try:
    while True:
        print("程式運行中，按 Ctrl+C 以中止。")
except KeyboardInterrupt:
    print("程式被用戶中止。")
```

## 示例
以下是幾個基本的使用範例：

### 簡單的中止示例
```python
try:
    input("按 Ctrl+C 嘗試中止程式...")
except KeyboardInterrupt:
    print("\n程式已中止！")
```

### 在循環中捕獲中止
```python
try:
    for i in range(10):
        print(i)
except KeyboardInterrupt:
    print("\n循環被中止！")
```

### 清理資源
```python
try:
    # 模擬長時間運行的任務
    while True:
        pass
except KeyboardInterrupt:
    print("清理資源，程式中止。")
```

## 解釋
在使用 `KeyboardInterrupt` 時，開發者應注意以下幾點：

- **用戶體驗**：捕獲 `KeyboardInterrupt` 可以改善用戶體驗，讓用戶知道程式已經收到中止請求並正在進行清理。
- **異常處理**：不捕獲 `KeyboardInterrupt` 會使程式異常終止，可能導致未完成的操作或資源未釋放。
- **多執行緒**：在多執行緒環境中，`KeyboardInterrupt` 可能不會像預期那樣立即響應，因為其他執行緒可能正在運行。

## 總結
`KeyboardInterrupt` 是 Python 中一個重要的例外類型，用於處理用戶中止程式的情況，幫助開發者進行適當的錯誤處理和資源管理。