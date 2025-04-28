<!--
Meta Description: # NameError trong Python: Hiểu và Khắc Phục Những Lỗi Thường Gặp ## Tóm tắt NameError là một loại lỗi trong Python xảy ra khi bạn cố gắng sử dụng một ...
Meta Keywords: biến, trong, nameerror, lỗi, một
-->

# NameError trong Python: Hiểu và Khắc Phục Những Lỗi Thường Gặp

## Tóm tắt
NameError là một loại lỗi trong Python xảy ra khi bạn cố gắng sử dụng một tên biến hoặc hàm chưa được định nghĩa.

## Tài liệu
NameError là một ngoại lệ (exception) trong Python, thường xuất hiện khi bạn tham chiếu đến một tên không tồn tại trong phạm vi hiện tại của chương trình. Điều này có thể xảy ra vì nhiều lý do, bao gồm việc không định nghĩa biến trước khi sử dụng, hoặc sai chính tả trong tên biến hoặc hàm.

### Cách sử dụng
Khi bạn gặp phải NameError, Python sẽ thông báo lỗi và dừng thực thi chương trình. Cú pháp của lỗi này thường được hiển thị như sau:

```
NameError: name 'tên_biến' is not defined
```

### Chi tiết
- **Nguyên nhân**: NameError thường xảy ra khi:
  - Biến hay hàm chưa được khai báo.
  - Tên biến bị viết sai chính tả.
  - Biến đã bị xóa hoặc không còn trong phạm vi của chương trình.

- **Phạm vi**: Lỗi này có thể xuất hiện trong các phạm vi khác nhau, bao gồm hàm, lớp, hoặc thậm chí trong toàn bộ chương trình chính.

## Ví dụ
### Ví dụ 1: Biến chưa định nghĩa
```python
print(x)
```
**Kết quả**:
```
NameError: name 'x' is not defined
```

### Ví dụ 2: Sai chính tả
```python
my_variable = 10
print(my_varible)
```
**Kết quả**:
```
NameError: name 'my_varible' is not defined
```

### Ví dụ 3: Biến đã xóa
```python
a = 5
del a
print(a)
```
**Kết quả**:
```
NameError: name 'a' is not defined
```

## Giải thích
- **Lỗi phổ biến**: Một trong những nguyên nhân chính gây ra NameError là lỗi chính tả. Bạn cần đảm bảo rằng tên biến hoặc hàm được khai báo và viết chính xác.
- **Phạm vi biến**: Nếu bạn định nghĩa một biến trong một hàm, biến đó sẽ không có sẵn bên ngoài hàm đó. Hãy kiểm tra phạm vi biến để đảm bảo rằng bạn đang sử dụng đúng biến trong đúng ngữ cảnh.
- **Khắc phục**: Để khắc phục NameError, bạn có thể:
  - Kiểm tra tên biến và hàm để đảm bảo rằng chúng đã được định nghĩa.
  - Sử dụng chức năng gợi ý của IDE để giúp phát hiện lỗi chính tả.
  - Đảm bảo rằng biến vẫn còn trong phạm vi khi được tham chiếu.

## Tóm tắt một câu
NameError trong Python là lỗi xảy ra khi bạn cố gắng sử dụng một tên biến hoặc hàm chưa được định nghĩa, thường do lỗi chính tả hoặc phạm vi không hợp lệ.