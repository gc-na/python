<!--
Meta Description: # Pythonの「NotImplemented」：使い方と注意点 ## 概要 Pythonの「NotImplemented」は、メソッドがまだ実装されていないことを示す特別な値です。この値は、特にオーバーライドされるべきメソッドで一般的に使用されます。 ## ドキュメンテーション ### 目的 「...
Meta Keywords: notimplemented, self, shape, side, def
-->

# Pythonの「NotImplemented」：使い方と注意点

## 概要
Pythonの「NotImplemented」は、メソッドがまだ実装されていないことを示す特別な値です。この値は、特にオーバーライドされるべきメソッドで一般的に使用されます。

## ドキュメンテーション
### 目的
「NotImplemented」は、特定のメソッドが現在のクラスまたはインスタンスで未実装であることを明示的に示すために利用されます。これにより、オーバーライドが期待されるメソッドであることを示すことができます。

### 使用法
通常、抽象基底クラス（ABC）やインターフェース的な役割を持つクラスで使用されます。以下のように、メソッドが未実装であることを示すために「NotImplemented」を返すことができます。

```python
class MyBaseClass:
    def my_method(self):
        return NotImplemented
```

### 詳細
- **戻り値**: `NotImplemented`は単なるシンボルであり、通常は`None`とは異なります。
- **エラーハンドリング**: `NotImplemented`が返された場合、Pythonでは型の互換性を確認するために、他のメソッドが呼び出されることがあります。

## 例
以下に「NotImplemented」の基本的な使用例を示します。

```python
class Shape:
    def area(self):
        return NotImplemented

class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side * self.side

# 使用例
shapes = [Square(4), Shape()]
for shape in shapes:
    result = shape.area()
    if result is NotImplemented:
        print("この形の面積は未実装です。")
    else:
        print(f"面積: {result}")
```

## 説明
### 一般的な落とし穴
- **誤解**: `NotImplemented`は`None`や`False`とは異なる意味を持つので、注意が必要です。条件文での比較では予期せぬ動作を引き起こす可能性があります。
- **オーバーライドの必要性**: `NotImplemented`が返された場合、そのメソッドを呼び出した側は他の実装を試みることが期待されるため、適切なオーバーライドが必要です。

## 一文要約
Pythonの「NotImplemented」は、未実装のメソッドを示すために使用される特別な値です。