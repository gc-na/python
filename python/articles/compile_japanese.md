<!--
Meta Description: # Pythonの「compile」関数：コンパイル機能の完全ガイド ## 概要 Pythonの`compile`関数は、ソースコードをバイトコードにコンパイルするための組み込み関数です。この関数は、文字列やAST（抽象構文木）をPythonのバイトコードに変換し、実行可能な形にします。 ## ドキ...
Meta Keywords: compile, exec, eval, 関数は, code
-->

# Pythonの「compile」関数：コンパイル機能の完全ガイド

## 概要
Pythonの`compile`関数は、ソースコードをバイトコードにコンパイルするための組み込み関数です。この関数は、文字列やAST（抽象構文木）をPythonのバイトコードに変換し、実行可能な形にします。

## ドキュメント
### 目的
`compile`関数は、Pythonのソースコードをバイトコードに変換することで、コードの実行を迅速化し、モジュールやスクリプトの動的な生成を可能にします。これにより、実行時にコードを評価したり、動的に生成したコードを実行したりすることができます。

### 使用法
`compile`関数の基本的な構文は次の通りです：

```python
compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)
```

- **source**: コンパイルするソースコード（文字列またはASTノード）。
- **filename**: エラーメッセージに表示されるファイル名（通常は`'<string>'`や実際のファイル名）。
- **mode**: コンパイルモード。'exec'（複数の文）、'eval'（単一の式）、'single'（単一の文）から選択します。
- **flags**: コンパイラのフラグ（オプション）。
- **dont_inherit**: `True`に設定すると、親のフラグを継承しません。
- **optimize**: 最適化レベル（-1はデフォルト）。

### 詳細
`compile`を使用することで、Pythonスクリプトをプログラム的に生成したり、実行時に評価したりすることが可能です。たとえば、`eval`関数や`exec`関数と組み合わせて使用されることが多く、柔軟なコード実行が実現します。

## 例
### 基本的な使用例
```python
# 単一の式をコンパイル
code = "2 + 2"
compiled_code = compile(code, '<string>', 'eval')
result = eval(compiled_code)
print(result)  # 出力: 4

# 複数の文をコンパイル
code = """
def greet(name):
    return f'Hello, {name}'

greet('World')
"""
compiled_code = compile(code, '<string>', 'exec')
exec(compiled_code)  # 出力: Hello, World
```

## 説明
- **コンパイルエラー**: ソースコードに構文エラーがある場合、`compile`関数は`SyntaxError`を投げます。エラーメッセージを確認し、問題を修正する必要があります。
- **バイトコードの使用**: `compile`関数で生成されたバイトコードは、実行時に`exec`や`eval`関数を使って実行できます。
- **モードの選択**: モードの選択は重要です。たとえば、複数の文をコンパイルする場合は`exec`モードを使用し、単一の式を評価する場合は`eval`モードを使用します。

## 一文要約
Pythonの`compile`関数は、文字列やASTをバイトコードに変換し、動的なコード実行を可能にする強力なツールです。