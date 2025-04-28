<!--
Meta Description: # Hàm divmod trong Python: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể ## Tóm Tắt Hàm `divmod` trong Python là một hàm tích hợp cho phép người dùng tính toán c...
Meta Keywords: divmod, hàm, thương, kết, quả
-->

# Hàm divmod trong Python: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể

## Tóm Tắt
Hàm `divmod` trong Python là một hàm tích hợp cho phép người dùng tính toán cả thương và số dư của phép chia hai số nguyên hoặc số thực. Hàm này trả về một tuple gồm hai giá trị: thương và số dư.

## Tài Liệu
### Mục Đích
Hàm `divmod` được sử dụng để thực hiện phép chia hai số và trả về kết quả dưới dạng một tuple. Kết quả này bao gồm:
- Thương: Kết quả của phép chia (số nguyên).
- Số dư: Phần còn lại sau khi thực hiện phép chia.

### Cú Pháp
```python
divmod(a, b)
```

- **a**: Số bị chia (có thể là số nguyên hoặc số thực).
- **b**: Số chia (có thể là số nguyên hoặc số thực, khác 0).

### Chi Tiết
- Nếu **a** và **b** là số nguyên, hàm sẽ trả về thương và số dư cũng là số nguyên.
- Nếu **a** hoặc **b** là số thực, hàm sẽ trả về thương dưới dạng số thực, nhưng số dư sẽ được tính toán dựa trên giá trị thực.
- Hàm sẽ ném ra ngoại lệ `ZeroDivisionError` nếu **b** bằng 0.

## Ví Dụ
### Ví dụ cơ bản
```python
# Ví dụ 1: Sử dụng divmod với số nguyên
thương, số_dư = divmod(10, 3)
print(thương)  # Kết quả: 3
print(số_dư)   # Kết quả: 1

# Ví dụ 2: Sử dụng divmod với số thực
thương, số_dư = divmod(10.5, 2)
print(thương)  # Kết quả: 5.0
print(số_dư)   # Kết quả: 0.5
```

### Ví dụ với ngoại lệ
```python
# Ví dụ 3: Sử dụng divmod với số chia là 0
try:
    divmod(10, 0)
except ZeroDivisionError as e:
    print(e)  # Kết quả: division by zero
```

## Giải Thích
- **Lưu ý về các loại số**: Khi sử dụng hàm `divmod`, hãy chú ý đến loại dữ liệu của các tham số. Việc sử dụng số nguyên với số thực có thể dẫn đến kết quả không như mong đợi nếu không được hiểu rõ.
- **Xử lý ngoại lệ**: Luôn kiểm tra xem số chia có bằng 0 hay không trước khi gọi hàm để tránh lỗi `ZeroDivisionError`.
- **Sử dụng tuple**: Kết quả của hàm `divmod` là một tuple, vì vậy bạn có thể sử dụng unpacking để lấy giá trị thương và số dư một cách thuận tiện.

## Tóm Tắt Một Dòng
Hàm `divmod` trong Python là công cụ hữu ích để tính toán thương và số dư của phép chia hai số, trả về kết quả dưới dạng một tuple.