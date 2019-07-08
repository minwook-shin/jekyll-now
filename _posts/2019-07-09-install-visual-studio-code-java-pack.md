---
layout: post
title: Visual Studio Code Java Pack 설치해보기
---

오늘은 마이크로소프트에서 만든 비주얼스튜디오 코드 Java팩 인스톨러를 소개해보려 합니다.

## 개요

Visual Studio Code Java Pack Installer는 JDK와 Visual Studio 코드를 감지하여 자바 개발 환경을 설치하고 설정해줍니다.

## 지원 운영체제

최초 버전은 윈도우만 지원하지만, 다음 릴리즈에는 맥도 지원된다고 합니다.

하지만, 리눅스는 사용자들이 자신의 개발 환경을 관리하는 것을 선호하므로 고려하지 않는다고 합니다.

> Q: is it or will be avilable for linux too?

> A: No, our next release will include a macOS version. According to our user study, most linux users prefer to manage their own dev environment. 

출처 : https://devblogs.microsoft.com/visualstudio/announcing-visual-studio-code-java-installer/

## 리눅스

https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack

리눅스는 Java Extension Pack을 직접 설치해야 합니다.

## 다운로드

https://aka.ms/vscode-java-installer-win

윈도우는 위 링크로 설치하며, 맥은 해당 포스트가 작성된 시점에서는 공개되지 않았으므로 나중에 포스트를 업데이트할 계획입니다.

https://code.visualstudio.com/docs/java/java-tutorial

만약, 포스트가 업데이트되지 않는다면 위 링크에서 "Download Visual Studio Code Java Pack Installer" 버튼을 찾아서 누르면 됩니다.

## 인스톨러 설치

처음 설치하면 라이선스 동의 화면이 나옵니다.

다음은 jdk와 비주얼 스튜디오 코드가 설치되었는지 확인되며, 만약 전부 없다면 jdk와 비주얼 스튜디오도 같이 설치됩니다.

모두 준비되어 있다면 비주얼스튜디오 코드의 자바 확장팩만 설치하고 설정하게 됩니다.

설치가 끝나고 vscode의 확장 프로그램 목록을 열면 자바 관련 확장팩들이 설치되어 있습니다.

## OpenJDK

OpenJDK 종류는 AdoptOpenJDK가 설치됩니다.

> AdoptOpenJDK: OpenJDK와 Hotspot(자바 머신)의 바이너리를 제공하는 배포판

## VS code

VS code에서 java 파일을 만들면 자바 확장팩이 활성화되면서 오버뷰 화면이 출력됩니다. 이때에 maven, spring boot 프로젝트를 시작할 수 있고, 각종 문서를 볼 수 있습니다. 

```java
public class hello {

    public static void main(String[] args) {
        // main
    }
}
```

class를 입력하고 ctrl+space로 자동완성이 되어 클래스가 생성되며, main을 입력하고 ctrl+space로 자동완성이 되어 메인 함수를 만들 수 있습니다.

```java
public class hello {

    public static void main(String[] args) {
        System.out.println("hello, world");
    }
}
```

이 때에 실행을 테스트하기 위해 System.out.println으로 문자열을 출력할 수 있습니다. 

메인함수에 나오는 run 텍스트를 클릭하면 해당 함수를 수행하게 됩니다.

```java
public class hello {

    public static void main(String[] args) {
        String x = "hello, world!";
        System.out.println(x);
    }
}
```

변수를 만들어서 브레이크 포인트를 설정하고 debug를 누르면 해당 포인터 이전으로 수행되면서 로컬 변수의 값을 볼 수 있고, 수정할 수도 있습니다.

## 프로젝트 생성

프로젝트 생성은 코드의 보기에서 명령 팔레트에 Java: Create Java Project를 입력하여 프로젝트의 위치와 이름을 지정하고 생성할 수 있습니다.

프로젝트의 하위폴더로 bin과 src 폴더가 생성되며, app이라는 패키지가 생성됩니다.

