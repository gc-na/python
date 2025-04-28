<!--
Meta Description: # Python에서의 ModuleNotFoundError: 해결 방법과 예제 ## 개요 `ModuleNotFoundError`는 Python에서 모듈을 찾을 수 없을 때 발생하는 예외입니다. 이 오류는 모듈이 설치되지 않았거나, 잘못된 경로를 참조하고 있을 때 주로 발...
Meta Keywords: modulenotfounderror, 모듈을, 발생합니다, 모듈이, 있습니다
-->

# Python에서의 ModuleNotFoundError: 해결 방법과 예제

## 개요
`ModuleNotFoundError`는 Python에서 모듈을 찾을 수 없을 때 발생하는 예외입니다. 이 오류는 모듈이 설치되지 않았거나, 잘못된 경로를 참조하고 있을 때 주로 발생합니다.

## 문서화
### 목적
`ModuleNotFoundError`는 Python의 내장 예외로, 특정 모듈을 가져오려고 시도할 때 해당 모듈이 존재하지 않을 경우 발생합니다. 이를 통해 개발자는 코드에서 누락된 종속성을 쉽게 찾아낼 수 있습니다.

### 사용법
`ModuleNotFoundError`는 주로 `import` 문을 사용할 때 발생합니다. 예를 들어, 사용자가 `import module_name`을 시도했지만 Python이 해당 모듈을 찾지 못할 경우 이 오류가 발생합니다. 

이 예외는 Python 3.6부터 도입되었으며, 이전 버전에서는 `ImportError`로 처리되었습니다. 따라서 Python 3.6 이상에서는 `ModuleNotFoundError`를 통해 보다 구체적인 오류 메시지를 제공합니다.

### 세부사항
- **오류 메세지**: 오류 메시지는 "No module named 'module_name'"의 형식으로 표시됩니다.
- **해결 방법**: 이 오류를 해결하기 위해서는 모듈을 설치하거나, 경로를 확인하고 수정해야 합니다. `pip`를 사용하여 필요한 모듈을 설치할 수 있습니다.
  
## 예제
### 예제 1: 모듈 미설치
```python
import non_existent_module
```
이 경우 `ModuleNotFoundError: No module named 'non_existent_module'` 오류가 발생합니다.

### 예제 2: 모듈 경로 오류
```python
import some_package.some_module
```
`some_package`가 존재하지 않거나, `some_module`이 그 안에 없다면 역시 `ModuleNotFoundError`가 발생합니다.

## 설명
### 일반적인 실수 및 주의사항
1. **모듈 이름 오타**: 모듈 이름을 잘못 입력한 경우 이 오류가 발생할 수 있습니다. 정확한 이름을 확인하세요.
2. **가상 환경**: 가상 환경을 사용하고 있다면, 필요한 모듈이 해당 환경에 설치되어 있는지 확인해야 합니다.
3. **PYTHONPATH**: 환경 변수 `PYTHONPATH`가 잘못 설정된 경우도 모듈을 찾지 못할 수 있습니다. 이 변수를 확인하고, 필요한 경로를 추가하세요.

## 한 줄 요약
`ModuleNotFoundError`는 Python에서 모듈을 찾을 수 없을 때 발생하는 예외로, 주로 모듈이 설치되지 않았거나 경로가 잘못되었을 때 나타납니다.