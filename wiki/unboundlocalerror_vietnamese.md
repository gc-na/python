<!--
Meta Description: # UnboundLocalError trong Python: Lỗi Biến Địa Phương Không Được Gán ## Tóm tắt UnboundLocalError là một loại lỗi trong Python xảy ra khi bạn cố gắng ...
Meta Keywords: biến, được, một, khi, trong
-->

# UnboundLocalError trong Python: Lỗi Biến Địa Phương Không Được Gán

## Tóm tắt
UnboundLocalError là một loại lỗi trong Python xảy ra khi bạn cố gắng truy cập một biến địa phương trong hàm mà chưa được gán giá trị. Đây là một trong những lỗi phổ biến mà lập trình viên mới gặp phải khi làm việc với biến trong phạm vi hàm.

## Tài liệu
UnboundLocalError là một phần của hệ thống xử lý lỗi trong Python, cụ thể là một ngoại lệ được nâng cao từ `NameError`. Lỗi này xuất hiện khi một biến địa phương được sử dụng trước khi nó được gán giá trị trong hàm. Python phân biệt rõ ràng giữa biến toàn cục và biến địa phương; nếu một biến được gán trong một hàm, Python coi nó là biến địa phương trừ khi được khai báo là biến toàn cục bằng từ khóa `global`.

### Mục đích
Mục đích của UnboundLocalError là để bảo vệ các biến khỏi việc được sử dụng mà không có giá trị, từ đó giúp lập trình viên nhận ra các lỗi trong mã của họ.

### Sử dụng
Khi bạn định nghĩa một hàm và cố gắng truy cập một biến địa phương mà chưa được khởi tạo, Python sẽ ném ra UnboundLocalError. Bạn có thể tránh lỗi này bằng cách đảm bảo rằng tất cả các biến địa phương được gán giá trị trước khi sử dụng.

## Ví dụ
Dưới đây là một số ví dụ đơn giản để minh họa lỗi UnboundLocalError:

### Ví dụ 1: Lỗi UnboundLocalError
```python
def tinh_tong():
    print(x)  # Cố gắng truy cập biến x trước khi nó được gán giá trị
    x = 10

tinh_tong()
```
Khi chạy đoạn mã trên, bạn sẽ thấy lỗi:
```
UnboundLocalError: local variable 'x' referenced before assignment
```

### Ví dụ 2: Sửa lỗi bằng cách gán giá trị trước
```python
def tinh_tong():
    x = 10
    print(x)  # Biến x đã được gán trước khi sử dụng

tinh_tong()
```
Kết quả khi chạy đoạn mã này sẽ là:
```
10
```

### Ví dụ 3: Sử dụng từ khóa global
```python
x = 5

def tinh_tong():
    global x
    print(x)  # Biến x được truy cập từ không gian toàn cục
    x = 10

tinh_tong()
print(x)  # Kết quả là 10
```

## Giải thích
Một số vấn đề phổ biến liên quan đến UnboundLocalError bao gồm:

- **Thứ tự gán giá trị:** Đảm bảo rằng bạn gán giá trị cho biến địa phương trước khi sử dụng nó.
- **Sự nhầm lẫn giữa biến toàn cục và địa phương:** Khi bạn có cùng tên biến trong không gian toàn cục và địa phương, Python sẽ ưu tiên biến địa phương.
- **Sử dụng từ khóa global:** Nếu bạn cần sử dụng biến toàn cục trong hàm, hãy sử dụng từ khóa `global` để xác định rõ rằng bạn đang muốn truy cập biến toàn cục.

## Tóm tắt một dòng
UnboundLocalError trong Python là lỗi xảy ra khi cố gắng truy cập một biến địa phương chưa được gán giá trị trong hàm.