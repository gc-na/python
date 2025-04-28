<!--
Meta Description: # Python frozenset: 불변 집합의 모든 것 ## 개요 Python의 `frozenset`는 변경할 수 없는(immutable) 집합을 생성하는 내장 데이터 타입입니다. 이 기능은 집합의 요소를 변경할 수 없도록 하여, 해시 가능한 객체로 사용할 수 있게 ...
Meta Keywords: frozenset, 변경할, 가능한, 집합의, fset1
-->

# Python frozenset: 불변 집합의 모든 것

## 개요
Python의 `frozenset`는 변경할 수 없는(immutable) 집합을 생성하는 내장 데이터 타입입니다. 이 기능은 집합의 요소를 변경할 수 없도록 하여, 해시 가능한 객체로 사용할 수 있게 합니다.

## 문서화
`frozenset`는 Python의 기본 집합 자료형인 `set`의 불변 버전입니다. `frozenset`는 집합의 모든 특성을 가지면서, 요소를 추가하거나 제거할 수 없는 특징이 있습니다. 이로 인해 `frozenset`은 다른 데이터 구조의 키로 사용하거나, 집합 연산을 수행할 수 있는 안전한 방법을 제공합니다.

### 사용법
`frozenset`는 다음과 같은 방식으로 생성할 수 있습니다:

```python
fset = frozenset([1, 2, 3, 4])
```

여기서 `frozenset`은 리스트, 튜플, 또는 다른 반복 가능한(iterable) 객체를 인자로 받을 수 있습니다. 

### 주요 특징
- **불변성**: `frozenset`의 요소는 생성 후 변경할 수 없습니다.
- **해시 가능성**: 이는 `frozenset`이 해시 테이블의 키로 사용될 수 있음을 의미합니다.
- **집합 연산**: `frozenset`은 집합의 기본 연산(합집합, 교집합 등)을 지원합니다.

## 예제
기본적인 `frozenset` 사용 예제는 다음과 같습니다:

```python
# frozenset 생성
fset1 = frozenset([1, 2, 3, 4])
fset2 = frozenset([3, 4, 5, 6])

# 집합 연산
union = fset1 | fset2  # 합집합
intersection = fset1 & fset2  # 교집합
difference = fset1 - fset2  # 차집합

print("합집합:", union)  # frozenset({1, 2, 3, 4, 5, 6})
print("교집합:", intersection)  # frozenset({3, 4})
print("차집합:", difference)  # frozenset({1, 2})
```

## 설명
`frozenset`을 사용할 때 주의할 점은 다음과 같습니다:
- **불변성**: `frozenset`의 요소를 변경하려고 하면 `AttributeError`가 발생합니다. 예를 들어, `fset.add(5)` 또는 `fset.remove(1)`은 허용되지 않습니다.
- **해시 가능성**: `frozenset`은 변경할 수 없기 때문에 해시 가능한 객체로 사용될 수 있지만, 내부 요소가 변경 가능한 객체(예: 리스트)를 포함할 수는 없습니다.

## 한 줄 요약
`frozenset`는 Python에서 변경할 수 없는 집합을 생성하여 해시 가능한 객체로 사용할 수 있게 해주는 데이터 타입입니다.