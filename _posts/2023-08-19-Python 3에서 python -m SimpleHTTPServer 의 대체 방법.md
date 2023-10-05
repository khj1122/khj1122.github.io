---
title: Python 3에서 python -m SimpleHTTPServer 의 대체 방법
date: 2023-08-19 20:00:00 +0900
categories:
  - python
tags:
---

## 서론

Python은 개발자에게 간편한 서버 환경을 제공하는 여러 모듈을 가지고 있습니다. Python 2에서는 `python -m SimpleHTTPServer` 명령어를 사용해 간단하게 HTTP 서버를 구동할 수 있었습니다. 하지만 Python 3에서는 이 방법이 바뀌었고, 그 대체 방법에 대해 알아보겠습니다.

## Python 2에서의 `SimpleHTTPServer`

Python 2에서는 다음과 같은 명령어를 통해 쉽게 HTTP 서버를 실행할 수 있었습니다.

```bash
python -m SimpleHTTPServer
```

이 명령어를 실행하면 현재 디렉터리를 기반으로 하는 HTTP 서버가 구동되고, 브라우저를 통해 파일을 접근할 수 있게 됩니다.

## Python 3에서의 대체 방법: `http.server`

Python 3에서는 `SimpleHTTPServer` 모듈이 없어졌고, `http.server` 모듈로 대체되었습니다. 이 모듈을 사용하기 위해서는 다음과 같은 명령어를 사용합니다.

```bash
python3 -m http.server
```

이 명령어는 Python 3.x 버전에서 동작하며, `SimpleHTTPServer`와 유사한 기능을 제공합니다. 디렉터리 구조를 기반으로 간단한 HTTP 서버를 구동시키고, 기본적으로 8000 포트를 사용합니다.

## 포트 지정하기

포트는 인터넷 연결을 위한 문 같은 것입니다. 기본 포트 외에 다른 포트를 사용하고 싶다면 명령어 뒤에 포트 번호를 추가할 수 있습니다.

```bash
python3 -m http.server 8080
```

이렇게 하면 8080 포트에서 HTTP 서버가 구동됩니다.

## 결론

Python 3에서는 `http.server` 모듈을 사용하여 Python 2의 `SimpleHTTPServer`와 유사한 기능을 쉽게 이용할 수 있습니다. 이를 통해 개발자는 빠르고 간편하게 HTTP 서버를 구성할 수 있으며, 다양한 포트 옵션을 통해 유연한 서버 운용이 가능합니다.