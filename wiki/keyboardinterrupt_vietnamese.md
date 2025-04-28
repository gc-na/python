<!--
Meta Description: # KeyboardInterrupt trong Python: Hiểu và Sử Dụng Hiệu Quả ## Tóm tắt `KeyboardInterrupt` là một ngoại lệ trong Python, được kích hoạt khi người dùng ...
Meta Keywords: trình, chương, keyboardinterrupt, khi, các
-->

# KeyboardInterrupt trong Python: Hiểu và Sử Dụng Hiệu Quả

## Tóm tắt
`KeyboardInterrupt` là một ngoại lệ trong Python, được kích hoạt khi người dùng nhấn tổ hợp phím Ctrl+C trong khi chương trình đang thực thi. Ngoại lệ này cho phép lập trình viên xử lý các tình huống dừng chương trình một cách an toàn.

## Tài liệu
### Mục đích
`KeyboardInterrupt` được sử dụng để quản lý các tình huống khi người dùng muốn ngừng một quá trình đang chạy. Điều này rất hữu ích trong các ứng dụng dài hạn hoặc khi chạy các quy trình không cần thiết.

### Cách sử dụng
Khi một chương trình Python đang chạy, người dùng có thể nhấn Ctrl+C để gửi tín hiệu ngắt đến chương trình. Điều này sẽ kích hoạt ngoại lệ `KeyboardInterrupt`. Lập trình viên có thể xử lý ngoại lệ này trong các khối lệnh `try` và `except` để thực hiện các hành động cần thiết trước khi chương trình dừng lại.

### Chi tiết
- **Khi nào xảy ra**: Khi người dùng nhấn Ctrl+C.
- **Cách xử lý**: Sử dụng cấu trúc `try...except` để bắt ngoại lệ và thực hiện các hành động cần thiết.
- **Mặc định**: Nếu không được xử lý, chương trình sẽ dừng ngay lập tức.

## Ví dụ
### Ví dụ cơ bản
```python
try:
    while True:
        print("Chương trình đang chạy... Nhấn Ctrl+C để dừng.")
except KeyboardInterrupt:
    print("Chương trình đã bị ngắt bởi người dùng.")
```

### Ví dụ với tài nguyên
```python
import time

try:
    print("Bắt đầu quá trình...")
    while True:
        time.sleep(1)
        print("Quá trình đang chạy...")
except KeyboardInterrupt:
    print("Ngắt quá trình. Đang giải phóng tài nguyên...")
    # Giải phóng tài nguyên nếu cần
    print("Quá trình đã dừng.")
```

## Giải thích
- **Sự cố phổ biến**: Nếu không xử lý `KeyboardInterrupt`, chương trình sẽ dừng mà không thông báo cho người dùng. Điều này có thể gây khó khăn cho việc kiểm soát các tác vụ đang diễn ra.
- **Ghi chú thêm**: Một số môi trường phát triển hoặc IDE có thể không phản hồi với Ctrl+C như mong đợi, vì vậy tốt nhất là thử chạy trong terminal hoặc command prompt.

## Tóm tắt một dòng
`KeyboardInterrupt` là ngoại lệ trong Python cho phép người dùng dừng chương trình một cách an toàn bằng cách nhấn Ctrl+C.