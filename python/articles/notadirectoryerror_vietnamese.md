<!--
Meta Description: # Lỗi NotADirectoryError trong Python: Nguyên Nhân và Cách Khắc Phục ## Tóm tắt Lỗi NotADirectoryError là một loại ngoại lệ trong Python, xảy ra khi m...
Meta Keywords: một, mục, thư, notadirectoryerror, đường
-->

# Lỗi NotADirectoryError trong Python: Nguyên Nhân và Cách Khắc Phục

## Tóm tắt
Lỗi NotADirectoryError là một loại ngoại lệ trong Python, xảy ra khi một thao tác yêu cầu một đường dẫn thư mục nhưng lại nhận được một đường dẫn tới một tệp tin thay vì thư mục.

## Tài liệu
### Mục đích
NotADirectoryError là một phần trong hệ thống quản lý ngoại lệ của Python, được sử dụng để xử lý các tình huống khi mã nguồn cố gắng truy cập vào một thư mục nhưng lại chỉ định một tệp tin không phải là thư mục.

### Cách Sử Dụng
Lỗi này thường gặp khi sử dụng các hàm yêu cầu đường dẫn thư mục, chẳng hạn như `os.listdir()`, `os.chdir()`, hoặc khi sử dụng các mô-đun liên quan đến tệp tin và thư mục. Khi Python phát hiện rằng đường dẫn được cung cấp không phải là thư mục, nó sẽ ném ra ngoại lệ NotADirectoryError.

### Chi Tiết
NotADirectoryError là một loại ngoại lệ con của OSError. Để xử lý lỗi này, bạn có thể sử dụng khối `try-except` để bắt và xử lý ngoại lệ, giúp chương trình của bạn không bị dừng đột ngột.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách NotADirectoryError có thể xảy ra:

### Ví dụ 1: Truy cập vào thư mục không tồn tại
```python
import os

try:
    os.listdir("file.txt")  # file.txt là tệp tin, không phải thư mục
except NotADirectoryError as e:
    print(f"Lỗi: {e}")
```

### Ví dụ 2: Chuyển đổi thư mục không hợp lệ
```python
import os

try:
    os.chdir("document.pdf")  # document.pdf là tệp tin, không phải thư mục
except NotADirectoryError as e:
    print(f"Lỗi: {e}")
```

## Giải thích
### Các vấn đề thường gặp
- **Đường dẫn không chính xác**: Đảm bảo rằng đường dẫn bạn cung cấp thực sự là một đường dẫn thư mục.
- **Tệp tin có cùng tên**: Nếu một tệp tin có cùng tên với thư mục mà bạn muốn truy cập, bạn sẽ gặp lỗi này.
- **Quyền truy cập**: Nếu bạn không có quyền truy cập vào thư mục, một số hệ thống có thể phản hồi bằng cách ném ra NotADirectoryError.

### Ghi chú bổ sung
- Kiểm tra đường dẫn trước khi thực hiện các thao tác trên nó có thể giúp giảm thiểu việc phát sinh lỗi này. Bạn có thể sử dụng `os.path.isdir()` để xác minh xem một đường dẫn có phải là thư mục hay không.

## Tóm tắt một câu
NotADirectoryError trong Python là lỗi xảy ra khi một thao tác yêu cầu một thư mục nhưng lại nhận được một tệp tin, cho thấy sự cần thiết phải xác minh đường dẫn trước khi thực hiện các thao tác liên quan đến tệp và thư mục.