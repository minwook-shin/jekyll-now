---
layout: post
title: 프로그래머스 문자열을 정수로 바꾸기 알고리즘 문제 풀기
---

오늘은 코드로 몇 줄도 안되는 문제 "문자열을 정수로 바꾸기"를 간단하게 풀어봅니다.

## 문제 설명

문자열 s를 숫자로 변환한 결과를 반환하는 함수, solution을 완성하세요.

## 제한 조건

* s의 길이는 1 이상 10,000이하입니다.

* s의 맨앞에는 부호(+, -)가 올 수 있습니다.

* s는 부호와 숫자로만 이루어져있습니다.

* s는 0으로 시작하지 않습니다.

## 입출력 예

예를들어 str이 1234이면 1234를 반환하고, -1234이면 -1234를 반환하면 됩니다.

str은 부호(+,-)와 숫자로만 구성되어 있고, 잘못된 값이 입력되는 경우는 없습니다.

## 코드

```c++
#include <string>
#include <vector>
#include <stdlib.h>

using namespace std;

int solution(string s) {
    int answer = stoi(s);;
    return answer;
}
```

정말 간단하게 stoi를 써서 string을 int형으로 바꾸어 보았습니다.