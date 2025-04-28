<!--
Meta Description: # Python에서의 예외 처리(Exception) 완벽 가이드 ## 개요 Python의 예외(Exception)는 프로그램 실행 중 발생할 수 있는 오류를 처리하는 메커니즘입니다. 예외 처리를 통해 프로그램의 비정상 종료를 방지하고, 오류를 우아하게 처리할 수 있습니...
Meta Keywords: except, 예외를, python, try, 있습니다
-->

# Python에서의 예외 처리(Exception) 완벽 가이드

## 개요
Python의 예외(Exception)는 프로그램 실행 중 발생할 수 있는 오류를 처리하는 메커니즘입니다. 예외 처리를 통해 프로그램의 비정상 종료를 방지하고, 오류를 우아하게 처리할 수 있습니다.

## 문서화

### 목적
Python 예외는 프로그램 실행 중 발생할 수 있는 다양한 오류를 관리하는 방법을 제공합니다. 예외 처리를 통해 오류 발생 시 프로그램이 중단되지 않고, 적절한 조치를 취할 수 있도록 도와줍니다.

### 사용법
Python에서는 `try`, `except`, `else`, `finally` 블록을 사용하여 예외를 처리합니다. 기본적인 구조는 다음과 같습니다:

```python
try:
    # 예외가 발생할 가능성이 있는 코드
except SomeException:
    # 예외 발생 시 실행될 코드
else:
    # 예외가 발생하지 않았을 때 실행될 코드
finally:
    # 항상 실행되는 코드
```

- **try**: 예외가 발생할 수 있는 코드를 포함합니다.
- **except**: 특정 예외를 처리하는 코드를 포함합니다. 여러 개의 예외를 처리할 수 있습니다.
- **else**: 예외가 발생하지 않았을 때 실행되는 코드를 포함합니다.
- **finally**: 예외 발생 여부와 상관없이 항상 실행되는 코드를 포함합니다.

### 예제
1. 기본적인 예외 처리:

```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("0으로 나눌 수 없습니다.")
```

2. 여러 개의 예외 처리:

```python
try:
    x = int(input("숫자를 입력하세요: "))
    y = 10 / x
except ValueError:
    print("유효한 숫자를 입력하세요.")
except ZeroDivisionError:
    print("0으로 나눌 수 없습니다.")
```

3. finally 블록 사용:

```python
try:
    file = open('example.txt', 'r')
    content = file.read()
except FileNotFoundError:
    print("파일을 찾을 수 없습니다.")
finally:
    file.close()
```

## 설명
- **일반적인 실수**: 예외를 처리할 때, 특정 예외를 처리하지 않으면 프로그램이 예상치 못한 방식으로 종료될 수 있습니다. 따라서 모든 가능한 예외를 고려해야 합니다.
- **예외 계층 구조**: Python 예외는 계층적 구조를 가지고 있습니다. `Exception` 클래스를 상속받은 여러 서브클래스가 있으며, 이를 통해 구체적인 예외를 정의할 수 있습니다.
- **사용자 정의 예외**: 필요에 따라 사용자 정의 예외를 만들 수 있습니다. 이를 위해 `Exception` 클래스를 상속받아 새로운 예외 클래스를 정의하면 됩니다.

```python
class MyException(Exception):
    pass

try:
    raise MyException("사용자 정의 예외 발생")
except MyException as e:
    print(e)
```

## 한 줄 요약
Python의 예외 처리는 프로그램 실행 중 발생하는 오류를 관리하고, 안정성을 높이는 중요한 메커니즘입니다.