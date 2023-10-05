---
title: Python에서 *args와 **kwargs의 활용
date: 2023-08-27 20:00:00 +0900
categories:
  - python
tags:
  - 파이썬파라미터
---

## 무엇이 args와 kwargs인가?

`*args`와 `**kwargs`는 Python 프로그래밍에서 매개변수(parameter)를 유연하게 관리하는 방법입니다. `*args`는 위치 인자(variable-length positional arguments)를 튜플로 받고, `**kwargs`는 키워드 인자(keyword arguments)를 딕셔너리로 받습니다.

## *args의 작동 원리

`*args`는 함수에 몇 개의 위치 인자를 전달할지 모를 때 사용합니다. 예를 들어, 여러 숫자의 평균을 구하는 함수를 만들 때 이를 활용할 수 있습니다.

```python
def average(*nums):
    return sum(nums) / len(nums)
```

여기서 `*nums`는 받은 모든 위치 인자를 `nums` 튜플에 저장합니다.

### 예제

```python
print(average(1, 2, 3))  # 결과: 2.0
print(average(10, 20, 30, 40))  # 결과: 25.0
```

## **kwargs의 작동 원리

`**kwargs`는 함수에 여러 키워드 인자를 전달할 수 있게 해줍니다. 예를 들어, 사람의 정보를 출력하는 함수에서 활용할 수 있습니다.

```python
def print_info(**details):
    for key, value in details.items():
        print(f"{key}: {value}")
```

### 예제

```python
print_info(name="John", age=30, country="USA")
```

이 함수는 다음과 같은 출력을 만듭니다:

```
name: John
age: 30
country: USA
```

## args와 kwargs를 함께 사용하기

두 개를 함께 사용할 수도 있습니다만, 순서에 주의해야 합니다. 일반적인 순서는 일반 인자, `*args`, 그리고 `**kwargs`입니다.

```python
def function(arg1, *args, **kwargs):
    pass
```

## 주의사항

- 함수 선언에서 `*args`가 `**kwargs`보다 먼저 나와야 합니다.
- `*`와 `**`는 실제로 매개변수 이름에 포함되지 않습니다. 이것들은 위치 인자와 키워드 인자를 각각 튜플과 딕셔너리로 묶을 것임을 Python에게 알려주는 역할을 합니다.

이러한 유연성 덕분에 Python에서는 함수를 매우 다양하게 활용할 수 있습니다.