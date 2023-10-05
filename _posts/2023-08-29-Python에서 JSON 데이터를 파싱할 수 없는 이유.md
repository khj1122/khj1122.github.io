---
title: Python에서 JSON 데이터를 파싱할 수 없는 이유
date: 2023-08-29 20:00:00 +0900
categories:
  - python
tags:
  파이썬JSON
---

## JSON 데이터 파싱이란 무엇인가?

JSON(JavaScript Object Notation)은 데이터를 교환하는 한 가지 방법입니다. 파이썬에서 이를 '파싱'한다는 것은 JSON 형식의 문자열을 파이썬 객체로 변환하는 작업을 의미합니다. 이 작업은 통상적으로 `json` 라이브러리의 `loads` 함수를 사용하여 수행됩니다.

## ValueError: Expecting Property Name Enclosed in Double Quotes

파이썬에서 가장 흔하게 발생하는 JSON 파싱 에러 중 하나는 `ValueError: Expecting property name enclosed in double quotes`입니다. 이 에러는 주로 JSON 문자열에서 프로퍼티 이름이 쌍따옴표(`" "`)로 둘러싸이지 않았을 때 발생합니다. 파이썬의 `json` 라이브러리는 이러한 형식을 엄격하게 준수하므로, JSON 데이터가 이 규칙을 어기면 위와 같은 에러가 발생합니다.

## JSON 문자열의 정확한 형식

JSON 형식을 지키기 위해선 몇 가지 주의사항이 있습니다:

1. 프로퍼티 이름과 문자열 값은 반드시 쌍따옴표(`" "`)로 둘러싸여야 합니다.
2. 숫자, 배열, 불리언 값, null은 쌍따옴표 없이 사용할 수 있습니다.
3. 추가적인 쉼표나 빈 공간은 허용되지 않습니다.

## 문제 해결 방법

1. JSON 데이터의 프로퍼티 이름이 쌍따옴표로 둘러싸여 있는지 확인합니다.
2. 데이터 내부에 이스케이프 문자(`\`)가 있는지 확인하고, 필요하면 제거합니다.
3. JSON 데이터가 유효한지 여러 온라인 툴을 통해 검증할 수 있습니다.

이러한 방법들을 통해 대부분의 JSON 파싱 에러를 해결할 수 있습니다. `ValueError: Expecting property name enclosed in double quotes` 에러는 특히 이러한 방법들로 쉽게 해결할 수 있으므로 문제 발생 시 참고하면 좋습니다.