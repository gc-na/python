<!--
Meta Description: # Python 中的 format 函數: 字串格式化的強大工具 ## 概述 `format` 是 Python 中一個用於字串格式化的函數，允許開發者以可讀的方式將變數嵌入到字串中。這種方法比傳統的字串拼接更為靈活和強大，並且支持多種格式設置。 ## 文檔 ### 目的 `format` 函數的...
Meta Keywords: format, python, print, name, 字串對齊
-->

# Python 中的 format 函數: 字串格式化的強大工具

## 概述
`format` 是 Python 中一個用於字串格式化的函數，允許開發者以可讀的方式將變數嵌入到字串中。這種方法比傳統的字串拼接更為靈活和強大，並且支持多種格式設置。

## 文檔
### 目的
`format` 函數的主要目的是提供一種方便的方式來格式化字串，從而使得字串的組合更加簡潔且可讀性更高。它可以用來控制數字的顯示格式、調整字串的對齊方式以及添加特定的填充字符等。

### 使用方法
`format` 函數的基本語法如下：

```python
str.format(*args, **kwargs)
```

- `*args`：位置參數，可以是任何類型的數據。
- `**kwargs`：關鍵字參數，允許使用鍵名來指定值。

### 詳細說明
使用 `format` 函數時，可以使用大括號 `{}` 作為佔位符，這些佔位符會被提供的參數替換。例如：

```python
name = "Alice"
age = 30
greeting = "你好，{}！你今年 {} 歲。".format(name, age)
print(greeting)  # 你好，Alice！你今年 30 歲。
```

此外，`format` 還支持更複雜的格式化需求，如數字格式化、字串對齊、填充等。例如：

```python
number = 3.14159
formatted_number = "圓周率約為 {:.2f}".format(number)
print(formatted_number)  # 圓周率約為 3.14
```

## 範例
### 基本範例
```python
# 簡單的字串格式化
name = "Bob"
print("嗨，{}！".format(name))  # 輸出: 嗨，Bob！
```

### 數字格式化
```python
# 數字格式化
price = 49.99
print("這件商品的價格是 ${:.2f}".format(price))  # 輸出: 這件商品的價格是 $49.99
```

### 多個參數
```python
# 使用多個參數
product = "蘋果"
quantity = 5
print("我買了 {} 個 {}".format(quantity, product))  # 輸出: 我買了 5 個 蘋果
```

### 字串對齊
```python
# 字串對齊
text = "Python"
print("{:<10} | {:>10}".format(text, "程式語言"))  # 輸出: Python    |      程式語言
```

## 解釋
使用 `format` 函數時，開發者需要注意以下幾點：
- 佔位符 `{}` 的數量必須與提供的參數數量匹配，否則會引發 `IndexError`。
- 在格式化數字時，必須使用相應的格式標識符（如 `:.2f`）來指定格式，否則可能導致意外結果。
- 確保使用的變數在使用 `format` 之前已經定義，否則將引發 `NameError`。

## 一行總結
`format` 函數是 Python 中一個靈活和強大的字串格式化工具，能夠輸出整齊且可讀的字串。