---
title: Python 3에서 ImportError attempted relative import with no known parent package 해결하기
date: 2023-08-18 20:00:00 +0900
categories:
  - python
tags:
  - 파이썬에러
---

## 문제 상황 

Python 3에서 상대 임포트를 사용할 때 자주 발생하는 문제 중 하나는 `ImportError: attempted relative import with no known parent package` 오류입니다. 이 오류는 모듈이나 패키지를 임포트하려고 할 때 Python이 부모 패키지를 찾지 못해 발생합니다.

## 상대 임포트와 절대 임포트

먼저, 상대 임포트(relative import)와 절대 임포트(absolute import)에 대해 알아보겠습니다. 상대 임포트는 같은 패키지 내의 다른 모듈을 임포트할 때 사용되고, 절대 임포트는 패키지의 전체 경로를 지정하여 모듈을 임포트할 때 사용됩니다.

- **상대 임포트 예시**: `from . import my_module`
- **절대 임포트 예시**: `import my_package.my_module`

## 해결 방법 1: `__init__.py` 파일 생성

파이썬에서는 디렉터리에 `__init__.py` 파일이 있으면 그 디렉터리를 패키지로 인식합니다. 따라서 상대 임포트가 필요한 디렉터리에 `__init__.py` 파일을 생성하면 이 문제를 해결할 수 있습니다.

## 해결 방법 2: 메인 스크립트 위치

메인 스크립트(프로그램의 시작점)이 패키지 외부에 있을 경우 상대 임포트가 작동하지 않습니다. 메인 스크립트를 패키지 내부로 옮겨보세요.

## 해결 방법 3: `-m` 옵션 사용

Python 명령어에 `-m` 옵션을 추가하여 모듈을 실행하면 상대 임포트 문제를 해결할 수 있습니다.

```bash
python -m my_package.my_module
```

## 해결 방법 4: `sys.path` 수정

`sys.path`는 Python이 모듈을 찾는 경로를 담고 있는 리스트입니다. 이 리스트를 수정하여 상대 임포트가 가능한 경로를 추가할 수 있습니다.

```python
import sys
sys.path.append('/path/to/your/package')
```

이러한 방법들을 통해 Python 3에서 `ImportError: attempted relative import with no known parent package` 오류를 효과적으로 해결할 수 있습니다. 이 정보가 여러분의 코딩 과정에서 도움이 되길 바랍니다.