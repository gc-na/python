<!--
Meta Description: # Python 中的 complex 数据类型 ## 概述 在 Python 中，`complex` 是一个内置数据类型，用于表示复数。复数是由一个实部和一个虚部构成的数字，通常表示为 a + bj，其中 a 是实部，b 是虚部，j 是虚数单位。 ## 文档 ### 目的 `complex` 类型...
Meta Keywords: complex, python, real, imag, abs
-->

# Python 中的 complex 数据类型

## 概述
在 Python 中，`complex` 是一个内置数据类型，用于表示复数。复数是由一个实部和一个虚部构成的数字，通常表示为 a + bj，其中 a 是实部，b 是虚部，j 是虚数单位。

## 文档
### 目的
`complex` 类型用于数学计算，特别是在涉及复数的应用中，如信号处理、控制系统和量子物理等领域。

### 用法
在 Python 中，可以通过几种方式创建复数：
1. 使用 `complex()` 函数。
2. 直接使用字面量形式 a + bj。

```python
# 使用 complex() 函数
z1 = complex(2, 3)  # 2 + 3j

# 使用字面量形式
z2 = 1 + 2j  # 1 + 2j
```

### 详细信息
- `complex` 类型支持基本的数学运算，如加法、减法、乘法和除法。
- 可以通过 `real` 和 `imag` 属性访问复数的实部和虚部。
- 使用 `abs()` 函数可以计算复数的模（绝对值）。

## 示例
```python
# 创建复数
z1 = complex(3, 4)  # 3 + 4j
z2 = 1 + 2j         # 1 + 2j

# 运算
z_sum = z1 + z2     # 4 + 6j
z_product = z1 * z2 # -5 + 10j

# 访问实部和虚部
real_part = z1.real  # 3.0
imag_part = z1.imag  # 4.0

# 计算绝对值
modulus = abs(z1)    # 5.0
```

## 说明
- **常见的陷阱**：在处理复数时，确保使用虚数单位 `j`，而不是 `i`，因为 `i` 不是 Python 中的有效虚数单位。
- **注意事项**：复数运算可能会导致理解上的混淆，特别是在涉及负数的平方根时。确保熟悉复数的基本性质。

## 一句话总结
`complex` 是 Python 中用于表示复数的内置数据类型，它支持基本的数学运算和属性访问。