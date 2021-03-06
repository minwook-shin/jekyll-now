---
layout: post
title: 시간 복잡도 알아보기
---

이전에 알고리즘을 잠깐 배웠을때, 시간 복잡도에 대한 개념을 잘 안 쌓고 넘어간거 같아서 오늘 조금 더 알아보려고 합니다.

## 특징

실행시간은 실행 환경에 따라서(예를 들어 하드웨어나 소프트웨어) 달라니므로 절대적인 수치는 아닙니다.

실행 시간을 측정하는 것이 아니고, 연산의 실행 횟수를 세는 것입니다.

연상의 실행 횟수는 입력 데이터의 크기와 관련된 함수로 표현됩니다.

데이터의 크기가 같아보여도 실제 데이터에 따라 달라지므로, worst case와 average case 둘 다 필요합니다.

## 점근적 표기법

데이터의 갯수가 무한히 증가할 떄 수행시간이 증가하는 상승률로 시간 복작도를 표한합니다.

O 표기법이 있습니다.

다른 표기법도 있지만, 알고리즘의 실행 환경에 비의존적이라 비교적 비슷합니다.

## 상수 시간복잡도

n개의 갯수와 상관없이 상수 시간이 소요되면 O(1)입니다.

```java
int test(int n, int i)
    return int n*i;
```

## 선형 시간복잡도

for문과 같이 n번 반복하면 실행 횟수의 합도 n에 선형적 비례하므로 선형 시간복잡도를 의미하는 O(n)이라고 합니다.

```java
int test(int n, int i)
    return int n*i;
```

## worst case

worst case, 즉 최악의 경우라고 하는데, 예를 들어 순차 검색 알고리즘의 최악의 경우가 O(n)입니다.

그 이유는 1번째만에 찾을 수 있고, 2번째만에도 찾을 수 있을 수 도 있지만... 셀 수 없는 n개일때가 최악의 경우라고 칭할 수 있습니다.

```java
boolean search(int array[], int n){
    for(int i = 0;i<array.length;)
        if(array[i] == n)
            return true;
}
```

위 코드에서 현재 array의 길이가 알 수 없는 n개 이므로 최악의 경우는 O(n)입니다.

## 2차 시간

2중 for문은 보통 O(n^2)입니다.

```java
for (int i = 0;i<n-1;i++){
    for (int j = 0;j<n-1;j++){
        if (array[i] == n[j])
            return true;
    }
}
```

최종적으로 이 코드는 최악의 경우 실행횟수 n(n-1)/2번이고, 이는 시간 복잡도로 O(n^2)입니다.

그 이상 중첩되는 n차 시간은 O(N^3), O(N^4)처럼 늘어나면서 O(N^n)이 됩니다. 

참고로 O(2^N)은 기하 급수적으로 증가하는 성장 곡선이며, 재귀함수에서 나타납니다.

## 접근적 표기법

알고리즘에 포함된 연산들의 실행횟수를 표기하는 또 하나의 기법으로서, 최고 차항의 차수만 표기합니다.

점근 표기법으로 O 표기와 옴 표기가 있습니다.

O 표기는 lower-bound를 표현하며, 옴 표기는 upper-bound와 lower-bound를 같이 표현할 수 있습니다.

## 각 알고리즘의 시간 복잡도

* 이진 탐색 

정렬이 되있다고 가정하고 탐색하는 알고리즘이며, 한번 비교할 때마다 남아있는 데이터가 절반으로 줄어들기 때문에 시간 복잡도는 O(log2n)입니다.

* 버블 정렬

```java
void bubbleSort(int arr[], int n){
   int i, j;
   for (i = 0; i < n-1; i++)       
       for (j = 0; j < n-i-1; j++) 
           if (arr[j] > arr[j+1])
              swap(&arr[j], &arr[j+1]);
}
```

위 java 코드처럼 이중 for문이기 때문에 시간 복잡도는 O(n^2)입니다.

* 삽입 정렬
 
```java
void sort(int arr[]){
    int n = arr.length;
    for (int i=1; i<n; ++i){
        int key = arr[i];
        int j = i-1;
        while (j>=0 && arr[j] > key){
            arr[j+1] = arr[j];
            j = j-1;
        }
        arr[j+1] = key;
    }
}
```

정렬이 안되어있는 상태, 즉 최악의 경우에서의 시간 복잡도는 O(n^2)입니다.