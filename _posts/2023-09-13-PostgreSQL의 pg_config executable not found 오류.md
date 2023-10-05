---
title: PostgreSQL의 pg_config executable not found 오류
date: 2023-09-13 20:00:00 +0900
categories:
  - python
tags:
  - PostgreSQL
---

## 오류 설명

'pg_config executable not found'는 PostgreSQL 데이터베이스와 연동할 때 자주 마주치는 오류 중 하나입니다. 이 오류가 발생하는 주된 이유는 시스템이 `pg_config` 파일을 찾을 수 없기 때문입니다. 이 파일은 PostgreSQL의 설정 정보를 관리하며, 특정 라이브러리나 어플리케이션은 이 파일을 필요로 합니다.

## 해결방법 1: 패키지 설치

첫 번째 해결 방법은 누락된 패키지를 설치하는 것입니다. PostgreSQL 개발 라이브러리를 설치해야 합니다.

### Ubuntu/Debian 환경

```bash
sudo apt-get install libpq-dev
```

### CentOS/RHEL 환경

```bash
sudo yum install postgresql-devel
```

## 해결방법 2: 환경 변수 설정

두 번째 방법은 `pg_config`의 경로를 직접 설정하는 것입니다. 터미널을 열고 다음 명령어를 실행하세요.

```bash
export PATH=$PATH:/usr/pgsql-<version>/bin
```

여기서 `<version>`은 설치된 PostgreSQL의 버전을 나타냅니다.

## 해결방법 3: 경로 확인 후 수동 설정

세 번째 방법은 `pg_config` 파일의 실제 위치를 찾은 다음, 해당 경로를 명령어에 직접 입력하는 것입니다.

```bash
which pg_config
```

이 명령어로 경로를 확인한 뒤, 이 경로를 사용하여 누락된 설정을 수동으로 완성할 수 있습니다.

## 요약

'pg_config executable not found' 오류는 주로 `pg_config` 파일이 없거나 시스템이 이를 찾지 못할 때 발생합니다. 이를 해결하기 위해 필요한 패키지를 설치하거나 환경 변수를 설정하면 대부분의 경우 해결할 수 있습니다. 이러한 방법들은 대체로 효과적이므로, 오류를 마주친다면 위의 방법 중 하나를 시도해 보세요.