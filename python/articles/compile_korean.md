<!--
Meta Description: # Python의 compile() 함수: 코드 컴파일의 모든 것 ## 개요 Python의 `compile()` 함수는 소스 코드를 바이트 코드로 변환하여 실행할 수 있게 해주는 기능입니다. 이 함수는 주로 동적으로 생성된 코드의 실행이나 소스 코드의 효율적인 실행을 ...
Meta Keywords: compile, exec, 코드의, eval, python
-->

# Python의 compile() 함수: 코드 컴파일의 모든 것

## 개요
Python의 `compile()` 함수는 소스 코드를 바이트 코드로 변환하여 실행할 수 있게 해주는 기능입니다. 이 함수는 주로 동적으로 생성된 코드의 실행이나 소스 코드의 효율적인 실행을 위해 사용됩니다.

## 문서화

### 목적
`compile()` 함수는 문자열 형태의 소스 코드를 바이트 코드로 변환하여, Python의 내장 `exec()` 또는 `eval()` 함수와 함께 사용할 수 있도록 합니다. 이렇게 변환된 코드는 Python 인터프리터에 의해 실행될 수 있습니다.

### 사용법
`compile()` 함수의 기본 구문은 다음과 같습니다:

```python
compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)
```

#### 매개변수 설명
- `source`: 컴파일할 코드의 문자열 또는 AST(추상 구문 트리)입니다.
- `filename`: 소스 코드의 파일 이름을 나타내는 문자열입니다. 주로 에러 메시지에서 사용됩니다.
- `mode`: `'exec'`, `'eval'`, 또는 `'single'` 중 하나로, 코드의 실행 모드를 정의합니다.
  - `'exec'`: 여러 문장을 포함하는 코드 블록을 컴파일합니다.
  - `'eval'`: 단일 표현식을 컴파일합니다.
  - `'single'`: 단일 문장을 컴파일합니다.
- `flags`: 컴파일 시 사용할 플래그를 지정합니다.
- `dont_inherit`: 기본값은 `False`이며, `True`로 설정하면 현재의 컴파일 플래그를 상속받지 않습니다.
- `optimize`: 최적화 수준을 지정합니다. 기본값은 `-1`로, 최적화를 수행하지 않습니다.

### 예제
1. 기본 사용 예:

```python
code = 'print("Hello, World!")'
compiled_code = compile(code, '<string>', 'exec')
exec(compiled_code)
```

2. 표현식 컴파일 예:

```python
expression = '3 + 4'
compiled_expression = compile(expression, '<string>', 'eval')
result = eval(compiled_expression)
print(result)  # 출력: 7
```

3. 단일 문장 컴파일 예:

```python
statement = 'x = 10'
compiled_statement = compile(statement, '<string>', 'single')
exec(compiled_statement)
print(x)  # 출력: 10
```

## 설명
`compile()` 함수를 사용할 때 유의해야 할 점은 다음과 같습니다:
- 컴파일된 코드의 오류는 실행 시에 발생하므로, 코드가 올바르게 작성되었는지 반드시 확인해야 합니다.
- `eval()`과 `exec()` 함수를 사용할 때는 보안에 유의해야 합니다. 신뢰할 수 없는 소스의 코드를 실행하는 것은 위험할 수 있습니다.
- `mode` 파라미터를 잘못 설정하면 의도한 대로 코드가 실행되지 않을 수 있습니다. 각 모드의 차이를 이해하고 적절히 사용해야 합니다.

## 한 줄 요약
Python의 `compile()` 함수는 문자열 형태의 소스 코드를 바이트 코드로 변환하여 실행할 수 있도록 지원하는 기능입니다.