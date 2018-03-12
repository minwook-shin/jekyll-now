---
layout: post
title: 우분투의 새로운 테마 체험하기
---

우분투가 유니티에서 그놈으로 변경되면서 테마도 바뀐다고 합니다.

오늘은 이번 18.04에서 달라지는 그놈 테마를 다른 버전에서도 미리 설치해볼 수 있는 써보려합니다.

참고로 이 테마는 커뮤니티 주도 테마로서, 아직 우분투 18.04 데일리 빌드에서도 적용 안되어 있다고 합니다.

## 테마 범위

이 테마는 새로운 아이콘 세트와 향상된 그놈 쉘 테마, 그리고 GDM 로그인 테마까지 영향을 끼칩니다.

## 다운로드

https://github.com/Ubuntu/gnome-shell-communitheme 에서 내려받아서 설치할 수 있습니다.

위 저장소의 마스터 브랜치에서 커밋되면 다음날에 빌드로 사용할 수 있습니다.

GNU General Public License v2.0로 관리되고 있습니다.

## 설정하기 

우분투 17.04 이후의 배포판에 새 우분투 테마를 설치하려면 communitheme ppa를 소프트웨어 소스에 추가해야 하며,
이 ppa로 그놈 세션이 패키지화되어 관리됩니다.

```bash
# Add the PPA to your repository list
sudo add-apt-repository ppa:communitheme/ppa
# Download a list of all the software that's available from the repositories
sudo apt update
# Download and install the actual software
sudo apt install ubuntu-communitheme-session
```

설치가 완료되면, 로그아웃하고 로그인 화면에서 communitheme 세션을 선택하고 로그인해야 합니다.

다시 기본 테마로 돌아가고 싶다면, 로그아웃하고 우분투 기본 테마로 돌아갈 수 있습니다.

## 업데이트

소프트웨어 소스에 ppa가 추가되었다면 우분투를 업데이트하면서 자동으로 업데이트됩니다.

## 공식 적용 날짜

아직 새로운 테마가 우분투 18.04의 기본 테마로 된다는 확신은 없습니다.

다만, 우분투 커뮤니티측에서 열심히 개발하고 있을 뿐입니다.

## 주의점

깃허브 저장소 readme에 따르면 현재 pre-release alpha 상태이며 많은 아이콘이 누락되었다고 합니다. 