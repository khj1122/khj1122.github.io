---
title: 문자열 포매팅 방법 % 연산자, format 함수, f-string
date: 2023-09-08 20:00:00 +0900
categories:
  - python
tags:
  - 파이썬문자열
---

## `%` 연산자를 사용한 문자열 포매팅

`%` 연산자는 문자열 포매팅에 가장 오래 전부터 사용되던 방식입니다. 이 방식은 C 언어의 `printf` 함수와 유사하게 작동합니다. 문자열 내에서 `%s`, `%d` 등의 형식 지정자를 사용하여 값을 대입합니다.

```python
name = "John"
age = 30
print("My name is %s and I am %d years old." % (name, age))
```

### 장점과 단점
- **장점**: 이 방식은 오래되어서 대부분의 Python 코드에서 볼 수 있습니다.
- **단점**: 문자열과 변수를 따로 관리해야 하므로 가독성이 떨어질 수 있습니다.

## `format` 함수를 사용한 문자열 포매팅

Python 2.6부터 도입된 `format` 함수는 `{}`를 사용해 변수를 대입합니다.

```python
name = "John"
age = 30
print("My name is {} and I am {} years old.".format(name, age))
```

### 장점과 단점
- **장점**: `%` 연산자보다 훨씬 유연하고, 다양한 형식의 값도 쉽게 처리할 수 있습니다.
- **단점**: 가독성이 좋은 편은 아니며, 문자열 내에서 순서를 지정해야 할 수도 있습니다.

## `f-string`을 사용한 문자열 포매팅

Python 3.6부터 사용 가능한 `f-string`은 문자열 앞에 `f`를 붙여 변수를 바로 문자열 내부에 넣을 수 있습니다.

```python
name = "John"
age = 30
print(f"My name is {name} and I am {age} years old.")
```

### 장점과 단점
- **장점**: 가독성이 뛰어나고, 직관적으로 사용할 수 있습니다.
- **단점**: Python 3.6 이상에서만 사용할 수 있습니다.

## 어떤 방식을 사용할까?

각 방식은 장단점이 있으므로, 프로젝트의 요구사항과 Python 버전에 따라 적절한 방식을 선택하면 됩니다. `f-string`이 가장 최근에 도입되었고 가독성이 뛰어나므로, 가능하다면 이 방식을 사용하는 것이 좋습니다.