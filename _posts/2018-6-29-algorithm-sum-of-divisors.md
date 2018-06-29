---
layout: post
title: 프로그래머스 약수의 합 알고리즘 문제 풀기
---

오늘도 어제와 같이 프로그래머스에서 "약수의 합"을 간단히 구해보겠습니다.

## 문제 설명

자연수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.

## 제한 사항

n은 0 이상 3000이하인 자연수입니다.

## 입출력 예

* 12의 약수는 1, 2, 3, 4, 6, 12입니다. 이를 모두 더하면 28입니다.

* 5의 약수는 1, 5입니다. 이를 모두 더하면 6입니다.

## 코드 

```c++
#include <string>
#include <vector>

using namespace std;

int solution(int n) {
    int answer = 0;
    for(int i=1; i<=n;i++)
    {
        if(n%i==0)
            answer += i;
    }
    return answer;
}
```

1부터 n까지 반복하면서 0으로 나누어 떨어지면 int형 변수에 더해줍니다.

끝나면 해당 변수를 반환합니다.