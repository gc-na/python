<!--
Meta Description: # NotImplemented trong Python: Giới thiệu và Hướng Dẫn Sử Dụng ## Tóm tắt `NotImplemented` là một hằng số trong Python được sử dụng để chỉ ra rằng một...
Meta Keywords: trong, một, notimplemented, phương, thức
-->

# NotImplemented trong Python: Giới thiệu và Hướng Dẫn Sử Dụng

## Tóm tắt
`NotImplemented` là một hằng số trong Python được sử dụng để chỉ ra rằng một phương thức hoặc hàm chưa được triển khai. Nó thường được dùng trong các lớp kế thừa để thông báo rằng một hành động cụ thể không được hỗ trợ.

## Tài liệu
### Mục đích
`NotImplemented` là một hằng số được định nghĩa trong module `builtins`. Nó chủ yếu được sử dụng trong các phương thức so sánh hoặc các phương thức khác mà không có thực hiện cụ thể trong lớp cha. Sử dụng `NotImplemented` giúp Python hiểu rằng phương thức này cần được thực hiện lại trong các lớp con.

### Cách sử dụng
Khi bạn định nghĩa một phương thức trong một lớp và không có ý định thực hiện nó, bạn có thể trả về `NotImplemented`. Điều này không chỉ giúp mã của bạn rõ ràng hơn mà còn cho phép Python xử lý các lỗi một cách hợp lý hơn trong các tình huống so sánh hoặc tính toán.

### Chi tiết
- Hằng số `NotImplemented` là một đối tượng duy nhất trong Python.
- Sử dụng `NotImplemented` thường thấy trong các phương thức như `__eq__`, `__add__`, và các phương thức toán học khác.
- Nếu bạn trả về `NotImplemented` trong một phương thức so sánh, Python sẽ thử tìm kiếm phương thức tương ứng trong lớp khác để thực hiện so sánh.

## Ví dụ
```python
class Shape:
    def area(self):
        return NotImplemented

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * (self.radius ** 2)

class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side ** 2

# Sử dụng
circle = Circle(5)
square = Square(4)

print(circle.area())  # Kết quả: 78.5
print(square.area())  # Kết quả: 16
```

## Giải thích
- **Lỗi thường gặp:** Một lỗi phổ biến là không sử dụng `NotImplemented` trong các phương thức so sánh. Điều này có thể dẫn đến việc so sánh không hoạt động hoặc gây ra lỗi không mong muốn.
- **Ghi chú thêm:** Trả về `NotImplemented` thay vì `None` hoặc một giá trị khác có thể giúp cải thiện khả năng tương thích của lớp khi được kế thừa. 

## Tóm tắt một dòng
`NotImplemented` là một hằng số trong Python được sử dụng để chỉ ra rằng một phương thức chưa được triển khai trong lớp hiện tại.