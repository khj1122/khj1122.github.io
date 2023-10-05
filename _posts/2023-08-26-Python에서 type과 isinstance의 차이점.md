---
title: Python에서 type과 isinstance의 차이점
date: 2023-08-26 20:00:00 +0900
categories:
  - python
tags:
---

## `type` 함수의 역할

`type`은 Python에서 객체의 데이터 타입을 알려주는 함수입니다. 이 함수를 사용하면, 해당 객체가 어떤 클래스로부터 만들어졌는지 알 수 있습니다. 예를 들어, `type(123)`을 호출하면 `<class 'int'>`가 반환됩니다. 이는 `123`이 정수(int) 클래스의 인스턴스라는 것을 의미합니다.

```python
x = 123
print(type(x))  # <class 'int'>
```

## `isinstance` 함수의 특징

`isinstance` 함수는 객체가 특정 클래스나 그 클래스의 하위 클래스의 인스턴스인지를 확인합니다. 이 함수는 상속을 고려하므로, 상속 관계에 있는 클래스를 다룰 때 매우 유용합니다.

```python
class Animal:
    pass

class Dog(Animal):
    pass

my_pet = Dog()
print(isinstance(my_pet, Animal))  # True
```

## 두 함수의 주요 차이점

1. **상속 처리**: `isinstance`는 상속을 고려하고, `type`은 그렇지 않습니다.
2. **정확성**: `type`은 객체의 정확한 타입을 알려주지만, `isinstance`는 객체가 속한 클래스의 계층 구조까지 고려합니다.

## 언제 어떤 함수를 사용할까?

- **정확한 타입 확인이 필요한 경우**: `type`을 사용합니다.
- **상속을 고려해야 하는 경우**: `isinstance`를 사용합니다.

## 코드 예시

여기에는 `type`과 `isinstance`를 사용하는 간단한 코드 예시가 있습니다.

```python
# type 사용
if type(x) is int:
    print("x는 정수입니다.")

# isinstance 사용
if isinstance(x, int):
    print("x는 정수 또는 정수를 상속받은 클래스의 인스턴스입니다.")
```

이 글을 통해 `type`과 `isinstance`의 차이점과 각각 언제 사용해야 하는지에 대해 알게 되셨길 바랍니다. 이 두 함수는 Python 프로그래밍에서 자주 사용되므로 잘 알아두면 좋습니다.