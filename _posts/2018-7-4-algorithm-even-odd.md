---
layout: post
title: 프로그래머스 짝수와 홀수 알고리즘 문제 풀기
---

오늘은 간단하게 짝수와 홀수를 판별해보려 합니다.

## 문제 설명 

정수 num이 짝수일 경우 Even을 반환하고 홀수인 경우 Odd를 반환하는 함수, solution을 완성해주세요.

## 제한 조건

* num은 int 범위의 정수입니다.

* 0은 짝수입니다.

## 입출력 예

num :3 , 4
return : Odd , Even

## 코드

```c++
#include <string>
#include <vector>

using namespace std;

string solution(int num) {
    if(num%2==0)
    {
        return "Even";
    }
    return "Odd";
}
```


2로 나눈 나머지 값이 없으면 짝수, 있으면 홀수이므로 if문을 이용하여 문자열로 반환해줍니다.