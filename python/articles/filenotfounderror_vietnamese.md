<!--
Meta Description: # Lỗi FileNotFoundError trong Python: Nguyên Nhân và Cách Khắc Phục ## Tóm Tắt Lỗi `FileNotFoundError` trong Python là một ngoại lệ được ném ra khi mộ...
Meta Keywords: tập, tin, trong, một, không
-->

# Lỗi FileNotFoundError trong Python: Nguyên Nhân và Cách Khắc Phục

## Tóm Tắt
Lỗi `FileNotFoundError` trong Python là một ngoại lệ được ném ra khi một tập tin hoặc thư mục được yêu cầu không tồn tại trong hệ thống. Điều này thường xảy ra trong các thao tác đọc, ghi hoặc mở tập tin.

## Tài Liệu
`FileNotFoundError` là một loại ngoại lệ được định nghĩa trong Python, thuộc về module `builtins`. Nó là một phần trong hierachy của các ngoại lệ, cụ thể là một subclass của `OSError`. Khi bạn cố gắng truy cập một tập tin mà không tồn tại, Python sẽ ném ra lỗi này. 

### Mục Đích
Mục đích của `FileNotFoundError` là để thông báo cho lập trình viên rằng thư mục hoặc tập tin mà họ đang cố gắng truy cập không có mặt trên hệ thống.

### Cách Sử Dụng
Khi lập trình, bạn có thể sử dụng khối `try` và `except` để xử lý lỗi này. Ví dụ:

```python
try:
    with open('duong_dan_toi_tap_tin.txt', 'r') as file:
        nội_dung = file.read()
except FileNotFoundError:
    print("Tập tin không tồn tại.")
```

### Chi Tiết
- `FileNotFoundError` có hai tham số chính: `errno` và `strerror`, cho phép bạn biết được mã lỗi và thông điệp lỗi tương ứng.
- Ngoài việc sử dụng trong khối `try/except`, bạn cũng có thể kiểm tra sự tồn tại của tập tin trước khi mở nó bằng cách sử dụng module `os` hoặc `pathlib`.

## Ví Dụ
### Ví Dụ 1: Đọc Tập Tin
```python
try:
    with open('khong_ton_tai.txt', 'r') as file:
        print(file.read())
except FileNotFoundError:
    print("Tập tin không tồn tại.")
```

### Ví Dụ 2: Kiểm Tra Sự Tồn Tại
```python
import os

if os.path.exists('duong_dan_toi_tap_tin.txt'):
    with open('duong_dan_toi_tap_tin.txt', 'r') as file:
        print(file.read())
else:
    print("Tập tin không tồn tại.")
```

## Giải Thích
- Một trong những sai lầm phổ biến là không kiểm tra đúng đường dẫn đến tập tin. Đảm bảo đường dẫn là chính xác, bao gồm cả ký tự viết hoa và thường.
- Ngoài ra, hãy chú ý đến quyền truy cập vào thư mục. Nếu thư mục không cho phép truy cập, bạn cũng có thể gặp phải lỗi này.
- Việc sử dụng các phương thức như `os.path.isfile` có thể giúp bạn kiểm tra xem một đường dẫn có phải là tập tin hay không trước khi cố gắng mở nó.

## Tóm Tắt Trong Một Câu
`FileNotFoundError` trong Python là một ngoại lệ cho biết rằng tập tin hoặc thư mục mà bạn đang cố gắng truy cập không tồn tại.