---
layout: post
title: 프로그래머스 서울에서 김서방 찾기 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 "서울에서 김서방 찾기" 라는 알고리즘 문제를 풀어보았습니다.

## 문제 설명

String형 배열 seoul의 element중 Kim의 위치 x를 찾아, 김서방은 x에 있다는 String을 반환하는 함수, solution을 완성하세요. seoul에 Kim은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.

## 제한 사항

* seoul은 길이 1 이상, 1000 이하인 배열입니다.

* seoul의 원소는 길이 1 이상, 20 이하인 문자열입니다.

* Kim은 반드시 seoul 안에 포함되어 있습니다.

## 입출력 예

seoul : [Jane, Kim]
return : 김서방은 1에 있다

## 코드

```c++
#include <string>
#include <vector>

using namespace std;

string solution(vector<string> seoul) {
    string answer = "";
    for(int i=0;i<seoul.size();i++)
    {
        if(seoul[i]=="Kim")
        {
            answer += "김서방은 ";
            answer += std::to_string(i);
            answer += "에 있다";
        }
    }
    return answer;
}
```

자바에서는 eqeuls를 써야하지만, c++에서는 그냥 == 연산자로 해결했습니다.

해당 인덱스에 kim이 있다면, answer 문자열에 필요한 문자열들을 추가해서 반환값을 일치시킵니다.