---
layout: post
title: 기수 정렬에 대하여 알아보기
---

오늘은 기수 정렬에 대하여 작성해보고자 합니다.

## 개요

분배 방식의 정렬 방식으로 정렬할 원소의 키값에 해당하는 버킷에 원소를 분배하였다가 버킷의 순서대로 원소를 꺼내는 방법을 반복하는 것을 기수 정렬이라고 합니다.

원소의 키를 표한하는 값의 기수만큼 버킷이 필요하고, 키값의 자릿수만큼 기수 정렬을 사용합니다. 10진수로 표현된 키값을 가진 원소들을 정렬할 때에는 0부터 9까지 10개의 버킷을 사용하고 키값의 일의 자리에 대한 기수 정렬을 수행합니다.

다음 단계에서는 키값의 십의 자리에 대해서 하고, 그 다음 단계에서는 키값의 백의 자리에 대한 기수 정렬을 합니다.

한 단계가 끝날때마다 버킷에 분배된 원소들을 버킷의 순서대로 꺼내어 다음 단계의 기수 정렬을 해야되기 때문에 자료구조의 큐를 사용합니다.

## 알고리즘

```java
radix(arr[],n){
    for(k<-1;k<=n;k<-k+1)do{
        for(i<-0;i<n;i<-i+1)do{
            k번째 자릿수 저장;
            enqueue(q[k],arr[i]);
        }
        p <- -1;
        for(i<-0;i<=9;i<=i+1)do{
            while(q[i]!=null)do{
                p<-p+1;
                arr[p] <- dequeue(q[i]);
            }
        }
    }
}
```