<!--
Meta Description: # Số phức trong Python: Tìm hiểu về kiểu dữ liệu `complex` ## Tóm tắt Trong Python, kiểu dữ liệu `complex` được sử dụng để biểu diễn số phức, bao gồm ...
Meta Keywords: phức, phần, trong, thực, toán
-->

# Số phức trong Python: Tìm hiểu về kiểu dữ liệu `complex`

## Tóm tắt
Trong Python, kiểu dữ liệu `complex` được sử dụng để biểu diễn số phức, bao gồm phần thực và phần ảo. Loại số này hữu ích trong các lĩnh vực như toán học, kỹ thuật và khoa học máy tính.

## Tài liệu
Kiểu dữ liệu `complex` trong Python cho phép người dùng tạo và thao tác với các số phức. Số phức có cấu trúc dưới dạng `a + bj`, trong đó `a` là phần thực và `b` là phần ảo, còn `j` là ký hiệu dành riêng cho phần ảo trong Python (thay vì ký hiệu `i` thường thấy trong toán học).

### Cách sử dụng
- Để tạo một số phức, bạn có thể sử dụng cú pháp `complex(a, b)` hoặc sử dụng ký hiệu `a + bj`.
- Bạn có thể thực hiện các phép toán như cộng, trừ, nhân, chia với các số phức tương tự như với các số thực.

### Chi tiết
- **Khởi tạo số phức**: 
  - `z1 = complex(2, 3)` tạo ra số phức 2 + 3j.
  - `z2 = 1 + 2j` cũng tạo ra một số phức tương tự.
  
- **Truy cập các thành phần**:
  - Sử dụng thuộc tính `.real` để lấy phần thực: `z1.real` sẽ trả về `2`.
  - Sử dụng thuộc tính `.imag` để lấy phần ảo: `z1.imag` sẽ trả về `3`.

- **Phép toán**:
  - Cộng: `z1 + z2` cho kết quả là `(3+5j)`.
  - Nhân: `z1 * z2` cho kết quả là `(-4 + 7j)`.

## Ví dụ
```python
# Khởi tạo số phức
z1 = complex(2, 3)
z2 = 1 + 2j

# Hiển thị các phần
print("Phần thực của z1:", z1.real)  # Kết quả: 2.0
print("Phần ảo của z1:", z1.imag)    # Kết quả: 3.0

# Thực hiện phép toán
tong = z1 + z2
tich = z1 * z2

print("Tổng:", tong)                  # Kết quả: (3+5j)
print("Tích:", tich)                  # Kết quả: (-4+7j)
```

## Giải thích
Khi làm việc với số phức trong Python, có một số điều cần lưu ý:
- **Biểu diễn số phức**: Luôn sử dụng `j` cho phần ảo. Sử dụng `i` sẽ gây lỗi.
- **Phép toán**: Các phép toán số phức có thể cho ra kết quả không như mong đợi nếu bạn không quen với cách hoạt động của số phức.
- **Thao tác với số thực**: Khi kết hợp số thực và số phức, Python sẽ tự động chuyển đổi kiểu dữ liệu.

## Tóm tắt
Kiểu dữ liệu `complex` trong Python cho phép bạn làm việc với số phức dễ dàng và hiệu quả, hỗ trợ nhiều phép toán toán học phức tạp.