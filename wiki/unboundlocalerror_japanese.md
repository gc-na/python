<!--
Meta Description: # UnboundLocalError: Pythonにおけるローカル変数のエラー ## 概要 UnboundLocalErrorは、Pythonプログラミングにおいて、ローカル変数が参照される前に初期化されていない場合に発生するエラーです。このエラーは、変数のスコープに関連する問題を示しています。...
Meta Keywords: counter, unboundlocalerrorは, increment_counter, python, unboundlocalerror
-->

# UnboundLocalError: Pythonにおけるローカル変数のエラー

## 概要
UnboundLocalErrorは、Pythonプログラミングにおいて、ローカル変数が参照される前に初期化されていない場合に発生するエラーです。このエラーは、変数のスコープに関連する問題を示しています。

## ドキュメンテーション
UnboundLocalErrorは、関数内でローカル変数を使用する際に、変数が初期化されていない、またはローカルスコープで定義されていない場合に発生します。Pythonは、関数内で変数が初めて出現した際、その変数をローカル変数として扱います。そのため、外部のスコープに同名の変数が存在しても、ローカルスコープ内で初期化されていない場合は、UnboundLocalErrorが発生します。

### 使用法
UnboundLocalErrorは通常、次のような状況で発生します：
- 関数内でローカル変数を定義せずにその変数を参照する場合。
- グローバル変数を意図的に変更する際に、同名のローカル変数を定義しない場合。

### 詳細
- エラーメッセージには「local variable '変数名' referenced before assignment」と表示され、どの変数が問題であるかを示します。
- このエラーは、Python 2.xおよび3.xの両方で発生しますが、処理の詳細はバージョンによって異なることがあります。

## 例
以下にUnboundLocalErrorの発生する簡単な例を示します。

```python
def increment_counter():
    counter += 1  # UnboundLocalErrorが発生
    return counter

counter = 0
print(increment_counter())
```

上記のコードを実行すると、`UnboundLocalError: local variable 'counter' referenced before assignment`というエラーが発生します。

このエラーを解決するためには、次のようにローカル変数を初期化するか、`global`キーワードを使用してグローバル変数を参照します。

```python
def increment_counter():
    global counter
    counter += 1
    return counter

counter = 0
print(increment_counter())
```

## 説明
UnboundLocalErrorは、変数のスコープに関する一般的な誤解から生じることが多いです。特に、以下の点に注意が必要です。

- **初期化の欠如**: ローカルスコープで変数を初期化しないと、参照時にエラーが発生します。
- **グローバル変数との混同**: 同名のグローバル変数が存在する場合でも、ローカルスコープ内で新たに定義しないと、Pythonはそれをローカル変数として扱います。
- **デバッグの難しさ**: 大規模なコードベースでは、どのスコープで変数が定義されているかを把握するのが難しく、エラーが発生することがあります。

## 一文要約
UnboundLocalErrorは、Pythonにおいてローカル変数が初期化されていない場合に発生するエラーです。