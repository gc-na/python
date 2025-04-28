<!--
Meta Description: # BaseExceptionGroup: Python 嘅基礎異常組合 ## Synopsis BaseExceptionGroup 係 Python 嘅一個新特性，主要用嚟處理多個異常情況，提供一個統一嘅異常處理機制。 ## Documentation BaseExceptionGroup 係 ...
Meta Keywords: baseexceptiongroup, error, python, caught, raise
-->

# BaseExceptionGroup: Python 嘅基礎異常組合

## Synopsis
BaseExceptionGroup 係 Python 嘅一個新特性，主要用嚟處理多個異常情況，提供一個統一嘅異常處理機制。

## Documentation
BaseExceptionGroup 係 Python 3.11 版本引入嘅一個重要特性，佢專門用來組合多個異常。透過 BaseExceptionGroup，開發者可以將多個異常包裝成一個異常組，方便一併處理。此特性特別適合處理異步程式中可能發生嘅多個異常情況。

### 目的
BaseExceptionGroup 嘅目的是簡化異常處理，特別係當一個操作可能引發多個異常時，開發者可以用一個異常組來捕捉。

### 使用方法
要使用 BaseExceptionGroup，開發者可以透過以下步驟進行：

1. 將多個異常包裝成一個 BaseExceptionGroup 物件。
2. 使用 `raise` 語句來引發這個異常組。
3. 在異常處理塊中捕捉這個 BaseExceptionGroup，通過迭代可以獲得其中每一個異常。

## Examples
以下係一個簡單嘅示例，展示如何使用 BaseExceptionGroup：

```python
class CustomErrorA(Exception):
    pass

class CustomErrorB(Exception):
    pass

try:
    raise BaseExceptionGroup("Multiple errors occurred", [
        CustomErrorA("This is error A"),
        CustomErrorB("This is error B"),
    ])
except BaseExceptionGroup as e:
    for error in e.exceptions:
        print(f"Caught an error: {error}")
```

### 輸出結果
```
Caught an error: This is error A
Caught an error: This is error B
```

## Explanation
使用 BaseExceptionGroup 時，有幾個常見嘅注意事項：

- **版本要求**：BaseExceptionGroup 只支援 Python 3.11 及以上版本。
- **異常類型**：可以包裝任何類型嘅異常，無論係內建異常定係自定義異常。
- **異常處理**：要確保異常處理邏輯能夠正確處理多個異常，避免漏掉某些異常。

## One Line Summary
BaseExceptionGroup 係 Python 用來處理多個異常嘅一個強大工具，令開發者可以更方便地管理錯誤。