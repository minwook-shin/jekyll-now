---
layout: post
title: 프로그래머스 자릿수 더하기 알고리즘 문제 풀기
---

오늘은 프로그래머스에서 자릿수 더하기 알고리즘 문제를 풀어보려 합니다.

## 문제 설명

자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.

예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

## 제한사항

N의 범위 : 100,000,000 이하의 자연수

## 입출력 예

* 9 + 8 + 7 = 24이므로 24를 return 하면 됩니다.

## 코드

```c++
#include <iostream>
#include <string>
#include <stdlib.h>

using namespace std;
int solution(int n)
{
    string n2 = to_string(n);
    int answer = 0;
    
    for(int i =0;i < n2.length();i++)
    {
        answer += n2[i]-'0';
    }

    // [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
    cout << "Hello Cpp" << endl;

    return answer;
}
```

숫자를 문자열로 변환하고, 문자열의 첫번째 자리부터 마지막 자리까지 for문으로 한 변수에 계속 더해줍니다.