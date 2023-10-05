---
title: Pandas에서 특정 열에 NaN 값이 있는 행 삭제하기
date: 2023-09-17 20:00:00 +0900
categories:
  - python
tags:
  - pandas
---

## 소개
Pandas는 데이터 분석에 매우 유용한 Python 라이브러리입니다. 이 글에서는 Pandas DataFrame에서 특정 열(Column)에 `NaN` (Not a Number) 값이 있는 행(Row)을 어떻게 삭제하는지에 대해 설명합니다. `NaN`은 결측값을 의미하며, 이를 제거하는 것은 데이터 분석에 있어 중요한 단계 중 하나입니다.

## dropna 메소드 사용하기

### 메소드 개요
`dropna` 메소드는 Pandas DataFrame에서 `NaN` 값이 있는 행을 삭제하는 데 사용됩니다. 이 메소드는 다양한 파라미터를 가지고 있어, 여러 가지 상황에 적용할 수 있습니다.

### 기본 사용법
```python
import pandas as pd

# DataFrame 생성
df = pd.DataFrame({'A': [1, 2, np.nan, 4], 'B': [5, np.nan, 7, 8]})

# 'A' 열에서 NaN 값을 가진 행을 삭제
df.dropna(subset=['A'], inplace=True)
```

이 코드를 실행하면 'A' 열에서 `NaN` 값이 있는 행은 삭제됩니다. `inplace=True` 파라미터는 원본 DataFrame을 직접 수정하라는 의미입니다.

### 주의사항
- `inplace=True`를 사용하면 원본 DataFrame이 변경됩니다. 원본 데이터를 유지하려면 `inplace=False`를 사용하고 결과를 새 변수에 저장하세요.

## DataFrame에서 다수의 열을 대상으로 삭제하기

복수의 열에서 `NaN` 값이 있는 행을 삭제하려면 `subset` 파라미터에 열 이름을 리스트로 전달합니다.

```python
# 'A'와 'B' 열에서 NaN 값을 가진 행을 삭제
df.dropna(subset=['A', 'B'], inplace=True)
```

## 결론

Pandas의 `dropna` 메소드를 이용하면 특정 열에 `NaN` 값이 있는 행을 쉽게 삭제할 수 있습니다. 이 기능은 데이터 전처리 과정에서 자주 사용되며, DataFrame을 더욱 깔끔하게 만들어 줍니다. 이를 통해 더 정확한 데이터 분석이 가능해집니다.