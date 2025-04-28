<!--
Meta Description: # PythonにおけるFileNotFoundError（ファイルが見つかりませんエラー） ## 概要 `FileNotFoundError`は、Pythonでファイルを操作する際に、指定したファイルが見つからない場合に発生する例外です。このエラーは、ファイルの読み込みや書き込みを試みた際に、対象...
Meta Keywords: filenotfounderror, file, txt, open, python
-->

# PythonにおけるFileNotFoundError（ファイルが見つかりませんエラー）

## 概要
`FileNotFoundError`は、Pythonでファイルを操作する際に、指定したファイルが見つからない場合に発生する例外です。このエラーは、ファイルの読み込みや書き込みを試みた際に、対象のファイルが存在しないことを示します。

## ドキュメンテーション
`FileNotFoundError`は、Pythonの組み込み例外の一つで、主にファイル操作に関連しています。このエラーは、以下の状況で発生します。

- 指定したファイルパスが間違っている場合（例：タイプミス、誤ったディレクトリの指定など）。
- ファイルが削除されたり移動されたために、指定したパスに存在しない場合。
- アクセス権限が不足している場合も、特定のOS環境において`FileNotFoundError`を引き起こすことがあります。

### 使い方
`FileNotFoundError`は通常、ファイルを開く際に`open()`関数を使用することで発生します。Python 3.3以降は、ファイルにアクセスできなかった場合にこのエラーが発生します。

例：
```python
file_path = 'example.txt'
with open(file_path, 'r') as file:
    content = file.read()
```

上記のコードで、`example.txt`というファイルが存在しない場合、以下のようなエラーが発生します。
```
FileNotFoundError: [Errno 2] No such file or directory: 'example.txt'
```

## 例
以下に、`FileNotFoundError`を引き起こす基本的な使用例を示します。

### 例1: 存在しないファイルを開く
```python
try:
    with open('non_existent_file.txt', 'r') as file:
        data = file.read()
except FileNotFoundError as e:
    print(f"エラー: {e}")
```

### 例2: 存在しないディレクトリ内のファイルを開く
```python
try:
    with open('/path/to/non_existent_directory/file.txt', 'r') as file:
        data = file.read()
except FileNotFoundError as e:
    print(f"エラー: {e}")
```

## 説明
`FileNotFoundError`は、特に以下の点に注意が必要です：

- **パスの正確性**: ファイルパスが正しいかを確認することが重要です。相対パスと絶対パスの違いを理解し、必要に応じて修正します。
- **ファイルの存在確認**: ファイルが存在するかを事前に確認するために、`os.path.exists()`関数を使用すると良いでしょう。
- **環境依存性**: OSによっては、ファイル名の大文字小文字が区別されるため、特にLinuxやmacOS環境では注意が必要です。
- **エラーハンドリング**: `try-except`ブロックを使用してエラーハンドリングを行うことで、プログラムのクラッシュを防止できます。

## 一文要約
`FileNotFoundError`は、指定したファイルが存在しない場合に発生するPythonの組み込み例外です。