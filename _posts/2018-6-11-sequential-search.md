---
layout: post
title: 순차 정렬에 대하여 알아보기
---

오늘은 검색 방법중 가장 단순하고 쉬운 방법인 순차 검색을 알아보고자 합니다.

## 개요

일렬로 되어있는 자료를 처음부터 마지막까지 순서대로 검색하는 평범한 방법의 정렬인 순차 검색은 선형 검색이라고도 합니다.

주로 배열이나 링크드리스트로 구현된 순차 자료구조에서 원하는 항목을 찾는 방법입니다.

순차 검색은 검색해야하는 자료의 양에 따라 효율이 달라지기 때문에 자료가 아주 많은 집합에서는 비효율적입니다.

정렬되지 않은 순차 자료구조에서는 첫번째 원소부터 마지막 원소까지 순서대로 키값을 찾아서 있다면 반환하고, 없으면 검색을 실패하고 종료합니다.

정렬된 순차 자료구조에서는 마지막 원소까지 찾을 필요 없이, 인덱스의 값이 찾는 키값보다 크면 원소가 없다고 판단하고 종료합니다.

## 알고리즘

```java
sequential(arr[],n,key){
    i<-0;
    while(i<n and arr[i]!=key)do{
        i<-i+1;
    }
    if (i<n) then {
        return i;
    }else{
        return -1;
    }
}
```

i번째 원소를 찾으려면 i번 비교해야 하므로 평균 비교횟수는 n+1/2이므로 시간 복잡도는 O(n)입니다.