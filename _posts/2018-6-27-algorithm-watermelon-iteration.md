---
layout: post
title: 프로그래머스 수박수박수박수박수박수 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 "수박수박수박수박수박수?" 라는 알고리즘 문제를 풀어보았습니다.

## 문제 설명

길이가 n이고, 수박수박수박수....와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 

예를들어 n이 4이면 수박수박을 리턴하고 3이라면 수박수를 리턴하면 됩니다.

## 제한 조건

* n은 길이 10,000이하인 자연수입니다.

## 입출력 예

n : 3 / 4
return : 수박수 / 수박수박

## 코드

```c++
#include <string>
#include <vector>

using namespace std;

string solution(int n) {
    string answer = "";
    for(int i=0;i<n;i++)
    {
        if(i%2==0)
        {
            answer += "수";
        }
        else
        {
            answer += "박";
        }
    }
    return answer;
}
```

for문으로 반복하면서 문자열에 짝수면 수를 넣고, 홀수면 박을 널습니다.

반복이 끝나면 누적된 문자열을 반환합니다.