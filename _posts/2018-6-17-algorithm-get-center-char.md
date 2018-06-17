---
layout: post
title: 프로그래머스 가운데 글자 가져오기 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 "가운데 글자 가져오기"이라는 알고리즘 문제를 풀어보았습니다.

## 문제 설명

단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

## 재한사항

s는 길이가 1 이상, 100이하인 스트링입니다.

## 입출력 예

s :	"abcde", "qwer"

return :"c", "we"

## 코드

```python
def solution(s):
    if(int(len(s)) %2 != 0):
        answer = s[int(len(s)/2)]
    else:
        answer = s[int(len(s)/2)-1]
        answer += s[int(len(s)/2)]
    return answer
```

이번에는 저번과 달리 파이썬으로 간단하게 짝수와 홀수로 나누고, 
홀수면 가운데 한자리만 반환하고 짝수면 가운데의 전 글자와 그 다음 글자를 이어붙혀서 반환합니다.