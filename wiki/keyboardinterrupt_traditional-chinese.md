<!--
Meta Description: # Python 中的 KeyboardInterrupt：處理用戶中斷信號 ## 概要 `KeyboardInterrupt` 是 Python 中的一個內建異常，通常在用戶透過鍵盤輸入中斷執行中的程式時觸發。這個異常能夠讓開發者有效地控制程式的執行流程，並在需要時清理資源或結束操作。 ## 文檔...
Meta Keywords: keyboardinterrupt, python, except, print, try
-->

# Python 中的 KeyboardInterrupt：處理用戶中斷信號

## 概要
`KeyboardInterrupt` 是 Python 中的一個內建異常，通常在用戶透過鍵盤輸入中斷執行中的程式時觸發。這個異常能夠讓開發者有效地控制程式的執行流程，並在需要時清理資源或結束操作。

## 文檔
### 目的
`KeyboardInterrupt` 的主要目的是在程式執行過程中，允許用戶通過按下 `Ctrl+C` 鍵來中斷程式的執行。這個機制對於長時間運行的應用程式（如循環或數據處理）尤為重要。

### 使用方式
在 Python 中，當用戶按下 `Ctrl+C` 時，當前執行的程式會引發 `KeyboardInterrupt` 異常。開發者可以使用 `try...except` 語句來捕獲這個異常，以便在中斷發生時執行清理操作或給用戶提供反饋。

### 詳細說明
- **捕獲異常**：可以使用 `try...except KeyboardInterrupt:` 來處理這個異常。這樣可以在用戶中斷時執行特定的代碼。
- **清理資源**：在捕獲異常時，可以執行必要的清理操作，例如關閉文件或釋放網絡連接。
- **程序結束**：如果不捕獲這個異常，程序將會終止並顯示 traceback。

## 範例
以下是一些基本的使用範例，展示如何處理 `KeyboardInterrupt`：

### 範例 1：基本使用
```python
try:
    while True:
        print("按 Ctrl+C 來中斷程式...")
except KeyboardInterrupt:
    print("程式已被中斷！")
```

### 範例 2：清理資源
```python
import time

try:
    while True:
        print("執行中...")
        time.sleep(1)
except KeyboardInterrupt:
    print("程式被中斷，正在清理資源...")
    # 假設這裡有釋放資源的代碼
    print("資源已清理，程式結束。")
```

## 解釋
- **常見問題**：在某些情況下，`KeyboardInterrupt` 可能不會被捕獲，尤其是在某些第三方庫或長時間執行的系統調用中。
- **Gotchas**：如果在捕獲異常的過程中再次拋出該異常，則會導致程序無法正常結束。
- **注意事項**：在處理 `KeyboardInterrupt` 時，應避免在 `except` 塊中執行耗時的操作，因為這可能會影響用戶的體驗。

## 總結
`KeyboardInterrupt` 是一種用於處理用戶中斷信號的異常，能夠有效管理程式的執行流程並進行必要的清理操作。