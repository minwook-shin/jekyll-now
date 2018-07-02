---
layout: post
title: 프로그래머스 정수 내림차순으로 배치하기 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 정수 내림차순으로 배치하기 알고리즘 문제를 풀어보려 합니다.

## 문제 설명

함수 solution은 정수 n을 매개변수로 입력받습니다. 

n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 

예를들어 n이 118372면 873211을 리턴하면 됩니다.

## 제한 조건

* n은 1이상 8000000000 이하인 자연수입니다.

## 입출력 예

n : 118372

return :873211

## 코드

```python
def solution(n):
    strn = str(n)
    l =[]
    for i in strn:
        l.append(i)
    l.sort(reverse=True)
    answer =''
    for i in l:
        answer += i
    return int(answer)
}
```

리스트에 문자열로 변환된 수를 넣어주고, 정렬을 reverse로 하면 바로 정수를 내림차순으로 배치할 수 있습니다.

출력이 정수이기 때문에 문자열로 이어 붙이다가 반환할때 int로 변환해줍니다.