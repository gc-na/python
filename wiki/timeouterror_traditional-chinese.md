<!--
Meta Description: # Python TimeoutError：解釋與範例 ## 概述 `TimeoutError` 是 Python 中的一個異常類型，當一個操作超過預設的時間限制時會被引發。這通常發生在需要等待某些外部資源或操作的情況下，例如網絡請求或多執行緒操作。 ## 文檔 ### 目的 `TimeoutErr...
Meta Keywords: timeouterror, socket, python, requests, asyncio
-->

# Python TimeoutError：解釋與範例

## 概述
`TimeoutError` 是 Python 中的一個異常類型，當一個操作超過預設的時間限制時會被引發。這通常發生在需要等待某些外部資源或操作的情況下，例如網絡請求或多執行緒操作。

## 文檔
### 目的
`TimeoutError` 主要用來指示一個操作未能在預定的時間內完成。這是一種指示異常，通常與網絡連接、資料庫查詢及其他需要等待的操作有關。

### 用法
當一個操作因超過時間限制而失敗時，Python 會引發 `TimeoutError`。開發者可以使用 try-except 區塊來捕捉這個異常，以便優雅地處理錯誤情況。

### 詳細說明
- **引發條件**：`TimeoutError` 通常在你設定了一個最大等待時間，但操作卻未能在該時間內完成時被引發。
- **常見場景**：
  - 網絡請求使用 `requests` 模組時設定超時。
  - 使用 `socket` 進行網絡連接時的超時設定。
  - 在多執行緒或多進程環境中，等待某個操作的結果時的超時。

## 範例
以下是一些使用 `TimeoutError` 的基本範例：

### 範例 1：使用 requests 模組
```python
import requests

try:
    response = requests.get('https://httpbin.org/delay/5', timeout=3)
except requests.exceptions.Timeout:
    print("請求超時，發生 TimeoutError。")
```

### 範例 2：使用 socket 模組
```python
import socket

sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
sock.settimeout(2)  # 設定超時為2秒

try:
    sock.connect(('www.example.com', 80))
except socket.timeout:
    print("連接超時，發生 TimeoutError。")
```

### 範例 3：使用 asyncio 模組
```python
import asyncio

async def main():
    await asyncio.sleep(5)

try:
    asyncio.run(asyncio.wait_for(main(), timeout=2))
except asyncio.TimeoutError:
    print("操作超時，發生 TimeoutError。")
```

## 解釋
- **常見陷阱**：在捕獲 `TimeoutError` 時，確保你檢查的是正確的異常類型，因為不同的庫可能引發不同的異常（例如：`requests` 模組使用 `requests.exceptions.Timeout`）。
- **優雅處理**：在處理超時時，考慮加入重試機制或提供用戶友好的錯誤訊息。
- **影響效能**：適當的超時設置可以避免無限期等待，提升應用程式的效能與穩定性。

## 一句總結
`TimeoutError` 是 Python 中用來指示操作超過預設時間限制而未能成功的異常。