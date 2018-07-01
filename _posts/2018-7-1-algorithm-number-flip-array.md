---
layout: post
title: 프로그래머스 자연수 뒤집어 배열로 만들기 알고리즘 문제 풀기
---

오늘은 프로그래머스에서 "자연수 뒤집어 배열로 만들기" 알고리즘 문제를 풀어보려 합니다.

## 문제 설명

자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

## 제한 조건

n은 10,000,000,000이하인 자연수입니다.

## 입출력 예

* n : 12345

* return : [5,4,3,2,1]

## 코드 

```c++
#include <string>
#include <vector>
#include <string>

using namespace std;

vector<int> solution(long long n) {
    vector<int> answer;
    string tmp = to_string(n);
    for(int i=tmp.length()-1;i>=0;i--)
    {
        answer.push_back(tmp[i]-48);
    }
    
    return answer;
}
```

자연수를 문자열로 변환해주고, 맨 뒤에서 앞으로 읽어가면서 배열에 넣어줍니다.

넣어주면서 숫자로 변환하기 위해 ascii 코드에서 48을 뺀 값을 넣어줍니다.
