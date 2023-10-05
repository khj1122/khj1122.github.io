---
title: Matplotlib에서 범례를 그래프 밖에 위치시키는 방법
date: 2023-08-22 20:00:00 +0900
categories:
  - python
tags:
  - Matplotlib
---

## 문제 상황: 범례(legend)가 그래프와 겹침

Matplotlib를 사용하여 데이터를 시각화할 때, 범례(legend)가 그래프 내부에 위치하게 되면 그래프의 데이터를 제대로 확인하기 어려울 수 있습니다. 여러분이 이 문제에 부딪혔다면, 아래에 소개된 해결책을 적용해보세요.

## 해결책 1: `bbox_to_anchor` 속성 사용

`bbox_to_anchor`는 범례의 위치를 조절하는 속성입니다. 이 속성은 x와 y 좌표를 튜플 형태로 받아 범례의 위치를 이동시킵니다.

```python
import matplotlib.pyplot as plt

plt.plot([0, 1, 2], [0, 1, 4], label='Line A')
plt.plot([0, 1, 2], [0, 2, 3], label='Line B')

plt.legend(loc='upper left', bbox_to_anchor=(1, 1))
plt.show()
```

## 해결책 2: `subplots_adjust` 함수와 함께 사용

`subplots_adjust` 함수는 그래프의 여백을 조절합니다. 이 함수와 `bbox_to_anchor`를 함께 사용하면, 더 정확하게 범례의 위치를 설정할 수 있습니다.

```python
import matplotlib.pyplot as plt

plt.plot([0, 1, 2], [0, 1, 4], label='Line A')
plt.plot([0, 1, 2], [0, 2, 3], label='Line B')

plt.subplots_adjust(right=0.7)
plt.legend(loc='upper left', bbox_to_anchor=(1, 1))
plt.show()
```

## 해결책 3: `ncol` 속성으로 열 개수 조절

범례가 여러 개일 경우, `ncol` 속성을 사용하여 범례의 열 개수를 조절할 수 있습니다. 이는 범례가 너무 길어져서 그래프 밖으로 나가는 것을 방지합니다.

```python
import matplotlib.pyplot as plt

plt.plot([0, 1, 2], [0, 1, 4], label='Line A')
plt.plot([0, 1, 2], [0, 2, 3], label='Line B')

plt.legend(loc='upper left', bbox_to_anchor=(1, 1), ncol=2)
plt.show()
```

이러한 방법들을 통해 Matplotlib에서 범례의 위치를 적절하게 조절할 수 있습니다. 이제 여러분의 그래프는 더 깔끔하고 정보 전달이 효율적이게 될 것입니다.