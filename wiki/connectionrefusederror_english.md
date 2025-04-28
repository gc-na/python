<!--
Meta Description: # ConnectionRefusedError in Python: Understanding and Troubleshooting ## Synopsis `ConnectionRefusedError` is a built-in exception in Python that indi...
Meta Keywords: socket, server, port, connectionrefusederror, connection
-->

# ConnectionRefusedError in Python: Understanding and Troubleshooting

## Synopsis
`ConnectionRefusedError` is a built-in exception in Python that indicates a network connection attempt was rejected by the target machine. This commonly occurs in socket programming when a client attempts to connect to a server that is not accepting connections.

## Documentation
### Purpose
`ConnectionRefusedError` is part of the built-in exceptions in Python's `socket` module. It is raised when a connection attempt to a server is made, but the server is either not running, or it is not configured to accept connections on the specified port.

### Usage
When a client attempts to connect to a server using the `socket` library, it is important to handle potential exceptions to ensure the program can respond gracefully to connection issues. Catching `ConnectionRefusedError` allows developers to provide user-friendly error messages or retry logic.

### Details
- **Type:** Exception
- **Inherits from:** `OSError`
- **Introduced in:** Python 3.3

The exception can be raised in the following situations:
- The server is down or not started.
- The server is running but not accepting connections (e.g., due to firewall rules).
- The server is configured to listen on a different port than the one the client is trying to connect to.

## Examples

### Basic Example of ConnectionRefusedError
```python
import socket

def connect_to_server(host, port):
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect((host, port))
        print("Connected to the server!")
    except ConnectionRefusedError:
        print("Connection was refused. The server may not be running.")

# Attempt to connect to a non-existent server
connect_to_server('localhost', 9999)
```

### Handling ConnectionRefusedError
```python
import socket
import time

def connect_with_retry(host, port, retries=5):
    while retries > 0:
        try:
            s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
            s.connect((host, port))
            print("Successfully connected to the server!")
            return
        except ConnectionRefusedError:
            print("Connection refused, retrying...")
            retries -= 1
            time.sleep(2)  # Wait before retrying
    print("Failed to connect after several tries.")

connect_with_retry('localhost', 9999)
```

## Explanation
### Common Pitfalls
- **Server Not Running:** Ensure that the server you are trying to connect to is actively running and listening on the specified port.
- **Incorrect Port:** Double-check that the port number in the client matches the port the server is listening on.
- **Firewall or Network Issues:** A firewall may block connections, or there may be network configuration issues preventing access.
- **Socket Configuration:** Ensure that the socket is created and configured correctly before attempting a connection.

### Gotchas
- Not all platforms handle network exceptions in the same way. Always test your code in the environment where it will be deployed.
- Using the wrong address family (IPv4 vs IPv6) can lead to unexpected connection issues.

## One Line Summary
`ConnectionRefusedError` is a Python exception indicating that a network connection attempt was rejected by the server.