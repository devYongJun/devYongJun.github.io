---
title: Python 개발환경 설정 (M1 Mac)
author: Yongjun
date: 2021-06-21 00:00:00 +0900
categories: [language, python]
tags: [m1, mac, python]
---


### Homebrew 설치

```bash
# 설치
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 버전 확인
brew -v
```

### 파이썬3 설치
```bash
brew install python3
python3 -V
```

### 가상환경 생성 
```bash
python3 -m venv myenv
```
**myenv 부분은 본인이 원하는 가상환경의 이름*

### 가상환경 활성화
```bash
cd myenv
source bin/activate
```

### 가상환경 비활성화
```bash
deactivate
```

### 장고 설치
```bash
python -m pip install Django
```
**가상 환경 활성화 상태에서 설치*

### 장고 프로젝트 생성
```bash
django-admin startproject myproj
```
**myproj 부분은 본인이 원하는 프로젝트 이름*

### 장고 서버 실행
```bash
cd myproj
python manage.py runserver
```