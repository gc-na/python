<!--
Meta Description: # Python의 bool: 불린 자료형에 대한 완벽 가이드 ## 개요 Python의 `bool`은 참(True)과 거짓(False) 두 가지 값을 가지는 불린 자료형입니다. 이 자료형은 조건문, 논리 연산, 반복문 등 다양한 상황에서 사용되어, 프로그램의 흐름을 제어...
Meta Keywords: bool, false, true, print, 자료형은
-->

# Python의 bool: 불린 자료형에 대한 완벽 가이드

## 개요
Python의 `bool`은 참(True)과 거짓(False) 두 가지 값을 가지는 불린 자료형입니다. 이 자료형은 조건문, 논리 연산, 반복문 등 다양한 상황에서 사용되어, 프로그램의 흐름을 제어하는 데 필수적인 역할을 합니다.

## 문서화

### 목적
`bool` 자료형은 참(True)과 거짓(False)을 표시하는 데 사용됩니다. 이 자료형은 조건적 표현식, 논리 연산자, 그리고 다양한 데이터 비교 작업에 사용됩니다.

### 사용법
Python에서 `bool`은 다음과 같이 사용할 수 있습니다:
- `True`와 `False`는 `bool` 타입의 두 가지 인스턴스입니다.
- `bool()` 함수를 사용하여 다른 자료형을 불린으로 변환할 수 있습니다.

### 세부사항
- `bool`은 기본적으로 0은 `False`로, 0이 아닌 모든 수는 `True`로 평가됩니다.
- 빈 컬렉션(리스트, 튜플, 딕셔너리 등)은 `False`로, 비어 있지 않은 컬렉션은 `True`로 평가됩니다.
- `not`, `and`, `or`와 같은 논리 연산자를 통해 불린 값을 조합할 수 있습니다.

## 예제

### 기본 사용법
```python
# bool 값의 생성
a = True
b = False

# bool() 함수 사용
print(bool(0))          # False
print(bool(3.14))      # True
print(bool(""))        # False
print(bool("Hello"))   # True

# 논리 연산자 사용
print(a and b)         # False
print(a or b)          # True
print(not a)           # False
```

### 조건문에서의 사용
```python
x = 10
if x > 5:
    print("x는 5보다 큽니다.")  # 출력: x는 5보다 큽니다.
else:
    print("x는 5보다 작거나 같습니다.")
```

## 설명
- **빈 값 평가**: 리스트나 문자열이 비어 있을 경우 `False`로 평가되므로, 이러한 경우를 체크할 때 주의해야 합니다.
- **불린 연산자**: `and`와 `or`의 논리적 결합을 이해하는 것이 중요합니다. 예를 들어, `True and False`는 `False`로 평가됩니다.
- **타입 일관성**: 다른 데이터 타입과의 비교 시, `bool`의 평가 방식에 따라 예상치 못한 결과가 발생할 수 있으므로 주의해야 합니다.

## 한 줄 요약
Python의 `bool` 자료형은 참과 거짓을 나타내며, 조건문과 논리 연산에서 필수적으로 사용됩니다.