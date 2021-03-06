---
layout: post
title: 우분투 18.04에서 달라진 주요 사항들을 알아보기
---

안녕하세요. 오늘은 우분투 18.04가 정식 출시되기 전에 파이널 베타로 알아보는 우분투 18.04의 달라진 점들을 알아보고자 합니다.

아래에 소개되는 새로운 점이라는 기준은 16.04 LTS라는 점을 유의해주시기 바랍니다.

대부분의 기능은 지난 17.04 ~ 17.10 에서 많이 나왔기 때문입니다.

## LTS

우선 이번 버전은 장기지원버전으로서, LTS 버전입니다.

## Gnome

오랜 시간동안 사용했던 unity를 버리고 이번 LTS 최초로 Gnome이 적용된 버전입니다.

버전은 3.28입니다.

gnome 셀에서 썬더볼트3를 지원합니다.

## 커널

리눅스 커널 4.15가 탑재됩니다.

## 파이썬

파이썬2가 이제 기본적으로 설치되지 않습니다.

파이썬3는 3.6으로 업데이트되었습니다.

## 리브레 오피스

기본 탑재되는 리브레 오피스의 버전이 6.0입니다.

## gpg

gpg가 gnupg2로 기본 설치 됩니다.

## 디스플레이 매니저

이제 LightDM을 사용합니다.

## gconf

이제 gconf는 기본적으로 설치되지 않습니다.

## X.org

X 서버가 아직 유지되면서 웨이랜드는 20.04 LTS 때 적용된다고 합니다.

## 네트워크

기본적으로 ifupdown가 사라집니다.

다만 main 저장소에서 계속 지원은 한다고 합니다.

## swap

이제 새로 설치한 경우에는 스왑 파티션 대신 스왑 파일이 생성됩니다.

## 최소 설치

우분투 데스크톱 설치 시, 최소 설치 옵션이 생겼습니다.

기본적인 웹 브라우저와 기타 유틸리티만 설치됩니다.

## 이모지

컬러 이모지가 지원됩니다.

## Snap

우분투 소프트웨어에서 Snap 앱들을 기본적으로 지원하며, 시스템에 탑재된 일부 유틸리티들이 snap으로 이루어졌습니다.

## 기본 설치

ToDo 앱이 기본 설치에 포함됩니다.

## 터치 패드

두 손가락 클릭이라는 옵션이 생겼으며, synaptics 드라이버를 사용할 수 있습니다.

## 전원

배터리 전원으로 켜져있는 상태에서 20분 동안 사용하지 않으면 컴퓨터가 자동으로 일시 중지됩니다.

## 설치 이미지

이제 32비트 설치 이미지는 제작되지 않습니다.

## 창 버튼

창 제어 버튼이 오른쪽으로 옮겼습니다.

## 프린터

Driverless printing support이 되어서 드라이버 없이 프린터를 작동시킬 수 있습니다.