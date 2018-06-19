---
layout: post
title: 프로그래머스 올바른 괄호 알고리즘 문제 풀기
---

오늘도 프로그래머스에서 "올바른 괄호" 라는 알고리즘 문제를 풀어보았습니다.

## 문제 설명

올바른 괄호란 두 개의 괄호 '(' 와 ')' 만으로 구성되어 있고, 괄호가 올바르게 짝지어진 문자열입니다. 괄호가 올바르게 짝지어졌다는 것은 '(' 문자로 열렸으면 반드시 짝지어서 ')' 문자로 닫혀야 합니다.

'(' 또는 ')' 로만 이루어진 문자열 s가 주어졌을 때, 문자열 s가 올바른 괄호이면 true를 return 하고, 올바르지 않은 괄호이면 false를 return하는 solution 함수를 완성해 주세요.

## 제한사항

* 문자열 s의 길이 : 100,000 이하의 자연수
* 문자열 s는 '(' 또는 ')' 로만 이루어져 있습니다.

## 입출력 예
* s : "()()", "(())()", ")()(", "(()(", "(()("
* answer : true, true , false, false

## 코드

```c++
#include<string>
#include <iostream>

using namespace std;

bool solution(string s)
{
    bool answer = true;
    int tmp = 0;
    for(int i =0;i< s.length();i++)
    {
        if(s[0]==')'&&s[s.length()]=='(')
        {
        return false;
        }
        if(s[i]=='(')
        {
            tmp ++;
        }
        else
        {
            tmp--;
            if(tmp<0)
            {
                return false;
            }
        }
    }
    
    if(tmp == 0){
        return true;
    }
    
    
    

    // [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
    cout << "Hello Cpp" << endl;

    return false;
}
```

처음과 끝이 ')'과 '('이면 false를 반환하고, '('를 세었을 때와 ')'를 세었을 때에 각 수가 일치해야자만 같은 괄호라고 true를 출력합니다.