---
layout: post
title: 리눅스 커널 4.18에서 달라진 점 알아보고 적용해보기
---

오늘은 최근에 출시한 리눅스 커널 4.18에서 달라진 점을 알아보고, 우분투에 적용하는 방법을 알아보려 합니다.

## 달라진 점

1. V3D DRM 드라이버 mainlined

1. NVIDIA Volta GV100 / Vega M 그래픽 하드웨어 초기 지원

1. Qualcomm Snapdragon 845 지원 / AMD GPU 지원 개선

1. Speck 파일 시스템 암호화 지원

1. 다양한 USB Type-C / Thunderbolt 개선

1. KVM 마이크로소프트 Hyper-V 개선

1. Lustre 파일 시스템 제거

1. CPUfreq의 성능 최적화

1. AMD Stoney Ridge / Bristol Ridge APU의 온도 리포트

1. 태블릿과 클램쉘 모드 이동을 위한 크롬북 스위치 드라이버

1. 비동기 I/O 위한 커널 폴링 인터페이스

1. 2038년 문제를 해결하기 위한 노력 

달라진 점을 참고하기 위해 [해당 홈페이지](https://www.omgubuntu.co.uk/2018/08/linux-4-18-kernel-release-features)를 참고하였습니다.

## 2038년 문제란?

POSIX 시간 표기법을 이용하는 유닉스 계열의 프로그램에서 생기는 문제로, 
32비트 운영체제에서 시간을 저장하는 데 이용되는 time_t 타입이 1970년 1월 1일을 기점으로 2147483647초가 지난 2038년 1월 19일에 시간이 멈추는 버그가 있다고 합니다.

## 커널 적용해보기

우선 작동되는 실기기에 커널을 임의로 적용하는 것은 운영체제에 위험할 수 있으므로 가상머신에서 적용하는 것을 추천합니다.

http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.18.5/

64비트 우분투 기준으로 위 주소에서 

* linux-headers-4.18.5-041805_4.18.5-041805.201808241320_all.deb

* linux-headers-4.18.5-041805-generic_4.18.5-041805.201808241320_amd64.deb

* linux-image-unsigned-4.18.5-041805-generic_4.18.5-041805.201808241320_amd64.deb

* linux-modules-4.18.5-041805-generic_4.18.5-041805.201808241320_amd64.deb

이 파일들을 모두 설치하고 재부팅하면 적용됩니다.