---
layout: post
title: 프로그래머스 나누어 떨어지는 숫자 배열 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 "나누어 떨어지는 숫자 배열" 라는 알고리즘 문제를 풀어보았습니다.

## 문제 설명

array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.
divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

## 제한사항

* arr은 자연수를 담은 배열입니다.
* 정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.
* divisor는 자연수입니다.
* array는 길이 1 이상인 배열입니다.

## 입출력 예

* arr의 원소 중 5로 나누어 떨어지는 원소는 5와 10입니다. 따라서 [5, 10]을 리턴합니다.

* arr의 모든 원소는 1으로 나누어 떨어집니다. 원소를 오름차순으로 정렬해 [1, 2, 3, 36]을 리턴합니다.

* 3, 2, 6은 10으로 나누어 떨어지지 않습니다. 나누어 떨어지는 원소가 없으므로 [-1]을 리턴합니다.

## 코드

```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

vector<int> solution(vector<int> arr, int divisor) {
    vector<int> answer;
    for(int i=0;i<arr.size();i++)
    {
        if(arr[i]%divisor==0)
        {
            answer.push_back(arr[i]);
        }
    }
    sort(answer.begin(),answer.end());
    if(answer.empty()){
        answer.push_back(-1);
    }
    return answer;
}
```

두번째 인자로 들어오는 수로 나누었을 때에 나누어 떨어지면, 새로운 배열에 저장하고 정렬하면 됩니다.

정렬은 알고리즘 헤더에 있는 sort를 이용하여 백터의 처음부터 끝까지 정렬합니다.

만약 정답 벡터에 아무것도 없으면 -1을 넣어주고 반환합니다.