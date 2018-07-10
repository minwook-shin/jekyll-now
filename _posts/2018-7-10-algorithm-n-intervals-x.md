---
layout: post
title: 프로그래머스 x만큼 간격이 있는 n개의 숫자 알고리즘 문제 풀기
---

오늘은 이름이 긴 알고리즘 문제인 "x만큼 간격이 있는 n개의 숫자"를 풀어보겠습니다.

## 문제 설명

함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 

## 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.

## 제한 조건

* x는 -10000000 이상, 10000000 이하인 정수입니다.
* n은 1000 이하인 자연수입니다.

## 입출력 예

x : 2, 4, -4	

n : 5, 3, 2	

answer : [2,4,6,8,10], [4,8,12], [-4, -8]

## 코드 

```c++
#include <string>
#include <vector>

using namespace std;

vector<long long> solution(int x, int n) {
    long long tmp = 0;
    vector<long long> answer;
    for(int i=0;i<n;i++)
    {
        tmp += x;
        answer.push_back(tmp);
    }
    return answer;
}
```

n개까지 반복하는 for문을 작성하고, 그 안에서 x를 누적하여 더한 값을 정답 배열에 추가해줍니다.

for문을 끝낸 정답 배열을 반환해줍니다.