<!--
Meta Description: # GeneratorExit：Python 中生成器的退出异常 ## 概述 `GeneratorExit` 是 Python 中的一个内置异常，它用于指示生成器被关闭。当生成器对象的 `close()` 方法被调用时，会引发此异常，以便生成器能够进行清理操作。 ## 文档 ### 目的 `Gene...
Meta Keywords: generatorexit, python, print, gen, close
-->

# GeneratorExit：Python 中生成器的退出异常

## 概述
`GeneratorExit` 是 Python 中的一个内置异常，它用于指示生成器被关闭。当生成器对象的 `close()` 方法被调用时，会引发此异常，以便生成器能够进行清理操作。

## 文档
### 目的
`GeneratorExit` 异常的主要目的是在生成器被关闭时通知生成器进行必要的清理。它是 Python 中生成器机制的一部分，确保生成器能够正确管理其资源。

### 用法
当生成器对象调用 `close()` 方法时，`GeneratorExit` 异常会被引发。开发者可以在生成器内部捕获此异常，以便执行清理代码。例如，释放资源或保存状态等。

### 详细信息
- `GeneratorExit` 是 `BaseException` 的子类，通常不应直接捕获。
- 捕获 `GeneratorExit` 异常的生成器可以执行一些清理代码，但如果生成器引发其他异常，`GeneratorExit` 将不会被处理。
- 在使用 `with` 语句和上下文管理器时，生成器的退出行为与 `GeneratorExit` 异常密切相关。

## 示例
以下是一个简单的生成器示例，展示了如何处理 `GeneratorExit` 异常：

```python
def my_generator():
    try:
        yield 1
        yield 2
    except GeneratorExit:
        print("生成器被关闭，执行清理操作")
    finally:
        print("执行最终清理")

gen = my_generator()
print(next(gen))  # 输出 1
print(next(gen))  # 输出 2
gen.close()       # 输出 "生成器被关闭，执行清理操作" 和 "执行最终清理"
```

## 解释
- 开发者需要注意，当生成器被关闭时，`GeneratorExit` 异常会被引发。如果在生成器中没有处理此异常，生成器将会终止。
- 不要将 `GeneratorExit` 与其他异常混淆，它是专门用于生成器的退出通知。
- 在生成器的 `try` 块中处理 `GeneratorExit` 可以确保清理代码的执行，但不应在其他上下文中捕获它。

## 一句话总结
`GeneratorExit` 是用于在 Python 生成器关闭时通知其进行清理的异常。