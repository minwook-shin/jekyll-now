---
layout: post
title: 프로그래머스 제일 작은 수 제거하기 알고리즘 문제 풀기
---

오늘도 평소와 같이 "제일 작은 수 제거하기" 문제를 풀어보겠습니다.

## 문제 설명

정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 

단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 

예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.

## 제한 조건

* arr은 길이 1 이상인 배열입니다.
* 인덱스 i, j에 대해 i ≠ j이면 arr[i] ≠ arr[j] 입니다.

## 입출력 예

[4,3,2,1] -> [4,3,2]

[10] -> [-1]

## 코드 

```c++
#include <string>
#include <vector>

using namespace std;

vector<int> solution(vector<int> arr) {
    vector<int> answer;
    int min=arr[0];
    for(int i=0;i<arr.size();i++)
    {
        if(min > arr[i])
        {
            min = arr[i];
        }
    }
    for(int i=0;i<arr.size();i++)
    {
        if(min == arr[i])
        {
            arr.erase(arr.begin()+i);
        }
    }
    if(arr.empty())
    {
        arr.push_back(-1);
    }
    return arr;
}
```

가장 작은 수를 0번째 인덱스라고 정의하고, for문으로 작은 수를 먼저 찾습니다.

찾은 작은 수를 가지고, 다시 for문으로 돌려서 같은 수를 찾는다면, 배열에서 지워줍니다.

마무리로 만약 작은 수를 지웠더니 빈 배열로 바뀐다면 -1을 넣어주고 해당 배열을 반환합니다.