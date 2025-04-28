<!--
Meta Description: # 파이썬 RecursionError: 재귀 호출의 한계 ## 개요 `RecursionError`는 파이썬에서 재귀 함수가 너무 깊게 호출될 때 발생하는 오류입니다. 이 오류는 무한 재귀나 잘못된 종료 조건으로 인해 발생하며, 프로그래머가 재귀 호출의 깊이를 초과했음을...
Meta Keywords: recursionerror, return, 호출이, fibonacci, 함수가
-->

# 파이썬 RecursionError: 재귀 호출의 한계

## 개요
`RecursionError`는 파이썬에서 재귀 함수가 너무 깊게 호출될 때 발생하는 오류입니다. 이 오류는 무한 재귀나 잘못된 종료 조건으로 인해 발생하며, 프로그래머가 재귀 호출의 깊이를 초과했음을 알리는 신호입니다.

## 문서화
`RecursionError`는 파이썬의 내장 예외 중 하나로, 재귀 함수 호출이 시스템이 허용하는 최대 한계를 초과했을 때 발생합니다. 파이썬의 기본 재귀 깊이는 1000으로 설정되어 있으며, 이는 `sys` 모듈을 통해 변경할 수 있습니다. 재귀 호출이 필요한 경우, 종료 조건을 명확히 설정해야 하며, 무한 루프에 빠지지 않도록 주의해야 합니다.

### 사용법
재귀 함수는 함수가 자기 자신을 호출하는 구조입니다. 재귀를 사용할 때는 항상 종료 조건을 명시해야 하며, 그렇지 않으면 `RecursionError`가 발생할 수 있습니다.

```python
import sys

# 최대 재귀 깊이 설정
sys.setrecursionlimit(1500)

def factorial(n):
    if n < 0:
        raise ValueError("음수의 팩토리얼은 정의되지 않습니다.")
    elif n == 0:
        return 1
    else:
        return n * factorial(n - 1)
```

## 예제
다음은 `RecursionError`를 발생시키는 간단한 예제입니다.

```python
def infinite_recursion():
    return infinite_recursion()

# 이 코드를 실행하면 RecursionError가 발생합니다.
# infinite_recursion()
```

### 재귀 함수 사용 예제
올바른 종료 조건을 가진 재귀 함수의 예입니다.

```python
def fibonacci(n):
    if n <= 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

print(fibonacci(5))  # 결과: 5
```

## 설명
`RecursionError`는 재귀 호출이 과도하게 중첩되었을 때 발생합니다. 이는 무한 루프에 빠지거나, 종료 조건이 잘못 설정된 경우에 흔히 나타납니다. 

### 일반적인 문제점
- **무한 재귀**: 종료 조건이 누락되거나 잘못된 경우.
- **재귀 깊이 초과**: 시스템의 기본 재귀 깊이 설정을 초과하는 경우.
- **메모리 부족**: 재귀 호출이 깊어질수록 메모리 사용량이 증가하여 시스템 자원이 고갈될 수 있습니다.

## 한 줄 요약
`RecursionError`는 파이썬에서 재귀 함수가 최대 호출 깊이를 초과했을 때 발생하는 오류입니다.