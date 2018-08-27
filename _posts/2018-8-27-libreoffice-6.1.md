---
layout: post
title: 리브레 오피스 6.1의 새로운 점 알아보기
---

오늘은 우분투에 기본 탑제되어 있는 리브레 오피스의 새로운 버전인 6.1에서 달라진 점을 알아보고자 합니다.

물론 이 버전이 우분투에 탑제되려면 다음 배포판까지 기다려야겠지만, ppa 추가로 미리 즐길 수도 있습니다.

## 변경점

1. 새로운 아이콘 팩

2. 새로운 앱 아이콘

3. 이미지 처리 개선

4. 노트북 바의 개선

5. 크게 개선 된 EPUB 내보내기

6. LibreOffice 문서 페이지 번호 개선

7. 툴바 및 최상위 메뉴를 사용자 정의 가능

8. 새로운 채우기 배경, 그라디언트

9. Excel 2003 XML 가져 오기 개선

10. DOCX 내보내기 / 가져 오기

11. 장 번호 매기기 스타일 추가

12. 그리기 메뉴 재구성

13. 새로운 기본 그라디언트 세트

14. 시그니처 라인 생성 추가

15. Linux에서 사용되는 GTK3 대화 상자 창 개선

16. 온라인 도움말 개선

변경점은 [해당 사이트](https://www.omgubuntu.co.uk/2018/08/libreoffice-6-1-release-download)의 글을 인용하여 작성하였습니다.

전체 릴리즈 노트는 https://wiki.documentfoundation.org/ReleaseNotes/6.1 에서 확인할 수 있습니다.

## 다운로드

https://www.libreoffice.org/download/download/

## 리브레 오피스 6.1 설치해보기

직접 다운로드 받지 않아도 간단하게 스냅과 Flatpak으로도 설치할 수 있습니다.

```
snap install libreoffice
```

or

```
 flatpak install flathub org.libreoffice.LibreOffice 
```

하지만, 스냅 패키지는 (한국어를 포함한) 영어 외의 언어는 입력기 권한(?) 상의 문제로 입력되지 않는다고 합니다.

기존의 ppa를 등록하고 내려받는 방식으로도 6.1 버전을 체험할 수 있습니다.

```
sudo add-apt-repository ppa:libreoffice/ppa
sudo apt-get update
sudo apt-get install libreoffice
```

## 우분투 18.10

우분투 18.10에서는 리브레 오피스 6.1이 기본적으로 탑제되어 있으므로 따로 내려받을 필요는 없습니다.