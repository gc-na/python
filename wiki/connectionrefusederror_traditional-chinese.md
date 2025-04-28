<!--
Meta Description: # ConnectionRefusedError：Python中的連接拒絕錯誤 ## 概述 `ConnectionRefusedError` 是 Python 中一種特定的異常，當嘗試連接到一個未運行的服務器或端口時，會引發此錯誤。這通常發生在網絡編程中，特別是使用 socket 模組進行通信時。 ...
Meta Keywords: connectionrefusederror, socket, python, print, connect_to_server
-->

# ConnectionRefusedError：Python中的連接拒絕錯誤

## 概述
`ConnectionRefusedError` 是 Python 中一種特定的異常，當嘗試連接到一個未運行的服務器或端口時，會引發此錯誤。這通常發生在網絡編程中，特別是使用 socket 模組進行通信時。

## 文檔
### 目的
`ConnectionRefusedError` 是 `OSError` 的一個子類，用於指示連接請求被拒絕，這通常表示目標主機上沒有正在運行的服務器監聽指定的端口。

### 使用方法
當你使用 socket 進行網絡連接時，如果目標主機拒絕了連接請求，Python 會引發此異常。開發者可以通過捕捉此異常來處理連接失敗的情況。

### 詳細說明
- 當你嘗試連接一個服務器時，如果該服務器沒有啟動或未在指定端口上運行，則會引發 `ConnectionRefusedError`。
- 這種錯誤通常與網絡配置、服務器狀態或防火牆設置有關。
- 可以通過捕獲這個異常來實現重試機制或日誌記錄，以便進一步的故障排除。

## 例子
以下是捕獲 `ConnectionRefusedError` 的基本示例：

```python
import socket

def connect_to_server(host, port):
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect((host, port))
        print("連接成功")
    except ConnectionRefusedError:
        print("無法連接：連接被拒絕")
    except Exception as e:
        print(f"發生錯誤：{e}")

# 示例用法
connect_to_server('127.0.0.1', 8080)  # 假設該端口上未有服務器運行
```

## 解釋
- **常見陷阱**：請確認服務器是否正在運行，並檢查防火牆設置以確保該端口未被封鎖。
- **注意事項**：在處理網絡異常時，應該考慮到各種可能的錯誤，而不僅僅是 `ConnectionRefusedError`。例如，還可能遇到 `TimeoutError` 或 `ConnectionResetError` 等異常。

## 一行總結
`ConnectionRefusedError` 是一種在 Python 中表示連接請求被拒絕的異常，通常與服務器狀態有關。