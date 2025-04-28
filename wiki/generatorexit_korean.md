<!--
Meta Description: # GeneratorExit: 파이썬의 제너레이터 종료 예외 ## 개요 `GeneratorExit`는 파이썬에서 제너레이터가 종료될 때 발생하는 특수한 예외입니다. 이 예외는 제너레이터가 `close()` 메서드에 의해 종료될 때 발생하며, 제너레이터 내부에서 이를 처...
Meta Keywords: generatorexit, 제너레이터가, 제너레이터, 종료될, close
-->

# GeneratorExit: 파이썬의 제너레이터 종료 예외

## 개요
`GeneratorExit`는 파이썬에서 제너레이터가 종료될 때 발생하는 특수한 예외입니다. 이 예외는 제너레이터가 `close()` 메서드에 의해 종료될 때 발생하며, 제너레이터 내부에서 이를 처리할 수 있도록 설계되었습니다.

## 문서화
### 목적
`GeneratorExit`는 제너레이터가 정상적으로 종료되었음을 나타내며, 제너레이터가 자원을 해제하거나 정리 작업을 수행할 수 있도록 합니다.

### 사용법
`GeneratorExit`는 제너레이터 함수 내에서 발생하며, `try...except` 블록을 사용하여 처리할 수 있습니다. 제너레이터가 종료될 때 `close()` 메서드가 호출되면, 제너레이터 내부에서 `GeneratorExit` 예외가 발생합니다.

### 세부 사항
- `GeneratorExit`는 일반 예외와 달리, 제너레이터가 종료되는 상황에서만 발생합니다.
- `close()` 메서드가 호출되면, 제너레이터는 현재 실행 중인 상태에서 `GeneratorExit` 예외를 발생시키고, 이 예외는 제너레이터 내부에서 처리될 수 있습니다.
- 만약 제너레이터가 `GeneratorExit` 예외를 처리하지 않으면, 제너레이터는 바로 종료됩니다.

## 예제
아래는 `GeneratorExit`를 사용하는 간단한 예제입니다.

```python
def my_generator():
    try:
        yield "First value"
        yield "Second value"
    except GeneratorExit:
        print("Generator is closing.")
    finally:
        print("Cleanup actions here.")

gen = my_generator()
print(next(gen))  # First value
print(next(gen))  # Second value
gen.close()  # Generator is closing. Cleanup actions here.
```

## 설명
- `GeneratorExit`는 제너레이터가 종료될 때 발생하는 예외이므로, 제너레이터의 `close()` 메서드 호출 시 주의해야 합니다.
- 제너레이터 내부에서 `GeneratorExit`를 처리하지 않으면, 제너레이터는 비정상적으로 종료될 수 있으며, 자원 해제가 제대로 이루어지지 않을 수 있습니다.
- `finally` 블록을 사용하여 청소 작업을 수행하는 것이 좋은 관행입니다.

## 한 줄 요약
`GeneratorExit`는 제너레이터가 종료될 때 발생하는 예외로, 제너레이터 내부에서 적절히 처리해야 합니다.