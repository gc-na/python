<!--
Meta Description: # Python의 KeyboardInterrupt: 프로그램 중단하기 ## 개요 `KeyboardInterrupt`는 Python에서 사용자가 프로그램 실행을 중단할 때 발생하는 예외입니다. 일반적으로 Ctrl+C 키 조합을 사용하여 프로그램을 강제 종료할 수 있습니다...
Meta Keywords: keyboardinterrupt, 사용자가, ctrl, 있습니다, 프로그램
-->

# Python의 KeyboardInterrupt: 프로그램 중단하기

## 개요
`KeyboardInterrupt`는 Python에서 사용자가 프로그램 실행을 중단할 때 발생하는 예외입니다. 일반적으로 Ctrl+C 키 조합을 사용하여 프로그램을 강제 종료할 수 있습니다.

## 문서화
`KeyboardInterrupt`는 Python의 내장 예외로, 사용자가 실행 중인 프로그램을 중단하고자 할 때 발생합니다. 이 예외는 주로 무한 루프나 긴 실행 시간을 가진 작업에서 유용합니다. 사용자가 Ctrl+C를 누르면 Python 인터프리터는 현재 실행 중인 프로세스를 중단하고 `KeyboardInterrupt` 예외를 발생시킵니다.

### 목적
- 프로그램의 실행을 안전하게 중단하기 위해 사용됩니다.
- 사용자에게 프로그램을 종료할 수 있는 방법을 제공합니다.

### 사용법
`KeyboardInterrupt`를 처리하려면 try-except 블록을 사용할 수 있습니다. 프로그램이 중단될 때 필요한 정리 작업을 수행하거나 사용자에게 알림을 제공할 수 있습니다.

```python
try:
    while True:
        print("작업 중... (Ctrl+C로 중단 가능)")
except KeyboardInterrupt:
    print("프로그램이 중단되었습니다.")
```

## 예제
### 기본 사용 예제
다음은 `KeyboardInterrupt`를 처리하는 간단한 예제입니다.

```python
try:
    for i in range(10):
        print(i)
except KeyboardInterrupt:
    print("사용자에 의해 중단됨.")
```

이 코드에서는 0부터 9까지의 숫자를 출력하며, 사용자가 Ctrl+C를 누르면 "사용자에 의해 중단됨."이라는 메시지가 출력됩니다.

## 설명
`KeyboardInterrupt` 예외를 사용할 때 주의해야 할 점은 다음과 같습니다:

- **무한 루프**: 프로그램이 무한 루프에 있을 때 `KeyboardInterrupt`가 발생합니다. 루프 안에 있는 코드는 정상적으로 종료되지 않을 수 있습니다.
- **정리 작업**: 프로그램 종료 시 리소스를 해제하거나 파일을 닫아야 하는 경우, `KeyboardInterrupt`를 통해 이를 처리하는 것이 필요합니다.
- **기타 예외와의 관계**: `KeyboardInterrupt`는 다른 예외와 동일하게 작동하므로, 필요한 경우 추가적인 예외 처리 로직을 구현할 수 있습니다.

## 한 줄 요약
`KeyboardInterrupt`는 Python에서 사용자가 프로그램 실행을 중단할 때 발생하는 예외로, 주로 Ctrl+C를 통해 활성화됩니다.