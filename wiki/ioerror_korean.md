<!--
Meta Description: # Python의 IOError: 파일 입출력 오류 처리 ## 개요 Python에서 `IOError`는 파일이나 스트림과 관련된 입출력 작업 중 발생하는 예외입니다. 이 오류는 파일을 열거나 읽거나 쓰는 과정에서 발생할 수 있으며, 프로그램이 예기치 않게 종료되는 것을...
Meta Keywords: ioerror, python, file, try, except
-->

# Python의 IOError: 파일 입출력 오류 처리

## 개요
Python에서 `IOError`는 파일이나 스트림과 관련된 입출력 작업 중 발생하는 예외입니다. 이 오류는 파일을 열거나 읽거나 쓰는 과정에서 발생할 수 있으며, 프로그램이 예기치 않게 종료되는 것을 방지하기 위해 적절히 처리해야 합니다.

## 문서화
`IOError`는 Python 2에서 사용되며, Python 3에서는 `IOError`가 `OSError`로 통합되었습니다. 하지만 Python 2를 사용하는 경우, `IOError`는 다음과 같은 상황에서 발생할 수 있습니다:

- 파일이 존재하지 않거나 경로가 잘못된 경우
- 파일에 대한 권한이 없을 경우
- 디스크 공간이 부족한 경우
- 파일 시스템이 손상된 경우

### 사용법
`IOError`는 일반적으로 `try`와 `except` 블록을 사용하여 처리합니다. 파일 입출력 작업을 수행하는 코드 블록을 `try`에 넣고, `IOError`를 처리하기 위해 `except` 블록을 사용합니다.

```python
try:
    with open('example.txt', 'r') as file:
        content = file.read()
except IOError as e:
    print(f"파일을 열 수 없습니다: {e}")
```

## 예제
다음은 `IOError`를 처리하는 몇 가지 기본적인 예제입니다.

### 예제 1: 파일 읽기
```python
try:
    with open('non_existing_file.txt', 'r') as file:
        data = file.read()
except IOError as e:
    print(f"오류 발생: {e}")
```

### 예제 2: 파일 쓰기
```python
try:
    with open('/protected_path/example.txt', 'w') as file:
        file.write("Hello, World!")
except IOError as e:
    print(f"오류 발생: {e}")
```

## 설명
`IOError`는 특정 상황에서 발생할 수 있으며, 다음과 같은 일반적인 함정과 주의점이 있습니다:

- **파일 경로 확인**: 파일 경로가 올바르지 않으면 `IOError`가 발생합니다. 항상 경로를 확인하고, 필요한 경우 절대 경로를 사용하세요.
- **권한 문제**: 쓰기 권한이 없는 디렉토리에 파일을 쓰려고 하면 `IOError`가 발생합니다. 필요한 권한이 있는지 확인하세요.
- **파일 모드**: 파일을 열 때 지정한 모드와 일치하지 않는 작업을 시도하면 오류가 발생할 수 있습니다. 예를 들어, 읽기 전용 모드로 연 파일에 쓰기를 시도하면 `IOError`가 발생합니다.

## 한 줄 요약
Python에서 `IOError`는 파일 입출력 작업 중 발생하는 오류로, 적절한 예외 처리가 필요합니다.