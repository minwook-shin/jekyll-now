---
layout: post
title: 선택 정렬에 대하여 알아보기
---

오늘은 정렬 방법중 하나인 선택 정렬에 대하여 알아보려고 합니다.

## 개요

전체 원소에서 기준 위치에 맞는 원소를 선택하여 자리를 교환하는 방식으로서 선택 정렬이라고 합니다.

전체 원소중에서 가장 작은 원소를 찾아 선택한 뒤, 첫번째 원소와 자리를 교환하게 됩니다.

그리고 두번째로 작은 원소를 선택하고 두번째 자리 원소와 교환하게 되는 과정을 반복하게 됩니다.

## 알고리즘

n개의 원소를 선택 정렬할 때에는 n개의 메모리를 사용하게 됩니다.

그리고 반복적으로 i단계에서는 n-i개의 원소를 비교하게 되므로 비교 횟수는 n(n-1)/2 이며,시간 복잡도는 o(n^2)이 됩니다.

## code 

```java
public void selectSort(int arr[]){
    int i;
    int j;
    int min;
    for(i=0;i<arr.length-1;i++){
        min = i;
        for(j=i+1;j<arr.length; j++){
            if(arr[j] < a[min]){
                min = j;
            }
        }
    }
}
```