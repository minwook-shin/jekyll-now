---
layout: post
title: 프로그래머스 문자열 내림차순으로 배치하기 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 "문자열 내 p와 y의 개수" 라는 알고리즘 문제를 풀어보았습니다.

## 문제 설명

문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.

s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.

## 제한 사항

* str은 길이 1 이상인 문자열입니다.

## 입출력 예

s : "Zbcdefg"

return : "gfedcbZ"

```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

string solution(string s) {
    vector<int> v;
    string answer = "";
    for(int i=0;i<s.length();i++)
    {
        v.push_back(s[i]);
    }
    sort(v.begin(),v.end());
    for(int i=s.length()-1;i >= 0;i--)
    {
        answer +=v[i];
    }
    return answer;
}
```

벡터에 한개씩 넣어주고, 알고리즘 헤더에 있는 sort 메소드를 사용합니다.

그리고 뒤쪽부터 차례대로 string에 다시 합쳐줍니다.