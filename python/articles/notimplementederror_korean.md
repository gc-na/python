<!--
Meta Description: # Python의 NotImplementedError: 기능 및 사용법 ## 개요 `NotImplementedError`는 Python에서 특정 메서드나 함수가 구현되지 않았음을 나타내는 내장 예외입니다. 주로 추상 클래스에서 메서드를 정의할 때, 하위 클래스에서 해당...
Meta Keywords: notimplementederror, 클래스에서, 메서드를, self, circle
-->

# Python의 NotImplementedError: 기능 및 사용법

## 개요
`NotImplementedError`는 Python에서 특정 메서드나 함수가 구현되지 않았음을 나타내는 내장 예외입니다. 주로 추상 클래스에서 메서드를 정의할 때, 하위 클래스에서 해당 메서드를 반드시 구현하도록 강제하기 위해 사용됩니다.

## 문서화
### 목적
`NotImplementedError`는 개발자가 인터페이스의 일부로 메서드를 정의했지만, 실제 구현은 제공하지 않을 때 사용됩니다. 이 예외는 코드의 명확성과 유지보수성을 높이는 데 기여합니다.

### 사용법
`NotImplementedError`는 일반적으로 다음과 같이 사용됩니다:

```python
class MyAbstractClass:
    def my_method(self):
        raise NotImplementedError("Subclasses must implement this method.")
```

위의 예에서 `MyAbstractClass`는 `my_method`를 정의하지만, 실제 메서드의 구현은 하위 클래스에서 제공해야 합니다. 하위 클래스에서 이 메서드를 호출하면 `NotImplementedError`가 발생합니다.

### 세부 사항
- `NotImplementedError`는 `Exception` 클래스의 서브클래스입니다.
- 이 예외는 주로 추상 클래스를 정의할 때 사용되며, 구현되지 않은 메서드에 대한 명확한 경고를 제공합니다.
- Python의 `abc` 모듈을 사용하여 추상 클래스를 정의할 경우, `@abstractmethod` 데코레이터로 메서드에 자동으로 `NotImplementedError`를 던질 수 있습니다.

## 예제
### 기본 사용 예
```python
class Shape:
    def area(self):
        raise NotImplementedError("Subclass must implement abstract method.")

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * (self.radius ** 2)

# 사용 예
circle = Circle(5)
print(circle.area())  # 78.5
```

위의 예제에서 `Shape` 클래스는 `area` 메서드를 정의하지만 구현하지 않았습니다. `Circle` 클래스에서 이 메서드를 구현하여 원의 면적을 계산합니다.

## 설명
`NotImplementedError`를 사용할 때의 일반적인 실수는 하위 클래스에서 메서드를 구현하지 않고 호출하는 것입니다. 이 경우 예외가 발생하며, 이는 프로그램의 실행을 중단시킬 수 있습니다. 따라서 반드시 하위 클래스에서 해당 메서드를 구현해야 합니다.

또한, `NotImplementedError`는 주로 개발 중에 발생하는 예외로, 실제 배포 버전에서는 이러한 예외가 발생하지 않도록 코드를 작성해야 합니다. 이를 통해 코드의 안정성을 높일 수 있습니다.

## 한 줄 요약
`NotImplementedError`는 Python에서 특정 메서드가 구현되지 않았음을 나타내는 예외로, 주로 추상 클래스에서 사용됩니다.