<!--
Meta Description: # Lỗi IndentationError trong Python: Nguyên Nhân và Cách Khắc Phục ## Tóm tắt Lỗi IndentationError là một trong những lỗi phổ biến trong Python, xảy r...
Meta Keywords: trong, lỗi, căn, không, indentationerror
-->

# Lỗi IndentationError trong Python: Nguyên Nhân và Cách Khắc Phục

## Tóm tắt
Lỗi IndentationError là một trong những lỗi phổ biến trong Python, xảy ra khi trình biên dịch gặp phải vấn đề về căn lề (indentation) trong mã nguồn.

## Tài liệu
### Mục đích
Lỗi IndentationError xuất hiện khi có sự không nhất quán trong việc sử dụng khoảng trắng hoặc tab để căn lề. Python yêu cầu mã nguồn phải được căn lề đúng cách để xác định cấu trúc của mã, chẳng hạn như các khối lệnh trong vòng lặp hoặc hàm.

### Cách sử dụng
Lỗi IndentationError thường xảy ra trong các tình huống sau:
- Không có khoảng trắng hoặc tab ở đầu dòng.
- Sử dụng cả tab và khoảng trắng trong cùng một khối mã.
- Số lượng khoảng trắng không đồng nhất giữa các dòng trong cùng một khối.

## Ví dụ
Dưới đây là một số ví dụ minh họa về IndentationError:

### Ví dụ 1: Quên căn lề

```python
def my_function():
print("Hello, World!")  # Lỗi IndentationError
```

### Ví dụ 2: Sử dụng cả tab và khoảng trắng

```python
def another_function():
    print("This is a tab")  # Sử dụng khoảng trắng
	print("This is a tab")  # Sử dụng tab, gây lỗi
```

### Ví dụ 3: Căn lề không nhất quán

```python
for i in range(5):
    print(i)
     print("Number")  # Lỗi IndentationError
```

## Giải thích
Các vấn đề thường gặp với IndentationError bao gồm:
- **Không nhất quán**: Sử dụng cả tab và khoảng trắng có thể dẫn đến lỗi khó phát hiện, vì Python không đồng bộ hóa các ký tự này.
- **Căn lề sai**: Bất kỳ dòng nào không phù hợp với cấu trúc căn lề của các dòng khác trong cùng một khối đều sẽ gây ra lỗi.
- **Thiếu căn lề**: Nếu bạn quên không căn lề cho một dòng lệnh trong hàm hoặc vòng lặp, điều đó cũng sẽ gây ra lỗi.

Để khắc phục lỗi này, hãy đảm bảo rằng bạn chỉ sử dụng một loại ký tự căn lề (hoặc tab hoặc khoảng trắng) trong toàn bộ mã nguồn và kiểm tra kỹ lưỡng các khối mã.

## Tóm tắt một câu
Lỗi IndentationError trong Python xảy ra khi mã nguồn không được căn lề đúng cách, dẫn đến sự không đồng nhất trong cấu trúc của mã.