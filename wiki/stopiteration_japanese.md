<!--
Meta Description: # Pythonの「StopIteration」：イテレーションの制御 ## 概要 Pythonにおける「StopIteration」は、イテレーターが全ての要素を返した後に発生する特別な例外です。この例外は、イテレーションの終了を示すために使用されます。主に、forループや他のイテレーション機構に...
Meta Keywords: self, stopiteration, current, def, __next__
-->

# Pythonの「StopIteration」：イテレーションの制御

## 概要
Pythonにおける「StopIteration」は、イテレーターが全ての要素を返した後に発生する特別な例外です。この例外は、イテレーションの終了を示すために使用されます。主に、forループや他のイテレーション機構において重要な役割を果たします。

## ドキュメント
### 目的
「StopIteration」は、イテレーターがもはや返すべき要素を持たないことを示すための例外です。この例外が発生すると、イテレーションは自動的に終了します。

### 使用法
Pythonのイテレーターを使用する際に、要素が尽きたことを示すために「StopIteration」を発生させます。これにより、for文などのイテレーション構文が正常に終了します。

### 詳細
イテレーターを作成する際、`__next__()`メソッドが要素を返すことができない場合、`StopIteration`を発生させる必要があります。以下は、イテレーターにおける基本的な構造です。

```python
class MyIterator:
    def __init__(self, max):
        self.max = max
        self.current = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.current < self.max:
            self.current += 1
            return self.current
        else:
            raise StopIteration
```

## 例
以下に「StopIteration」の基本的な使用例を示します。

```python
# 自作のイテレーターを利用する
class Counter:
    def __init__(self, low, high):
        self.current = low
        self.high = high

    def __iter__(self):
        return self

    def __next__(self):
        if self.current < self.high:
            self.current += 1
            return self.current - 1
        else:
            raise StopIteration

# カウンターを使ったイテレーション
for num in Counter(1, 4):
    print(num)
```

この例では、`Counter`クラスがイテレーターとして機能し、`StopIteration`がイテレーションの終わりを示します。

## 説明
「StopIteration」を正しく扱わないと、無限ループが発生したり、予期しないエラーが発生する可能性があります。以下の点に留意してください：

1. **例外を捕捉**: `StopIteration`は通常、forループなどのイテレーション構文内で自動的に処理されますが、手動で`__next__()`を呼び出す場合は、例外処理を適切に行う必要があります。
   
2. **カスタムイテレーターの設計**: 自作のイテレーターを設計する際は、`StopIteration`を正しく発生させることが重要です。これを怠ると、イテレーションが終了しない場合があります。

## 一文の要約
Pythonにおける「StopIteration」は、イテレーターが全ての要素を返した後に発生する例外であり、イテレーションの終了を示します。