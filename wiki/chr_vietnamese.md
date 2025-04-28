<!--
Meta Description: # Hàm `chr` trong Python: Tìm Hiểu và Cách Sử Dụng ## Tóm Tắt Hàm `chr` trong Python được sử dụng để chuyển đổi một số nguyên thành ký tự tương ứng tr...
Meta Keywords: chr, hàm, một, python, nguyên
-->

# Hàm `chr` trong Python: Tìm Hiểu và Cách Sử Dụng

## Tóm Tắt
Hàm `chr` trong Python được sử dụng để chuyển đổi một số nguyên thành ký tự tương ứng trong bảng mã Unicode. Đây là một công cụ hữu ích cho lập trình viên khi làm việc với các ký tự và chuỗi.

## Tài Liệu
Hàm `chr` là một hàm tích hợp sẵn trong Python, có chức năng nhận một số nguyên `n` và trả về ký tự Unicode tương ứng với số đó. Ký tự Unicode là một tiêu chuẩn quốc tế cho việc mã hóa văn bản, cho phép đại diện cho ký tự từ nhiều ngôn ngữ khác nhau.

### Cú Pháp
```python
chr(n)
```

### Tham Số
- `n`: Một số nguyên, phải nằm trong khoảng từ 0 đến 1114111 (0x10FFFF), tương ứng với các ký tự Unicode.

### Trả Về
Hàm `chr` trả về một chuỗi có độ dài 1, chứa ký tự tương ứng với số nguyên đã cho.

## Ví Dụ
### Ví Dụ Cơ Bản
```python
# Chuyển đổi số nguyên thành ký tự
print(chr(65))  # Kết quả: 'A'
print(chr(97))  # Kết quả: 'a'
print(chr(8364))  # Kết quả: '€'
```

### Ví Dụ với Vòng Lặp
```python
# In ra ký tự từ 65 đến 90
for i in range(65, 91):
    print(chr(i), end=' ')  # Kết quả: A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
```

## Giải Thích
Mặc dù hàm `chr` rất hữu ích, nhưng có một số điểm cần lưu ý:
- Nếu bạn truyền vào một số nguyên ngoài khoảng từ 0 đến 1114111, hàm sẽ gây ra lỗi `ValueError`.
- Hàm `chr` thường được sử dụng kết hợp với hàm `ord`, hàm này trả về số nguyên tương ứng với ký tự. Ví dụ:
```python
print(ord('A'))  # Kết quả: 65
print(chr(ord('A')))  # Kết quả: 'A'
```
- Đảm bảo rằng bạn đã hiểu rõ về bảng mã Unicode để sử dụng hàm hiệu quả.

## Tóm Tắt Một Dòng
Hàm `chr` trong Python chuyển đổi số nguyên thành ký tự Unicode tương ứng, hữu ích trong việc xử lý văn bản và chuỗi.