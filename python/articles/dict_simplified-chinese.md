<!--
Meta Description: # Python dict：字典类型的全面指南 ## 概述 在Python中，`dict`（字典）是一种可变的、无序的数据结构，用于存储键值对。字典允许通过键来快速访问对应的值，是处理关联数据的强大工具。 ## 文档 ### 目的 `dict`类型用于存储具有唯一键的键值对，使得可以根据键快速查找、...
Meta Keywords: my_dict, student, name, age, dict
-->

# Python dict：字典类型的全面指南

## 概述
在Python中，`dict`（字典）是一种可变的、无序的数据结构，用于存储键值对。字典允许通过键来快速访问对应的值，是处理关联数据的强大工具。

## 文档
### 目的
`dict`类型用于存储具有唯一键的键值对，使得可以根据键快速查找、插入和删除对应的值。它广泛应用于数据存储、配置管理和数据处理等场景。

### 使用
在Python中，字典是通过花括号 `{}` 创建的，键值对用冒号 `:` 分隔，多个键值对用逗号 `,` 分隔。例如：

```python
my_dict = {
    'name': 'Alice',
    'age': 30,
    'city': 'Beijing'
}
```

可以使用以下方法操作字典：

- **访问值**: 通过键访问值，例如 `my_dict['name']` 返回 `'Alice'`。
- **添加或更新值**: 直接赋值，例如 `my_dict['age'] = 31`。
- **删除键值对**: 使用 `del` 语句，例如 `del my_dict['city']`。
- **获取所有键或值**: 使用 `my_dict.keys()` 获取所有键，使用 `my_dict.values()` 获取所有值。

### 详细信息
- 字典的键必须是不可变类型，如字符串、数字或元组，而值可以是任意类型。
- 字典是无序的（在Python 3.7及以后的版本中保持插入顺序，但不保证）。
- 字典的查找时间复杂度为O(1)，因此在需要频繁查找的场景中表现优越。

## 示例
```python
# 创建字典
student = {
    'name': 'Bob',
    'age': 25,
    'major': 'Computer Science'
}

# 访问字典
print(student['name'])  # 输出: Bob

# 更新字典
student['age'] = 26

# 添加新键值对
student['graduation_year'] = 2023

# 删除键值对
del student['major']

# 获取所有键
print(student.keys())  # 输出: dict_keys(['name', 'age', 'graduation_year'])
```

## 说明
- 常见的坑：试图使用可变类型（如列表）作为字典的键会导致 `TypeError`。
- 字典的复制：使用 `my_dict.copy()` 方法进行浅拷贝，使用 `copy.deepcopy(my_dict)` 进行深拷贝。
- 字典推导式：可以使用字典推导式快速创建字典，例如 `{x: x**2 for x in range(5)}` 生成 `{0: 0, 1: 1, 2: 4, 3: 9, 4: 16}`。

## 一句话总结
Python中的`dict`是一种高效的无序键值对数据结构，适合用于快速存储和检索相关数据。