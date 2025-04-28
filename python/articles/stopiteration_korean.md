<!--
Meta Description: # Python의 StopIteration: 반복 작업을 중단하는 방법 ## 개요 `StopIteration`은 Python에서 반복 가능한 객체의 끝을 나타내는 예외입니다. 주로 이터레이터를 사용할 때 발생하며, 이터레이션이 완료되었음을 알리는 역할을 합니다. ## ...
Meta Keywords: stopiteration, self, end, current, 예외가
-->

# Python의 StopIteration: 반복 작업을 중단하는 방법

## 개요
`StopIteration`은 Python에서 반복 가능한 객체의 끝을 나타내는 예외입니다. 주로 이터레이터를 사용할 때 발생하며, 이터레이션이 완료되었음을 알리는 역할을 합니다.

## 문서화
### 목적
`StopIteration` 예외는 이터레이터가 더 이상 반환할 항목이 없음을 나타냅니다. 이 예외가 발생하면 반복문(예: `for` 루프)을 안전하게 종료할 수 있습니다.

### 사용법
이터레이터를 사용할 때, `__next__()` 메소드를 호출하면 다음 항목을 반환합니다. 더 이상 반환할 항목이 없을 경우, `StopIteration` 예외가 발생합니다. 이를 통해 반복문은 자동으로 종료됩니다.

### 세부사항
- `StopIteration`은 기본적으로 `iter()` 함수와 `next()` 함수에 의해 사용됩니다.
- 이 예외는 사용자가 직접 발생시킬 수 있으며, 사용자 정의 이터레이터 클래스에서 사용될 수 있습니다.
- 이 예외가 발생하면, 반복문은 현재 이터레이션을 종료하고 다음 코드를 실행합니다.

## 예제
### 기본 사용 예
```python
class MyRange:
    def __init__(self, start, end):
        self.current = start
        self.end = end

    def __iter__(self):
        return self

    def __next__(self):
        if self.current < self.end:
            result = self.current
            self.current += 1
            return result
        else:
            raise StopIteration

# 사용 예
for num in MyRange(1, 5):
    print(num)
```
이 코드는 `1`부터 `4`까지의 숫자를 출력합니다. `StopIteration`이 발생하면 반복이 종료됩니다.

## 설명
- **일반적인 오류**: `StopIteration` 예외를 적절히 처리하지 않으면 프로그램이 중단될 수 있습니다. 반복문 내에서 무한 루프를 피하기 위해 `StopIteration` 예외를 적절히 활용해야 합니다.
- **추가 메모**: 사용자가 정의한 이터레이터에서 `StopIteration`을 발생시키는 것 외에도, 내장 이터레이터에서도 자동으로 처리됩니다. 예를 들어, 리스트, 튜플, 딕셔너리 등은 기본적으로 이터러블하며, 이터레이션이 끝나면 자동으로 `StopIteration`을 발생시킵니다.

## 한 줄 요약
`StopIteration`은 Python에서 이터레이터의 끝을 나타내는 예외로, 반복문이 안전하게 종료될 수 있도록 돕습니다.