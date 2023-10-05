---
title: Python에서 파일 이동하기 shutil 모듈 사용법
date: 2023-09-12 20:00:00 +0900
categories:
  - python
tags:
---
## shutil 라이브러리란 무엇인가?

`shutil`은 Python 표준 라이브러리 중 하나로, 파일과 디렉터리(폴더) 작업을 쉽게 수행할 수 있게 도와줍니다. 이 라이브러리는 파일을 복사하거나 이동하는 데 유용하며, 단 몇 줄의 코드로 복잡한 파일 작업을 수행할 수 있습니다.

## shutil.move 메서드를 이용한 파일 이동

`shutil.move` 메서드를 사용하면, 파일을 쉽게 한 위치에서 다른 위치로 이동할 수 있습니다. 이 메서드의 기본 구조는 아래와 같습니다.

```python
import shutil
shutil.move("원본_파일_경로", "목적지_파일_경로")
```

여기서 "원본_파일_경로"는 이동하려는 파일의 현재 위치를, "목적지_파일_경로"는 파일을 이동시키려는 새로운 위치를 나타냅니다.

### 예시 코드

```python
import shutil

# 파일을 /Users/your_username/folderA에서 /Users/your_username/folderB로 이동
shutil.move("/Users/your_username/folderA/sample.txt", "/Users/your_username/folderB/")
```

이 코드를 실행하면 `sample.txt`라는 파일이 `folderA`에서 `folderB`로 이동하게 됩니다.

## 주의사항과 에러 처리

`FileNotFoundError`라는 에러는 원본 파일이 존재하지 않을 때 발생합니다. 이 에러를 방지하기 위해 `os.path.exists` 메서드를 사용하여 파일의 존재 여부를 먼저 확인할 수 있습니다.

```python
import os

if os.path.exists("원본_파일_경로"):
    shutil.move("원본_파일_경로", "목적지_파일_경로")
else:
    print("원본 파일이 존재하지 않습니다.")
```

이렇게 하면 파일 이동 작업을 더 안전하게 수행할 수 있습니다.

## 결론

Python의 `shutil` 라이브러리를 이용하면 파일을 쉽고 효율적으로 이동할 수 있습니다. 원본 파일의 위치와 목적지의 위치만 정확하게 지정해주면, 복잡한 파일 작업도 몇 줄의 코드로 해결할 수 있습니다.