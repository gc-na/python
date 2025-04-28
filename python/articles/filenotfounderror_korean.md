<!--
Meta Description: # Python의 FileNotFoundError: 파일을 찾을 수 없을 때 발생하는 오류 ## 개요 `FileNotFoundError`는 Python에서 지정한 파일이나 디렉토리를 찾을 수 없을 때 발생하는 예외입니다. 이 오류는 파일 입출력 작업 중 흔히 발생하며,...
Meta Keywords: filenotfounderror, 파일을, 파일이, file, 있습니다
-->

# Python의 FileNotFoundError: 파일을 찾을 수 없을 때 발생하는 오류

## 개요
`FileNotFoundError`는 Python에서 지정한 파일이나 디렉토리를 찾을 수 없을 때 발생하는 예외입니다. 이 오류는 파일 입출력 작업 중 흔히 발생하며, 프로그램의 정상적인 흐름을 방해합니다.

## 문서화
### 목적
`FileNotFoundError`는 파일 시스템에서 요청한 파일이 존재하지 않을 때 발생합니다. 이는 주로 잘못된 파일 경로, 파일 이름 오타, 또는 파일이 삭제된 경우에 발생할 수 있습니다.

### 사용법
`FileNotFoundError`는 파이썬의 기본 예외 클래스인 `OSError`의 하위 클래스입니다. 이 예외는 파일을 열거나 읽으려 할 때 발생하며, 일반적으로 다음과 같은 상황에서 발생합니다:

- 파일을 열기 위해 `open()` 함수를 사용할 때 파일 경로가 잘못된 경우
- 디렉토리 내 파일을 찾으려고 할 때 파일이 존재하지 않는 경우

### 세부 사항
`FileNotFoundError`는 Python 3.x 버전에서 사용되며, 이전 버전에서는 `IOError`가 사용되었습니다. 이 오류는 파일 입출력 작업을 수행하는 코드에 적절한 예외 처리를 추가하여 안전하게 관리할 수 있습니다.

## 예제
```python
# 잘못된 파일 경로로 파일 열기
try:
    with open('잘못된_파일.txt', 'r') as file:
        content = file.read()
except FileNotFoundError as e:
    print(f"오류 발생: {e}")

# 존재하지 않는 파일에 대한 파일 생성
try:
    with open('존재하지_않는_파일.txt', 'r') as file:
        content = file.read()
except FileNotFoundError:
    print('파일을 찾을 수 없습니다. 새로운 파일을 생성합니다.')
    with open('존재하지_않는_파일.txt', 'w') as file:
        file.write('이 파일은 새로 생성되었습니다.')
```

## 설명
`FileNotFoundError`를 처리할 때 주의해야 할 점은 다음과 같습니다:

- **파일 경로 확인**: 파일 경로가 정확한지 확인해야 합니다. 상대 경로와 절대 경로를 혼동할 수 있습니다.
- **파일 권한**: 파일이 존재하더라도 접근 권한이 없을 경우 다른 예외가 발생할 수 있습니다.
- **파일 삭제**: 프로그램 실행 중 파일이 삭제되는 경우에도 이 오류가 발생할 수 있습니다.

예외 처리를 통해 프로그램이 오류로 인해 중단되지 않도록 해야 합니다.

## 한 줄 요약
`FileNotFoundError`는 Python에서 요청한 파일이 존재하지 않을 때 발생하는 예외입니다.