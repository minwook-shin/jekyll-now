---
layout: post
title: HTML의 윈도우&브라우저 객체에 대하여 알아보기 1
---

오늘은 HTML에서 윈도우와 브라우저 관련한 객체에 대하여 간단히 알아보려고 합니다.

## bom

html 페이지의 내용과 관계없이 자바스크립트로 브라우저를 제어하기 위하여 지원되는 객체입니다.

bom은 w3c의 국제 표준이 없어서 브라우저마다 객체들이 조금씩 다르며, 이름이 같아도 속성과 메소드가 상이할 수도 있습니다.

* window – 브라우저의 윈도우 모양을 제어합니다. 새 window의 열고 닫는 작업이 포함됩니다.

* navigator – 브라우저에 대한 다양한 정보를 제공합니다.

* history - 브라우저 윈도우에 불러온 URL 리스트의 기록을 관리합니다.

* location – 브라우저 윈도우에 불러온 html 페이지의 URL을 관리합니다.

* screen – 브라우저가 실행되고 있는 스크린 장치에 대한 정보를 제공합니다.

## window 객체

열려 있는 브라우저 윈도우나 탭 윈도우의 속성을 나타내는 객체입니다.

윈도우마다 한 개의 윈도우 객체가 생성됩니다.

윈도우 객체가 생성되는 경우는 총 3가지가 있습니다.

1. 브라우저가 새로운 웹 페이지를 불러올 때에 윈도우 객체를 자동적으로 생성하는 경우

1. ifreme 태그에 한 개의 윈도우 객체가 자동으로 생성하는 경우

1. 개발자가 임의의 자바스크립트 코드로 윈도우를 열 때마다 새로운 객체를 생성하도록 하는 경우

```javascript
window.open("URL", "name", "ect")
```

open으로 새로운 윈도우나 탭 윈도우를 열 수 있습니다.
체
자바스크립트로 윈도우 객체에 접근할 수 있는 방법더 3가지입니다.

1. window

1. window.self

1. self

이렇게 윈도우 객체에 접근할 수 있습니다.

> 다음 포스팅에서 계속됩니다.