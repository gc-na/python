<!--
Meta Description: # ExceptionGroup trong Python: Xử lý Nhiều Ngoại Lệ cùng một Lúc ## Tóm tắt `ExceptionGroup` là một tính năng mới trong Python, cho phép lập trình viê...
Meta Keywords: exceptiongroup, ngoại, lỗi, trong, một
-->

# ExceptionGroup trong Python: Xử lý Nhiều Ngoại Lệ cùng một Lúc

## Tóm tắt
`ExceptionGroup` là một tính năng mới trong Python, cho phép lập trình viên xử lý nhiều ngoại lệ xảy ra đồng thời trong một khối mã. Điều này rất hữu ích trong các tình huống mà nhiều lỗi có thể phát sinh, chẳng hạn như khi làm việc với các tác vụ bất đồng bộ hoặc nhiều luồng.

## Tài liệu
`ExceptionGroup` được giới thiệu trong Python 3.11 và là một lớp ngoại lệ mới, cho phép nhóm nhiều ngoại lệ lại với nhau. Thay vì chỉ xử lý một ngoại lệ đơn, `ExceptionGroup` cho phép bạn thu thập và xử lý một tập hợp các ngoại lệ, giúp việc quản lý lỗi trở nên dễ dàng hơn.

### Mục đích
Mục đích chính của `ExceptionGroup` là để cải thiện khả năng xử lý lỗi trong các tình huống phức tạp, nơi mà nhiều lỗi có thể xảy ra đồng thời.

### Cách sử dụng
Để sử dụng `ExceptionGroup`, bạn có thể tạo một nhóm các ngoại lệ bằng cách khởi tạo nó với một danh sách các ngoại lệ. Bạn có thể xử lý ngoại lệ bằng cách sử dụng khối `try` và `except`.

### Cú pháp
```python
from exceptiongroup import ExceptionGroup

try:
    # Mã có thể gây ra nhiều ngoại lệ
    ...
except ExceptionGroup as eg:
    # Xử lý nhóm ngoại lệ
    for exc in eg.exceptions:
        print(f"Đã xảy ra lỗi: {exc}")
```

## Ví dụ
### Ví dụ 1: Nhóm ngoại lệ đơn giản
```python
from exceptiongroup import ExceptionGroup

def example_function():
    raise ValueError("Lỗi giá trị")
    raise TypeError("Lỗi kiểu")

try:
    example_function()
except ExceptionGroup as eg:
    for exc in eg.exceptions:
        print(f"Đã xảy ra lỗi: {exc}")
```

### Ví dụ 2: Nhóm ngoại lệ bất đồng bộ
```python
import asyncio
from exceptiongroup import ExceptionGroup

async def async_function():
    raise ValueError("Lỗi giá trị trong bất đồng bộ")
    raise TypeError("Lỗi kiểu trong bất đồng bộ")

async def main():
    try:
        await async_function()
    except ExceptionGroup as eg:
        for exc in eg.exceptions:
            print(f"Đã xảy ra lỗi: {exc}")

asyncio.run(main())
```

## Giải thích
Khi làm việc với `ExceptionGroup`, có một số điều cần lưu ý:

- **Khó khăn trong việc xác định nguồn gốc lỗi**: Khi nhiều ngoại lệ xảy ra, có thể khó xác định lỗi nào đã xảy ra đầu tiên hoặc quan trọng hơn.
- **Không hỗ trợ trong các phiên bản trước**: `ExceptionGroup` chỉ có sẵn trong Python 3.11 và các phiên bản mới hơn. Nếu bạn đang sử dụng một phiên bản cũ hơn, bạn sẽ không thể sử dụng tính năng này.
- **Kiến thức về lập trình bất đồng bộ**: Để tận dụng tối đa `ExceptionGroup`, việc hiểu biết về lập trình bất đồng bộ và việc xử lý lỗi trong các tác vụ bất đồng bộ là cần thiết.

## Tóm tắt một dòng
`ExceptionGroup` trong Python cho phép lập trình viên xử lý nhiều ngoại lệ đồng thời, cải thiện khả năng quản lý lỗi trong các tình huống phức tạp.