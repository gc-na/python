<!--
Meta Description: # Hàm `getattr` trong Python: Cách Sử Dụng và Ví Dụ Cụ Thể ## Tóm tắt Hàm `getattr` trong Python cho phép bạn truy cập các thuộc tính của một đối tượn...
Meta Keywords: thuộc, tính, getattr, không, bạn
-->

# Hàm `getattr` trong Python: Cách Sử Dụng và Ví Dụ Cụ Thể

## Tóm tắt
Hàm `getattr` trong Python cho phép bạn truy cập các thuộc tính của một đối tượng một cách linh hoạt. Nó giúp bạn lấy giá trị của thuộc tính dựa trên tên thuộc tính được cung cấp dưới dạng chuỗi, và có thể mặc định giá trị trả về nếu thuộc tính không tồn tại.

## Tài liệu
Hàm `getattr` là một hàm tích hợp sẵn trong Python, có thể được sử dụng để truy cập các thuộc tính của đối tượng. Cú pháp của nó như sau:

```python
getattr(object, name[, default])
```

### Tham số:
- **object**: Đối tượng mà bạn muốn truy cập thuộc tính.
- **name**: Tên thuộc tính mà bạn muốn lấy giá trị, dưới dạng chuỗi.
- **default** (tùy chọn): Giá trị mặc định được trả về nếu thuộc tính không tồn tại trong đối tượng.

### Mục đích:
Hàm `getattr` rất hữu ích khi bạn không chắc chắn về sự tồn tại của một thuộc tính trong một đối tượng, giúp tránh việc phát sinh lỗi `AttributeError`.

### Ví dụ:
Dưới đây là một số ví dụ cơ bản về cách sử dụng `getattr`:

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

my_car = Car("Toyota", "Corolla")

# Lấy thuộc tính 'brand'
brand = getattr(my_car, 'brand')
print(brand)  # Kết quả: Toyota

# Lấy thuộc tính không tồn tại với giá trị mặc định
color = getattr(my_car, 'color', 'Không có màu')
print(color)  # Kết quả: Không có màu
```

## Giải thích
Khi sử dụng `getattr`, bạn cần lưu ý một số điểm sau:

- **Tránh lỗi**: Sử dụng `getattr` là một cách an toàn để tránh lỗi khi thuộc tính không tồn tại. Nếu bạn sử dụng cú pháp thông thường (ví dụ: `my_car.color`), nếu thuộc tính `color` không tồn tại, Python sẽ ném ra một `AttributeError`.
- **Giá trị mặc định**: Nếu bạn không cung cấp giá trị mặc định, và thuộc tính không tồn tại, hàm sẽ ném ra lỗi.
- **Làm việc với lớp kế thừa**: `getattr` cũng hoạt động tốt với các lớp kế thừa, cho phép bạn truy cập các thuộc tính của lớp cha.

## Tóm tắt một câu
Hàm `getattr` trong Python cho phép bạn truy cập linh hoạt các thuộc tính của đối tượng mà không gây ra lỗi nếu thuộc tính không tồn tại, với khả năng cung cấp giá trị mặc định.