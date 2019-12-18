---
layout: post
title: 파이썬 의존성 관리자 Poetry 알아보기
---

오늘은 최근 1.0.0 버전이 출시된 파이썬의 의존성 관리자 Poetry에 대하여 알아봅니다.

## 개요

Python 프로젝트의 종속성을 관리할 수 있게 도와주는 의존성 관리자 Poetry 입니다.

기존 pip의 requirements.txt 파일로 관리할 때 나타나는 단점을 보안하고, virtualenv를 같이 쓸 수 있습니다.

## 설치

```sh
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
```

curl로 스크립트 코드를 받아서 poetry를 설치합니다.

```sh
export PATH="$HOME/.poetry/bin:$PATH"
```

쉘에 환경변수를 저장합니다.

```sh
exec "$SHELL"
```

쉘을 재시작합니다.

## 자동 완성

poetry의 자동완성 기능을 위해서 각자의 시스템과 쉘에 맞게 수행합니다.

```sh
poetry completions bash > /etc/bash_completion.d/poetry.bash-completion
```

만약 bash를 사용하면 위 명령어를 수행합니다.

```sh
poetry completions bash > $(brew --prefix)/etc/bash_completion.d/poetry.bash-completion
```

만약 맥에서 bash를 사용하면 위 명령어를 수행합니다.

```sh
poetry completions zsh > $(brew --prefix)/share/zsh/site-functions/_poetry
```

만약 맥에서 zsh를 사용하면 위 명령어를 수행합니다.

## 업그레이드

```sh
poetry self update
```

poetry 버전을 올릴 수 있습니다.

## 제거 

```sh
POETRY_UNINSTALL=1 bash -c 'curl -sSL https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python'
```

시스템에서 poetry를 제거할 수 있습니다.

## 예제

```sh
poetry new new_project  
```

새로운 프로젝트를 만듭니다.

```toml
[tool.poetry]
name = "new_project"
version = "0.1.0"
description = ""
authors = ["user <user@example.com>"]

[tool.poetry.dependencies]
python = "^3.7"

[tool.poetry.dev-dependencies]
pytest = "^4.6"

[build-system]
requires = ["poetry>=0.12"]
build-backend = "poetry.masonry.api"
```

새로운 프로젝트를 만들면 해당 프로젝트 폴더에서 pyproject.toml를 확인할 수 있습니다.

```sh
cd new_project

poetry install
```

해당 프로젝트 폴더에 접근한 뒤에 프로젝트의 의존성을 설치할 수 있습니다.

또는 설치할 때 --no-dev 옵션으로 개발 의존성은 설치하지 않을 수 있습니다.

## 커맨드 

* poetry update $package

* poetry add $package

* poetry remove $package

의존성 패키지들을 업데이트하거나 추가/제거할 수 있습니다.

* poetry show

의존성 패키지들의 자세한 내용을 볼 수 있습니다.

* poetry build

* poetry publish

wheels로 빌드하거나 pypi에 배포할 수 있습니다.

https://python-poetry.org/docs/cli/

그 외 위 링크에서 모든 cli 명령을 볼 수 있습니다.