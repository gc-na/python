<!--
Meta Description: # Hiểu về __name__ trong Python: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Trong Python, `__name__` là một biến đặc biệt có vai trò quan trọng trong việc xác...
Meta Keywords: __name__, được, một, chạy, nhập
-->

# Hiểu về __name__ trong Python: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Trong Python, `__name__` là một biến đặc biệt có vai trò quan trọng trong việc xác định ngữ cảnh thực thi của một tập tin Python, giúp phân biệt giữa việc chạy một tập tin như một chương trình chính hay nhập khẩu nó như một mô-đun.

## Tài Liệu
### Mục Đích
Biến `__name__` được sử dụng để kiểm tra xem một tập tin Python có đang được chạy trực tiếp hay không. Nếu tập tin đó đang được chạy trực tiếp, giá trị của `__name__` sẽ là `"__main__"`. Ngược lại, nếu tập tin đó được nhập khẩu từ một tập tin khác, giá trị của `__name__` sẽ là tên của mô-đun.

### Cách Sử Dụng
Để sử dụng `__name__`, bạn thường thấy nó được kết hợp với câu lệnh điều kiện `if` như sau:

```python
if __name__ == "__main__":
    # Mã sẽ được thực thi chỉ khi tập tin này được chạy trực tiếp
    print("Chương trình đang được chạy trực tiếp")
else:
    print("Chương trình đang được nhập khẩu")
```

### Chi Tiết
- **Ngữ Cảnh**: Biến `__name__` rất hữu ích khi bạn muốn phân chia mã của mình thành các mô-đun có thể tái sử dụng. Bạn có thể viết mã kiểm tra trong khối `if __name__ == "__main__":` để chạy mã chỉ khi mô-đun đó được chạy trực tiếp.
- **Thay đổi tên mô-đun**: Nếu bạn thay đổi tên của mô-đun, giá trị của `__name__` sẽ tự động thay đổi theo tên mới, giúp giảm thiểu lỗi khi nhập khẩu.

## Ví Dụ
### Ví dụ Cơ Bản
Dưới đây là một ví dụ đơn giản minh họa cách sử dụng `__name__`:

```python
# my_module.py
def greet():
    print("Xin chào!")

if __name__ == "__main__":
    greet()
```

Khi bạn chạy `my_module.py` trực tiếp, nó sẽ in ra "Xin chào!". Tuy nhiên, nếu bạn nhập khẩu `my_module` từ một tập tin khác, hàm `greet()` không được gọi tự động.

### Ví dụ Nhập Khẩu
```python
# another_file.py
import my_module

print("Đã nhập khẩu my_module")
```

Khi bạn chạy `another_file.py`, nó sẽ in ra "Đã nhập khẩu my_module" mà không in "Xin chào!" vì đoạn mã trong khối `if __name__ == "__main__":` không được thực thi.

## Giải Thích
### Những Cái Bẫy Thông Thường
- **Nhầm lẫn giữa `__name__` và `__main__`**: Nhiều người mới học Python có thể nhầm lẫn giữa hai khái niệm này. `__name__` là biến đặc biệt, trong khi `__main__` là giá trị mà `__name__` nhận được khi chạy trực tiếp.
- **Sử dụng không đúng ngữ cảnh**: Nếu bạn không sử dụng `if __name__ == "__main__":` một cách chính xác, mã của bạn có thể gây ra nhầm lẫn hoặc lỗi khi được nhập khẩu.

## Tóm Tắt Một Dòng
Biến `__name__` trong Python cho phép xác định ngữ cảnh thực thi của một tập tin, giúp phân biệt giữa việc chạy trực tiếp và nhập khẩu mô-đun.