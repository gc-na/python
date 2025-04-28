<!--
Meta Description: # Lệnh "exit" trong Python: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Lệnh `exit` trong Python được sử dụng để thoát khỏi chương trình hoặc môi trường tư...
Meta Keywords: exit, python, một, sys, trạng
-->

# Lệnh "exit" trong Python: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Lệnh `exit` trong Python được sử dụng để thoát khỏi chương trình hoặc môi trường tương tác. Đây là một công cụ hữu ích để kiểm soát luồng thực thi và dừng chương trình khi cần thiết.

## Tài liệu
Lệnh `exit` không phải là một lệnh chính thức trong Python, mà là một hàm được định nghĩa trong module `sys` hoặc một số môi trường tương tác như IDLE và Jupyter Notebook. Khi gọi lệnh này, chương trình sẽ dừng lại và trả về giá trị cho hệ điều hành hoặc môi trường thực thi.

### Cú pháp:
```python
import sys

sys.exit([status])
```
- **status**: Một số nguyên hoặc một đối tượng. Nếu là số nguyên, nó sẽ được sử dụng làm mã trạng thái trả về. Nếu không có giá trị nào được cung cấp, giá trị mặc định là `0` (thành công).

### Mục đích:
- Dừng chương trình Python đang chạy.
- Trả về mã trạng thái cho hệ điều hành.
- Thoát khỏi vòng lặp hoặc môi trường tương tác.

## Ví dụ
### Ví dụ 1: Thoát khỏi chương trình
```python
import sys

print("Chương trình đang chạy...")
sys.exit(0)  # Thoát với mã trạng thái 0
print("Dòng này sẽ không được in ra.")
```

### Ví dụ 2: Thoát với mã trạng thái khác
```python
import sys

print("Đã xảy ra lỗi!")
sys.exit(1)  # Thoát với mã trạng thái 1
```

### Ví dụ 3: Sử dụng trong vòng lặp
```python
import sys

while True:
    user_input = input("Nhập 'quit' để thoát: ")
    if user_input.lower() == 'quit':
        sys.exit(0)
```

## Giải thích
Khi sử dụng lệnh `exit`, có một số điểm cần lưu ý:
- Nếu bạn đang sử dụng Python trong một môi trường tương tác như IDLE hoặc Jupyter, lệnh `exit` sẽ dừng môi trường đó chứ không chỉ là chương trình.
- Mã trạng thái trả về mặc định là `0`, biểu thị cho sự thành công. Mã trạng thái khác (thường là `1` hoặc các số âm) thường chỉ ra rằng có lỗi xảy ra.
- Khi gọi `sys.exit()`, bạn có thể truyền một chuỗi để thông báo lỗi, nhưng điều này sẽ khiến Python ném ra một ngoại lệ `SystemExit`, do đó, không nên sử dụng chuỗi cho mã trạng thái.

## Tóm tắt một dòng
Lệnh `exit` trong Python cho phép người dùng dừng chương trình và trả về mã trạng thái cho hệ điều hành hoặc môi trường tương tác.