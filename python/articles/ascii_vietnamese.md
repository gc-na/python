<!--
Meta Description: # ASCII trong Python: Hiểu Biết Cơ Bản và Cách Sử Dụng ## Tóm tắt ASCII (American Standard Code for Information Interchange) là một mã ký tự tiêu chuẩ...
Meta Keywords: ascii, trị, giá, hàm, python
-->

# ASCII trong Python: Hiểu Biết Cơ Bản và Cách Sử Dụng

## Tóm tắt
ASCII (American Standard Code for Information Interchange) là một mã ký tự tiêu chuẩn được sử dụng phổ biến trong lập trình. Trong Python, các hàm liên quan đến ASCII cho phép chuyển đổi các ký tự thành giá trị số nguyên tương ứng và ngược lại.

## Tài liệu
### Mục đích
Mã ASCII cung cấp cách để đại diện cho các ký tự trong một định dạng số, giúp máy tính có thể xử lý và lưu trữ văn bản một cách hiệu quả. Python hỗ trợ làm việc với mã ASCII thông qua một số hàm tích hợp.

### Cách sử dụng
- **ord()**: Hàm này nhận một ký tự (chuỗi có độ dài 1) và trả về giá trị ASCII tương ứng của ký tự đó.
- **chr()**: Ngược lại, hàm này nhận một số nguyên (trong khoảng 0 đến 1114111) và trả về ký tự tương ứng trong bảng mã Unicode, nhưng với các giá trị từ 0 đến 127, nó cũng tương ứng với ký tự ASCII.

### Chi tiết
- `ord(c)`: Trả về giá trị ASCII của ký tự `c`.
- `chr(i)`: Trả về ký tự tương ứng với giá trị ASCII `i`.

## Ví dụ
### Sử dụng hàm `ord()`
```python
# Lấy giá trị ASCII của ký tự 'A'
ascii_value = ord('A')
print(ascii_value)  # Kết quả: 65
```

### Sử dụng hàm `chr()`
```python
# Lấy ký tự tương ứng với giá trị ASCII 65
character = chr(65)
print(character)  # Kết quả: 'A'
```

### Kết hợp cả hai hàm
```python
# Chuyển đổi ký tự thành giá trị ASCII và ngược lại
char = 'B'
ascii_value = ord(char)
print(f"Gía trị ASCII của '{char}' là: {ascii_value}")  # Kết quả: 66

reverted_char = chr(ascii_value)
print(f"Ký tự tương ứng với giá trị {ascii_value} là: {reverted_char}")  # Kết quả: 'B'
```

## Giải thích
Khi làm việc với mã ASCII trong Python, một số vấn đề phổ biến có thể xảy ra:
- **Ký tự không hợp lệ**: Hàm `ord()` chỉ chấp nhận chuỗi có độ dài 1. Nếu bạn truyền một chuỗi dài hơn hoặc rỗng, Python sẽ nhắc lỗi.
- **Giá trị ngoài phạm vi**: Hàm `chr()` chỉ chấp nhận giá trị từ 0 đến 1114111. Nếu giá trị nằm ngoài khoảng này, cũng sẽ có thông báo lỗi.

## Tóm tắt một dòng
Hàm `ord()` và `chr()` trong Python cho phép bạn chuyển đổi giữa ký tự và giá trị ASCII, hỗ trợ việc xử lý văn bản hiệu quả.