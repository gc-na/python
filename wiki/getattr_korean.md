<!--
Meta Description: # Python의 getattr: 속성 접근을 위한 강력한 도구 ## 개요 `getattr`는 Python에서 객체의 속성에 동적으로 접근하기 위해 사용되는 내장 함수입니다. 이 함수는 특정 객체에서 지정된 속성을 가져오며, 속성이 존재하지 않을 경우 기본값을 설정할 ...
Meta Keywords: getattr, name, 속성이, 존재하지, person
-->

# Python의 getattr: 속성 접근을 위한 강력한 도구

## 개요
`getattr`는 Python에서 객체의 속성에 동적으로 접근하기 위해 사용되는 내장 함수입니다. 이 함수는 특정 객체에서 지정된 속성을 가져오며, 속성이 존재하지 않을 경우 기본값을 설정할 수 있는 기능을 제공합니다.

## 문서화

### 목적
`getattr`는 객체의 속성에 안전하게 접근할 수 있는 방법을 제공하며, 속성이 존재하지 않을 경우 `AttributeError`를 방지할 수 있습니다. 이는 동적 속성 접근이 필요한 경우에 유용합니다.

### 사용법
`getattr`의 기본 구문은 다음과 같습니다:

```python
getattr(object, name[, default])
```

- **object**: 속성에 접근할 객체.
- **name**: 문자열로 된 속성의 이름.
- **default**: 선택적 인수로, 속성이 존재하지 않을 경우 반환할 기본값.

### 세부사항
- `getattr`는 객체의 속성을 문자열로 지정해야 하며, 이는 변수명이나 다른 문자열 표현으로 동적으로 생성될 수 있습니다.
- `default` 인수를 지정하지 않으면, 속성이 존재하지 않을 때 `AttributeError`가 발생합니다.

## 예제

### 기본 사용법

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        return f"안녕하세요, 제 이름은 {self.name}입니다."

person = Person("홍길동")

# 이름 속성 접근
name = getattr(person, 'name')
print(name)  # 출력: 홍길동

# greet 메서드 호출
greeting = getattr(person, 'greet')()
print(greeting)  # 출력: 안녕하세요, 제 이름은 홍길동입니다.

# 존재하지 않는 속성 접근 (기본값 사용)
age = getattr(person, 'age', '나이를 알 수 없습니다.')
print(age)  # 출력: 나이를 알 수 없습니다.
```

## 설명
- `getattr`을 사용할 때, 속성 이름을 잘못 입력하면 `AttributeError`가 발생하므로, 항상 속성이 존재하는지 확인하는 것이 좋습니다.
- `default` 값을 설정하면, 속성이 존재하지 않을 경우 코드의 안정성을 높일 수 있습니다.
- 동적 속성 접근이 필요한 경우, `getattr`은 매우 유용하지만, 과도하게 사용하면 코드의 가독성이 떨어질 수 있습니다. 따라서 필요한 경우에만 사용하는 것이 좋습니다.

## 한 줄 요약
`getattr`는 Python 객체의 속성에 안전하게 접근할 수 있게 해주는 함수로, 속성이 존재하지 않을 경우 기본값을 반환할 수 있습니다.