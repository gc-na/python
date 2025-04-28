<!--
Meta Description: # Python에서 ASCII 사용법: 문자열 인코딩과 디코딩의 이해 ## 개요 Python에서 ASCII는 문자열을 인코딩하고 디코딩하는 데 중요한 역할을 합니다. ASCII(미국 표준 문자 집합)는 128개의 문자에 대한 표준화된 인코딩 방식으로, 컴퓨터와 다른 장...
Meta Keywords: ascii, 문자열을, hello, world, ascii는
-->

# Python에서 ASCII 사용법: 문자열 인코딩과 디코딩의 이해

## 개요
Python에서 ASCII는 문자열을 인코딩하고 디코딩하는 데 중요한 역할을 합니다. ASCII(미국 표준 문자 집합)는 128개의 문자에 대한 표준화된 인코딩 방식으로, 컴퓨터와 다른 장치 간의 데이터 전송에서 기본적으로 사용됩니다.

## 문서
ASCII는 American Standard Code for Information Interchange의 약자로, 텍스트 데이터의 디지털 표현을 위해 사용됩니다. Python에서는 `str` 객체와 `bytes` 객체 간의 변환을 통해 ASCII 인코딩과 디코딩을 쉽게 수행할 수 있습니다.

### 목적
- 문자열을 ASCII 형식으로 인코딩하기
- ASCII 형식의 데이터를 문자열로 디코딩하기

### 사용법
Python에서 ASCII 인코딩과 디코딩은 `encode()` 및 `decode()` 메소드를 사용하여 처리할 수 있습니다.

#### 인코딩
- 문자열을 ASCII로 인코딩하려면 `encode()` 메소드를 사용합니다.
```python
ascii_encoded = "Hello, World!".encode('ascii')
```

#### 디코딩
- ASCII 바이트 데이터를 문자열로 변환하려면 `decode()` 메소드를 사용합니다.
```python
ascii_decoded = b'Hello, World!'.decode('ascii')
```

### 세부사항
- ASCII는 0부터 127까지의 정수 값으로 각 문자에 매핑됩니다.
- 비ASCII 문자가 포함된 문자열을 ASCII로 인코딩하려고 하면 `UnicodeEncodeError`가 발생합니다.
- 반대로, ASCII 바이트 스트림을 디코딩할 때도 비ASCII 문자가 포함되어 있으면 `UnicodeDecodeError`가 발생할 수 있습니다.

## 예제
### ASCII 인코딩 예제
```python
# 문자열을 ASCII로 인코딩
text = "Hello, World!"
encoded_text = text.encode('ascii')
print(encoded_text)  # Output: b'Hello, World!'
```

### ASCII 디코딩 예제
```python
# ASCII 바이트를 문자열로 디코딩
encoded_text = b'Hello, World!'
decoded_text = encoded_text.decode('ascii')
print(decoded_text)  # Output: Hello, World!
```

## 설명
- ASCII는 영어 알파벳, 숫자, 기본 구두점 및 제어 문자를 포함하여 128개의 문자만 지원하므로, 다른 언어의 문자를 포함하는 문자열은 인코딩할 수 없습니다.
- 예를 들어, "Café"와 같은 문자열을 ASCII로 인코딩하려고 하면 오류가 발생합니다.
- `errors` 매개변수를 사용하여 오류 처리를 세밀하게 조정할 수 있습니다. 예를 들어, `errors='ignore'`를 사용하면 인코딩할 수 없는 문자를 무시할 수 있습니다.

## 한 줄 요약
Python에서 ASCII는 문자열을 인코딩하고 디코딩하는 데 사용되는 기본적인 문자 인코딩 방식입니다.