<!--
Meta Description: # Python의 NotImplemented: 기능과 활용 ## 개요 `NotImplemented`는 Python에서 특정 메소드 또는 연산이 구현되지 않았음을 나타내는 특별한 상수입니다. 주로 사용자 정의 클래스에서 연산자 오버로딩 시 사용됩니다. ## 문서화 `No...
Meta Keywords: notimplemented, myclass, value, 클래스에서, 연산자
-->

# Python의 NotImplemented: 기능과 활용

## 개요
`NotImplemented`는 Python에서 특정 메소드 또는 연산이 구현되지 않았음을 나타내는 특별한 상수입니다. 주로 사용자 정의 클래스에서 연산자 오버로딩 시 사용됩니다.

## 문서화
`NotImplemented`는 Python의 내장 상수로, 주로 메소드가 특정 연산을 지원하지 않을 때 반환됩니다. 이 상수는 다른 클래스의 연산자 메소드가 호출되었으나 현재 클래스에서는 해당 작업을 수행할 수 없음을 나타냅니다. 예를 들어, 클래스에서 덧셈(`__add__`) 연산을 정의하지 않았을 때, 이 메소드는 `NotImplemented`를 반환하여 Python이 다른 클래스의 덧셈 메소드를 시도하도록 유도할 수 있습니다.

### 사용 목적
- 사용자 정의 클래스에서 연산자 오버로딩을 지원하지 않을 때 명확한 의도를 전달.
- 다른 객체와의 상호작용을 위한 메소드 구현을 유도.

### 사용 방법
`NotImplemented`는 다음과 같이 사용할 수 있습니다:
```python
class MyClass:
    def __add__(self, other):
        if not isinstance(other, MyClass):
            return NotImplemented
        return MyClass()
```

## 예제
### 기본 사용 예제
```python
class MyClass:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        if not isinstance(other, MyClass):
            return NotImplemented
        return MyClass(self.value + other.value)

a = MyClass(5)
b = MyClass(10)

result = a + b  # MyClass(15)
print(result.value)  # 출력: 15

result = a + 3  # NotImplemented 반환
print(result)  # 출력: NotImplemented
```

## 설명
`NotImplemented`를 사용하면 연산이 지원되지 않는 경우를 명확히 처리할 수 있습니다. 이를 통해 Python의 기본 연산자 오버로딩 메커니즘이 작동하여 다른 클래스의 메소드를 호출하게 할 수 있습니다. 

### 일반적인 함정
- `NotImplemented`를 반환하지 않으면 TypeError가 발생할 수 있습니다. 따라서 적절한 타입 검사를 수행하는 것이 중요합니다.
- 사용자 정의 클래스에서 모든 연산을 구현할 필요는 없지만, 지원하지 않는 연산에 대해 `NotImplemented`를 반환하는 것이 모범 사례입니다.

## 한 줄 요약
`NotImplemented`는 Python에서 특정 연산이 구현되지 않았음을 나타내는 특별한 상수로, 사용자 정의 클래스에서 연산자 오버로딩을 지원하는 데 유용합니다.