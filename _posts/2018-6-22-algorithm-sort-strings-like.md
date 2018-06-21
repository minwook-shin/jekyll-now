---
layout: post
title: 프로그래머스 문자열 내 마음대로 정렬하기 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 "문자열 내 마음대로 정렬하기" 라는 알고리즘 문제를 풀어보았습니다.

## 문제 설명

문자열로 구성된 리스트 strings와, 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬하려 합니다. 

예를 들어 strings가 [sun, bed, car]이고 n이 1이면 각 단어의 인덱스 1의 문자 u, e, a로 strings를 정렬합니다.

## 제한 조건

* strings는 길이 1 이상, 50이하인 배열입니다.
* strings의 원소는 소문자 알파벳으로 이루어져 있습니다.
* strings의 원소는 길이 1 이상, 100이하인 문자열입니다.
* 모든 strings의 원소의 길이는 n보다 큽니다.
* 인덱스 1의 문자가 같은 문자열이 여럿 일 경우, 사전순으로 앞선 문자열이 앞쪽에 위치합니다.

## 입출력 예

* sun, bed, car의 1번째 인덱스 값은 각각 u, e, a 입니다. 이를 기준으로 strings를 정렬하면 [car, bed, sun] 입니다.

* abce와 abcd, cdx의 2번째 인덱스 값은 c, c, x입니다. 따라서 정렬 후에는 cdx가 가장 뒤에 위치합니다. abce와 abcd는 사전순으로 정렬하면 abcd가 우선하므로, 답은 [abcd, abce, cdx] 입니다.

```c++
#include <string>
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

vector<string> solution(vector<string> strings, int n) {
    sort(strings.begin(),strings.end());
    string temp = "";
    for(int i =0;i<strings.size();i++)
    {
        for(int j =0;j<strings.size()-1;j++)
        {
            if(strings[j][n]>strings[j+1][n])
            {
                temp = strings[j];
                strings[j] = strings[j+1];
                strings[j+1] = temp;
            }
        }
    }
    return strings;
}
```

우선 알고리즘 헤더를 이용하여 정렬을 수행하고, 특정 인덱스만 비교하는 버블 정렬을 구현하여 자기 자신이 더 크면 다음 인덱스로 바꾸어 줍니다.

이중 for문을 수행하면 문제에서 원하는 출력이 나오게 됩니다.