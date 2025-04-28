<!--
Meta Description: # Từ điển (dict) trong Python: Cách sử dụng và ứng dụng ## Tóm tắt `dict` (từ điển) trong Python là một kiểu dữ liệu mạnh mẽ cho phép lưu trữ các cặp ...
Meta Keywords: khóa, điển, giá, trị, một
-->

# Từ điển (dict) trong Python: Cách sử dụng và ứng dụng

## Tóm tắt
`dict` (từ điển) trong Python là một kiểu dữ liệu mạnh mẽ cho phép lưu trữ các cặp khóa-giá trị, giúp truy cập dữ liệu một cách nhanh chóng và hiệu quả.

## Tài liệu
### Mục đích
`dict` là một cấu trúc dữ liệu quan trọng trong Python, giúp tổ chức và quản lý dữ liệu dưới dạng các cặp khóa-giá trị. Mỗi khóa trong từ điển là duy nhất và không thể thay đổi, trong khi giá trị có thể là bất kỳ kiểu dữ liệu nào, bao gồm cả danh sách, tuple và thậm chí là từ điển khác.

### Cách sử dụng
Tạo một từ điển trong Python có thể thực hiện bằng cách sử dụng dấu ngoặc nhọn `{}` hoặc hàm `dict()`. Dưới đây là cú pháp cơ bản để tạo và thao tác với từ điển:

```python
# Tạo từ điển bằng dấu ngoặc nhọn
my_dict = {'ten': 'Nguyễn Văn A', 'tuoi': 30, 'dia_chi': 'Hà Nội'}

# Tạo từ điển bằng hàm dict()
my_dict2 = dict(ten='Nguyễn Văn B', tuoi=25, dia_chi='Hồ Chí Minh')

# Truy cập giá trị theo khóa
print(my_dict['ten'])  # Kết quả: Nguyễn Văn A

# Thêm hoặc cập nhật giá trị
my_dict['tuoi'] = 31

# Xóa một cặp khóa-giá trị
del my_dict['dia_chi']
```

### Chi tiết
- **Tạo từ điển**: Bạn có thể tạo từ điển rỗng bằng cách sử dụng `my_dict = {}` hoặc `my_dict = dict()`.
- **Truy cập dữ liệu**: Sử dụng cú pháp `my_dict[‘khoa’]` để truy cập giá trị tương ứng với khóa.
- **Kiểm tra sự tồn tại của khóa**: Bạn có thể kiểm tra xem một khóa có tồn tại trong từ điển hay không bằng cách sử dụng cú pháp `khoa in my_dict`.
- **Phương thức hữu ích**: Một số phương thức hữu ích của từ điển bao gồm `keys()`, `values()`, và `items()`, cho phép bạn lấy ra danh sách các khóa, giá trị hoặc cả hai.

## Ví dụ
```python
# Tạo từ điển
person = {
    'name': 'Nguyễn Văn A',
    'age': 28,
    'city': 'Hà Nội'
}

# Truy cập và in ra thông tin
print(person['name'])  # Kết quả: Nguyễn Văn A

# Thay đổi giá trị
person['age'] = 29

# Thêm cặp khóa-giá trị mới
person['job'] = 'Lập trình viên'

# Xóa khóa-giá trị
del person['city']

# In ra từ điển cập nhật
print(person)  # Kết quả: {'name': 'Nguyễn Văn A', 'age': 29, 'job': 'Lập trình viên'}
```

## Giải thích
Một số lỗi thường gặp khi sử dụng từ điển:
- **Khóa trùng lặp**: Nếu bạn thêm một cặp khóa-giá trị với khóa đã tồn tại, giá trị sẽ được cập nhật mà không có thông báo lỗi.
- **Lỗi KeyError**: Khi bạn cố gắng truy cập một khóa không tồn tại, Python sẽ phát sinh lỗi `KeyError`. Bạn nên kiểm tra sự tồn tại của khóa trước khi truy cập.
- **Khóa không thể thay đổi**: Các khóa trong từ điển chỉ có thể là các kiểu dữ liệu không thay đổi như chuỗi, số và tuple. Danh sách không thể được sử dụng làm khóa.

## Tóm tắt một dòng
`dict` trong Python là một cấu trúc dữ liệu mạnh mẽ cho phép lưu trữ và quản lý dữ liệu theo cặp khóa-giá trị, giúp truy cập thông tin nhanh chóng và hiệu quả.