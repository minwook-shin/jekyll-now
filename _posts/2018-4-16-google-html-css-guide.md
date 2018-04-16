---
layout: post
title: 구글의 html과 css의 코딩 가이드 알아보기
---

오늘은 구글에서 제공하는 문서중에 html과 css에서 어떻게 코딩해야되는지 나와있는 문서를 간단히 요약해보겠습니다.

## https

HTTPS 프로토콜을 사용합니다.

```html
<script src="http://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
```

위와 같은 http는 권장하지 않으며

```html
 <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
```

위와 같이 인터넷에 연결되면 좋습니다.

```html
@import 'https://fonts.googleapis.com/css?family=Open+Sans';
```

import도 동일합니다.

## 들여쓰기

한번에 두칸씩 들여씁니다.

그리고 Tab과 혼용하여 사용하면 좋지 못합니다.

## 작명

소문자만 사용합니다.

html 요소와 속성, selector등에 적용됩니다.

```css
color: #E5E5E5;
```

위와 같이 대문자는 권장하지 않습니다.

```css
color: #e5e5e5;
```

## 필요없는 공백

코드 뒤에 존재하는 공백은 향후 diff 작업시 불편해질 수 있습니다.

## 인코딩

UTF-8 (no BOM)을 사용합니다.

## 주석

가능한 주석으로 코드를 설명하도록 노력해야 합니다.

코드가 무슨 행동을 하고, 어떤 목적에 있는지 설명합니다.

## TODO

TODO로 수행할 작업을 미리 지정할 수 있습니다.

```html
{# TODO(john.doe): revisit centering #} <center>Test</center>

<!-- TODO: remove optional tags --> <ul> <li>Apples</li> <li>Oranges</li> </ul>
```

위와 같이 할 일을 강조할 수 있습니다.

## html

* html5를 사용합니다.

* 닫을 필요가 없는 태그를 닫지 않습니다. (예 : <br/> 아니라 <br> ).

* 올바른 html 코드를 사용합니다.

* 적절한 요소를 사용하여 html 파일을 만듭니다.

* alt 속성으로 컨텐츠를 읽을 수 없는 사람들에게 대체 텍스트를 제공할 수 있어야 합니다.

* 스타일시트와 자바스크립트는 가능한 적게 연결합니다.

* 보이지 않는 문자(<.&)를 제외하고는 가능한 엔티티를 사용하지 않습니다.

* html5에서는 스타일시트와 자바스크립트는 자동으로 타입 속성을 정해주므로, 이 속성을 생략해도 됩니다.

```html
<!-- Recommended --> <link rel="stylesheet" href="https://www.google.com/css/maia.css">
```

* 모든 블록과 목록 그리고 표는 새로운 행을 사용하고, 모든 요소를 들여쓰기합니다.

* 속성 값을 대입할 때는 이중 따움표를 사용합니다.

## CSS

* 유효한 css 코드를 사용합니다.

* 의미있는 id나 클래스 명을 사용합니다.

* 의미있지만 가능한 짧게 id나 클래스 명을 사용합니다.

* 타입 selector로 id나 클래스 이름을 한정하지 않습니다.

```css
/* Not recommended */ ul#example {} div.error {}

/* Recommended */ #example {} .error {}
```

* 가능한 단축 속성을 사용합니다.

```css
/* Not recommended */ border-top-style: none; font-family: palatino, georgia, serif; font-size: 100%; line-height: 1.6; padding-bottom: 2em; padding-left: 1em; padding-right: 1em; padding-top: 0;

/* Recommended */ border-top: 0; font: 100%/1.6 palatino, georgia, serif; padding: 0 1em 2em;
```

* 값이 0 이라면 0 뒤에 값을 입력하지 않습니다.

* id와 클래스 명의 단어 구분은 하이픈으로 이루어집니다.

* 모든 블록은 들여쓰기를 합니다.

* 모든 속성의 선언은 항상 세미콜론을 붙이고 끝냅니다.

* 속성과 값 사이에는 공백이 하나 들어갑니다.

* selector와 블록 사이에도 공백이 하나 들어갑니다.

* 새로운 css 규칙은 새로운 두줄로 구분합니다.

* css의 속성에 값을 대입하려면 단일 따움표를 사용합니다.

## 참고 문서

https://google.github.io/styleguide/htmlcssguide.html