---
title: Pandas에서 SettingWithCopyWarning 다루기
date: 2023-09-27 20:00:00 +0900
categories:
  - python
tags:
---

## 문제 상황과 오류 메시지

Pandas를 이용한 데이터 처리 중 `SettingWithCopyWarning`라는 경고 메시지를 본 적 있나요? 이 경고는 보통 DataFrame을 복사하고 복사한 DataFrame에 값을 할당할 때 나타납니다. 여기서 복사한 DataFrame은 원래 DataFrame의 일부이며, 이런 상황에서 값을 변경하면 원래 DataFrame에 영향을 줄 수 있습니다. 오류 메시지는 대략 다음과 같이 나옵니다:

```
SettingWithCopyWarning: A value is trying to be set on a copy of a slice from a DataFrame.
```

## 원인 파악

`SettingWithCopyWarning`이 발생하는 주된 원인은 Pandas가 내부적으로 DataFrame을 어떻게 관리하는지와 관련이 있습니다. DataFrame은 행과 열로 구성된 데이터 테이블입니다. 일부 데이터만 선택하여 새로운 DataFrame을 만들 경우, 이 새 DataFrame은 원본 DataFrame과 데이터를 공유하게 됩니다. 이렇게 되면 새 DataFrame에 변경을 가하면 원본 DataFrame도 영향을 받을 가능성이 있습니다.

## 해결 방법 1: .copy() 사용

가장 간단한 방법은 `.copy()` 함수를 이용해서 DataFrame을 명시적으로 복사하는 것입니다. 이렇게 하면 원본 DataFrame과 별개의 데이터를 가진 새로운 DataFrame이 생성됩니다.

```python
new_df = original_df.copy()
```

## 해결 방법 2: `.loc[]` 사용

`.loc[]` 메서드를 이용하면, 원본 DataFrame에서 필요한 부분만 선택하여 변경할 수 있습니다. 이 방법은 원본 DataFrame에 직접 수정을 가하는 방법이므로 `SettingWithCopyWarning` 오류를 피할 수 있습니다.

```python
original_df.loc[조건, '열_이름'] = '새로운 값'
```

## 해결 방법 3: 경고 무시

경고 메시지가 나타나더라도 문제가 없다고 판단된다면, 경고를 무시하는 방법도 있습니다. Pandas 설정을 통해 경고를 무시할 수 있습니다. 

```python
import pandas as pd
pd.options.mode.chained_assignment = None
```

## 결론

`SettingWithCopyWarning`은 DataFrame을 안전하게 관리하기 위한 경고 메시지입니다. 이를 해결하기 위한 몇 가지 방법을 알아보았습니다. 명시적으로 DataFrame을 복사하거나, 원본 DataFrame에 직접 수정을 가하거나, 필요에 따라 경고를 무시하는 방법이 있습니다. 이러한 방법 중에서 상황에 맞는 최적의 해결책을 선택해 주세요.