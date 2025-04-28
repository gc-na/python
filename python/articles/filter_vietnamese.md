<!--
Meta Description: # Hàm filter trong Python: Lọc Dữ Liệu Hiệu Quả ## Tóm tắt Hàm `filter` trong Python là một hàm tích hợp cho phép người dùng lọc các phần tử trong một...
Meta Keywords: hàm, một, filter, python, trong
-->

# Hàm filter trong Python: Lọc Dữ Liệu Hiệu Quả

## Tóm tắt
Hàm `filter` trong Python là một hàm tích hợp cho phép người dùng lọc các phần tử trong một iterable (danh sách, tuple, v.v.) dựa trên một điều kiện cho trước, trả về một iterator chứa các phần tử thỏa mãn điều kiện.

## Tài liệu
Hàm `filter` được sử dụng để lọc các phần tử trong một iterable. Cú pháp của hàm như sau:

```python
filter(function, iterable)
```

- **function**: Là một hàm trả về giá trị True hoặc False. Hàm này sẽ được áp dụng cho từng phần tử trong iterable.
- **iterable**: Là một đối tượng có thể lặp lại như danh sách, tuple, hoặc một iterator khác.

Hàm `filter` sẽ trả về một iterator chứa tất cả các phần tử trong iterable mà hàm `function` trả về True. Nếu `function` là `None`, thì hàm `filter` sẽ loại bỏ tất cả các phần tử có giá trị False (như 0, None, "", v.v.).

## Ví dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng hàm `filter`:

### Ví dụ 1: Lọc số chẵn từ danh sách
```python
def is_even(n):
    return n % 2 == 0

numbers = [1, 2, 3, 4, 5, 6]
even_numbers = filter(is_even, numbers)

print(list(even_numbers))  # Kết quả: [2, 4, 6]
```

### Ví dụ 2: Lọc các chuỗi không rỗng
```python
strings = ["Python", "", "Java", "C#", "", "JavaScript"]
non_empty_strings = filter(None, strings)

print(list(non_empty_strings))  # Kết quả: ['Python', 'Java', 'C#', 'JavaScript']
```

## Giải thích
Khi sử dụng hàm `filter`, có một số lưu ý cần chú ý:

- **Hàm phải trả về True hoặc False**: Đảm bảo rằng hàm bạn truyền vào trả về giá trị Boolean. Nếu không, kết quả có thể không như mong đợi.
- **Iterator**: Kết quả trả về từ hàm `filter` là một iterator. Để sử dụng được kết quả, bạn có thể chuyển đổi nó thành danh sách hoặc tuple.
- **Thay đổi hàm**: Bạn có thể sử dụng lambda để tạo hàm một cách ngắn gọn hơn. Ví dụ:
  ```python
  numbers = [1, 2, 3, 4, 5, 6]
  even_numbers = filter(lambda n: n % 2 == 0, numbers)
  ```

## Tóm tắt một dòng
Hàm `filter` trong Python cho phép lọc các phần tử trong một iterable dựa trên một điều kiện được xác định bởi một hàm.