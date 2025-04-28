<!--
Meta Description: # Lệnh exec trong Python: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Lệnh `exec` trong Python cho phép thực thi mã Python được lưu trữ dưới dạng chuỗi, cu...
Meta Keywords: exec, thực, thi, python, được
-->

# Lệnh exec trong Python: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Lệnh `exec` trong Python cho phép thực thi mã Python được lưu trữ dưới dạng chuỗi, cung cấp khả năng tạo và thực thi mã động trong runtime.

## Tài liệu
### Mục đích
Lệnh `exec` được sử dụng để thực thi một đoạn mã Python được cung cấp dưới dạng chuỗi. Điều này hữu ích khi bạn muốn chạy mã mà không biết trước nội dung của nó, ví dụ như trong các trình thông dịch hoặc ứng dụng tương tác.

### Cú pháp
```python
exec(object[, globals[, locals]])
```
- **object**: Đối tượng cần thực thi, có thể là chuỗi chứa mã Python hoặc một mã đối tượng biên dịch.
- **globals**: (Tùy chọn) Từ điển chứa không gian tên toàn cục cho mã được thực thi.
- **locals**: (Tùy chọn) Từ điển chứa không gian tên cục bộ cho mã được thực thi.

### Chi tiết
- Nếu không chỉ định `globals` và `locals`, lệnh `exec` sẽ sử dụng không gian tên hiện tại.
- Khi `globals` và `locals` được chỉ định, chúng có thể là cùng một từ điển hoặc hai từ điển khác nhau.
- Lệnh `exec` có thể thực thi nhiều dòng mã, điều này có nghĩa là bạn có thể chạy các cấu trúc điều kiện, vòng lặp, và định nghĩa hàm.

## Ví dụ
### Ví dụ 1: Thực thi một chuỗi đơn giản
```python
code = "print('Hello, World!')"
exec(code)
```

### Ví dụ 2: Sử dụng với biến
```python
x = 10
exec("print('Giá trị của x là:', x)")
```

### Ví dụ 3: Thực thi nhiều dòng mã
```python
code = """
def greet(name):
    return 'Hello, ' + name

print(greet('Python'))
"""
exec(code)
```

## Giải thích
### Những cạm bẫy thường gặp
- **Bảo mật**: Sử dụng `exec` có thể tiềm ẩn rủi ro bảo mật nếu bạn thực thi mã không đáng tin cậy. Hãy tuyệt đối cẩn thận với đầu vào từ người dùng.
- **Hiệu suất**: Thực thi mã thông qua `exec` có thể chậm hơn so với mã được biên dịch tĩnh. Nên cân nhắc sử dụng các cách khác nếu hiệu suất là ưu tiên hàng đầu.
- **Phạm vi biến**: Khi sử dụng `globals` và `locals`, hãy chú ý đến cách mà các biến được truy cập và thay đổi, có thể dẫn đến lỗi khó phát hiện.

## Tóm tắt một dòng
Lệnh `exec` trong Python cho phép thực thi mã động được lưu trữ dưới dạng chuỗi, nhưng cần cẩn trọng với các vấn đề bảo mật và hiệu suất.