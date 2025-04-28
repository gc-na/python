<!--
Meta Description: # Python의 콜러블(callable): 개념과 사용법 ## 개요 Python에서 **콜러블(callable)**은 호출 가능한 객체를 의미합니다. 이는 함수, 메서드, 클래스 인스턴스 등과 같이 호출할 수 있는 모든 객체를 포함합니다. 이 개념은 Python 프로...
Meta Keywords: callable, 객체를, python, 콜러블, python에서
-->

# Python의 콜러블(callable): 개념과 사용법

## 개요
Python에서 **콜러블(callable)**은 호출 가능한 객체를 의미합니다. 이는 함수, 메서드, 클래스 인스턴스 등과 같이 호출할 수 있는 모든 객체를 포함합니다. 이 개념은 Python 프로그래밍에서 매우 중요하며, 다양한 활용도가 있습니다.

## 문서화
콜러블은 Python의 다양한 기능을 사용할 수 있게 해주는 중요한 개념입니다. Python에서 객체가 호출 가능하려면 `__call__` 메서드를 구현해야 합니다. 이를 통해 인스턴스 객체를 마치 함수처럼 사용할 수 있습니다.

### 목적
콜러블의 주요 목적은 코드를 더 유연하고 재사용 가능하게 만드는 것입니다. 함수형 프로그래밍 스타일을 지원하며, 고차 함수(higher-order function)와 함께 사용될 때 그 진가를 발휘합니다.

### 사용법
Python에서 객체가 콜러블인지 확인하기 위해 `callable()` 함수를 사용할 수 있습니다. 이 함수는 인자로 전달된 객체가 호출 가능한지 여부를 Boolean 값으로 반환합니다.

```python
callable(object)
```

### 예제
1. **기본 함수**
   ```python
   def my_function():
       return "Hello, World!"

   print(callable(my_function))  # True
   ```

2. **클래스 인스턴스**
   ```python
   class MyClass:
       def __call__(self):
           return "Instance called!"

   my_instance = MyClass()
   print(callable(my_instance))  # True
   ```

3. **일반 객체**
   ```python
   class NotCallable:
       pass

   obj = NotCallable()
   print(callable(obj))  # False
   ```

## 설명
콜러블 객체를 사용할 때 주의해야 할 점은 `__call__` 메서드를 정의하지 않은 클래스의 인스턴스는 호출할 수 없다는 것입니다. 또한, 내장 함수나 메서드는 항상 호출 가능하지만, 일반 객체는 그렇지 않다는 점도 유의해야 합니다. 

콜러블은 고차 함수와 함께 사용될 때 함수의 매개변수로 전달할 수 있어 강력한 기능을 발휘합니다. 예를 들어, 특정 조건에 따라 다른 함수를 호출하는 로직을 작성할 수 있습니다.

## 한 줄 요약
Python에서 콜러블(callable)은 호출 가능한 객체를 의미하며, 함수, 메서드, 클래스 인스턴스를 포함합니다.