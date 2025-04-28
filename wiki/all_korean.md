<!--
Meta Description: # Python의 all() 함수: 모든 요소가 참인지 확인하기 ## 개요 Python의 `all()` 함수는 iterable(반복 가능한 객체)의 모든 요소가 참인지 여부를 검사하는 함수입니다. 모든 요소가 참일 경우 `True`를 반환하고, 하나라도 거짓인 경우 `...
Meta Keywords: all, 요소가, true, result, 함수는
-->

# Python의 all() 함수: 모든 요소가 참인지 확인하기

## 개요
Python의 `all()` 함수는 iterable(반복 가능한 객체)의 모든 요소가 참인지 여부를 검사하는 함수입니다. 모든 요소가 참일 경우 `True`를 반환하고, 하나라도 거짓인 경우 `False`를 반환합니다.

## 문서
### 목적
`all()` 함수는 조건을 만족하는 모든 요소가 있는지를 확인할 때 유용합니다. 주로 리스트, 튜플, 집합 등의 반복 가능한 객체에서 사용되며, 조건문과 함께 사용하여 특정 조건을 체크하는 데 활용됩니다.

### 사용법
`all()` 함수의 기본적인 사용법은 다음과 같습니다:

```python
all(iterable)
```

- **인수**: `iterable` - 검사하려는 반복 가능한 객체를 입력합니다.
- **반환값**: 모든 요소가 참일 경우 `True`, 그렇지 않으면 `False`를 반환합니다.

#### 예외
- 빈 iterable을 입력할 경우 `True`를 반환합니다.

## 예제
```python
# 리스트의 모든 요소가 참인지 확인
numbers = [1, 2, 3, 4]
result = all(num > 0 for num in numbers)
print(result)  # True

# 하나의 요소가 거짓인 경우
numbers = [1, 2, 0, 4]
result = all(num > 0 for num in numbers)
print(result)  # False

# 빈 리스트의 경우
empty_list = []
result = all(empty_list)
print(result)  # True
```

## 설명
`all()` 함수를 사용할 때 주의해야 할 점은 다음과 같습니다:

- **빈 iterable**: 빈 iterable의 경우 `all()`은 항상 `True`를 반환하므로, 이를 고려해야 합니다.
- **데이터 타입**: `all()` 함수는 다양한 데이터 타입(리스트, 튜플, 집합 등)에서 사용 가능하지만, iterable의 요소가 `True`로 평가되는지 여부를 정확히 이해해야 합니다. 예를 들어, 숫자 0, 빈 문자열, `None`은 모두 `False`로 평가됩니다.
- **성능**: `all()` 함수는 첫 번째 `False` 값을 발견하면 즉시 평가를 중단하므로, 성능 측면에서도 유리합니다.

## 한 줄 요약
Python의 `all()` 함수는 iterable의 모든 요소가 참인지 검사하여, 모두 참일 경우 `True`를 반환하는 유용한 함수입니다.