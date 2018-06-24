---
layout: post
title: 프로그래머스 문자열 다루기 기본 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 "문자열 다루기 기본" 라는 알고리즘 문제를 풀어보았습니다.

## 문제 설명

문자열 s의 길이가 4혹은 6이고, 숫자로만 구성되있는지 확인해주는 함수, solution을 완성하세요.

예를들어 s가 a234이면 False를 리턴하고 1234라면 True를 리턴하면 됩니다.

## 제한 사항

* s는 길이 1 이상, 길이 8 이하인 문자열입니다.

## 입출력 예

s : a234 / 1234

return : false / true

## 코드

```c++
bool solution(string s) {
    bool answer = true;
    if(s.length() == 4||s.length() == 6)
    {
        for(int i =0;i<s.length();i++)
        {
            if(s[i]!='0'&&s[i]!='1'&&s[i]!='2'&&s[i]!='3'&&s[i]!='4'&&s[i]!='5'&&s[i]!='6'&&s[i]!='7'&&s[i]!='8'&&s[i]!='9')
            {
                goto f;
            }
        }
        return true;
    }
    f:
    return false;
}
```

문자열의 길이가 4이거나 6인 경우를 if문으로 거르고, 문자열 처음부터 끝까지 탐색하면서 0부터 9가 아니면 바로 하단의 return false로 점프합니다.

for문을 무사히 통과했다는 뜻은 전부 숫자로만 구성되어 있으므로, true를 반환합니다.

(goto문을 안쓰고 바로 return false로 해도 되지만, 호기심에 goto로 작성해보았습니다.)