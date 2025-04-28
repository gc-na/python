<!--
Meta Description: # Python中的ConnectionRefusedError：连接被拒绝错误 ## 概述 `ConnectionRefusedError` 是 Python 中的一个内置异常，表示在尝试建立网络连接时，目标主机拒绝了连接请求。通常，这种错误会在使用 `socket` 模块或进行网络请求时出现。 ...
Meta Keywords: socket, connectionrefusederror, python, try, except
-->

# Python中的ConnectionRefusedError：连接被拒绝错误

## 概述
`ConnectionRefusedError` 是 Python 中的一个内置异常，表示在尝试建立网络连接时，目标主机拒绝了连接请求。通常，这种错误会在使用 `socket` 模块或进行网络请求时出现。

## 文档
### 目的
`ConnectionRefusedError` 主要用于指示客户端与服务器之间的连接请求未能成功，因为服务器端没有接受该连接。此异常通常发生在以下情况下：

- 目标服务器未启动或未监听指定端口。
- 防火墙或网络安全设置阻止了连接。
- 服务器达到最大连接限制。

### 用法
当 Python 的网络操作（如使用 `socket` 模块或依赖于网络的库）失败时，如果连接被拒绝，Python 会引发 `ConnectionRefusedError`。

可以通过捕获该异常来处理连接失败的情况。示例代码如下：

```python
import socket

try:
    # 尝试连接到服务器
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.connect(("localhost", 8080))
except ConnectionRefusedError:
    print("连接被拒绝，请检查服务器状态和端口是否正确。")
```

## 示例
以下是使用 `ConnectionRefusedError` 的基本示例：

```python
import socket

def connect_to_server(host, port):
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect((host, port))
        print("成功连接到服务器！")
    except ConnectionRefusedError:
        print(f"无法连接到 {host}:{port}，连接被拒绝。")

# 尝试连接到本地未启动的服务器
connect_to_server("localhost", 8080)
```

## 解释
### 常见问题
- **服务器未运行**：如果目标服务器未运行或未正确配置，连接请求将被拒绝。
- **端口错误**：确保指定的端口是服务器正在监听的端口。
- **防火墙设置**：某些防火墙可能会阻止入站连接，请检查防火墙规则。
- **最大连接限制**：服务器可能已达到其最大连接数，导致拒绝新的连接请求。

### 注意事项
- 在处理网络连接时，建议使用 `try-except` 块来捕获和处理 `ConnectionRefusedError`，以提高代码的健壮性。
- 使用 `socket` 模块时，确保在连接前创建并配置套接字。

## 一句话总结
`ConnectionRefusedError` 是在尝试连接一个未响应的服务器或端口时引发的异常，表示连接请求被拒绝。