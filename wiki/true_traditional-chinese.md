<!--
Meta Description: # Python中的“True”：布林值的基礎 ## 簡介 在Python編程語言中，“True”是布林型別的真值，代表邏輯上的真。它在條件判斷和邏輯運算中扮演著重要角色，是控制流程的關鍵。 ## 文檔 “True”是Python內建的布林值之一，與“False”相對應。這兩個值是Python的基本...
Meta Keywords: true, false, print, count, bool
-->

# Python中的“True”：布林值的基礎

## 簡介
在Python編程語言中，“True”是布林型別的真值，代表邏輯上的真。它在條件判斷和邏輯運算中扮演著重要角色，是控制流程的關鍵。

## 文檔
“True”是Python內建的布林值之一，與“False”相對應。這兩個值是Python的基本數據類型之一，屬於`bool`類型。具有以下特點：

- **類型**：`True`的類型是`bool`，可以通過`type(True)`來驗證。
- **使用場景**：`True`主要用於條件語句（如`if`和`while`），作為邏輯表達式的結果，幫助程序決定執行哪部分代碼。
- **自動轉換**：在需要布林值的上下文中，Python會自動將其他數據類型轉換為布林值，例如，非空字符串、非零數字和非空容器都會被視為`True`。

## 示例
以下是一些使用“True”的基本示例：

```python
# 使用在if語句中
if True:
    print("這段代碼會被執行。")

# 在while循環中
count = 0
while True:
    count += 1
    if count >= 5:
        break
print("計數結束。")

# 布林運算
is_active = True
if is_active:
    print("活動狀態為真。")
```

## 解釋
在使用“True”時，需要注意以下幾點：

1. **大小寫敏感**：Python中的布林值是大小寫敏感的，只有“True”被認可為真值，而“true”或“TRUE”會引發錯誤。
2. **邏輯運算**：在進行邏輯運算時，`True`和`False`可以與其他布林表達式結合使用，例如`and`、`or`和`not`。
3. **比較運算**：在比較運算中，任何非零數字和非空容器都可以被視為`True`，而零和空容器則被視為`False`。

## 一句總結
在Python中，“True”是用於表示邏輯真值的內建布林型別，對於控制程式的執行流程至關重要。