<!--
Meta Description: # PythonにおけるRecursionError（再帰エラー）について ## 概要 Pythonの`RecursionError`は、再帰関数が最大再帰深度を超えた場合に発生するエラーです。再帰を用いるプログラムで無限再帰や深すぎる再帰が起こると、プログラムが停止し、エラーが発生します。 ## ...
Meta Keywords: recursionerror, print, sys, countdown, python
-->

# PythonにおけるRecursionError（再帰エラー）について

## 概要
Pythonの`RecursionError`は、再帰関数が最大再帰深度を超えた場合に発生するエラーです。再帰を用いるプログラムで無限再帰や深すぎる再帰が起こると、プログラムが停止し、エラーが発生します。

## ドキュメンテーション
`RecursionError`は、Pythonの組み込み例外の一つで、再帰呼び出しが制限を超えた際に発生します。Pythonにはデフォルトで最大再帰深度が設定されており、通常は1000回です。この制限は、無限再帰やスタックオーバーフローを防ぐために設けられています。

### 使用方法
`RecursionError`は、特に再帰関数を実装する際に注意が必要です。再帰呼び出しが適切に終了しない場合、次のようにエラーが発生します。

```python
def factorial(n):
    return n * factorial(n - 1)

print(factorial(5))  # これはRecursionErrorを引き起こします
```

### 詳細
- **最大再帰深度の確認**: `sys`モジュールを使用して、現在の最大再帰深度を確認することができます。
  
  ```python
  import sys
  print(sys.getrecursionlimit())  # 現在の再帰深度を表示
  ```

- **再帰深度の設定**: `sys.setrecursionlimit(limit)`を使うことで、最大再帰深度の設定を変更可能ですが、過度に大きく設定すると、スタックオーバーフローの原因となるため注意が必要です。

## 例
以下は、簡単な再帰関数の例で、`RecursionError`が発生する状況を示しています。

```python
def countdown(n):
    if n <= 0:
        print("終了！")
    else:
        print(n)
        countdown(n - 1)

countdown(5)  # 正常に動作します
countdown(10000)  # 深すぎる再帰でRecursionErrorを引き起こす可能性があります
```

## 説明
`RecursionError`は、再帰関数が適切に基底条件を持たない場合や、誤った条件で呼び出される場合に一般的に発生します。これにより、無限ループに陥り、プログラムがクラッシュする原因となります。また、スタックの使用量が増えることでパフォーマンスにも影響を与えるため、再帰の使用には慎重さが求められます。

### 一般的な落とし穴
- **基底条件の不備**: 再帰関数には必ず基底条件を設定し、適切に終了するようにすることが重要です。
- **過剰な再帰深度**: デフォルトの再帰深度を超えないように、必要に応じて反復処理に切り替えることを検討してください。

## 一文要約
Pythonにおける`RecursionError`は、再帰関数が最大再帰深度を超えた際に発生するエラーです。