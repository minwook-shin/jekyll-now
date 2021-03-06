---
layout: post
title: 알고리즘 공부-6 (트리)
---

알고리즘 공부에서 트리에 대한 내용을 공부해보았습니다.

아래는 오늘 공부한 내용을 요약한 노트입니다.

오늘도 저번과 마찬가지로 어김없이 즉석에서 필기한 내용이라 잘 정리가 안된 포스팅입니다.

## 트리

* 기본 개념 : 비선형 자료구조로서, 노드와 링크로 구성되어 있습니다.

노드는 정보를 나타나있고, 링크는 두 노드간의 연결관계를 나타내고 있습니다.

특징 : 최상위가 하나 존재하며, 최상위를 제외한 노드는 하나의 상위를 가져야합니다.
그리고, 노드는 여러개의 하위를 가질 수 있고, 한 노드로부터 다른 노드로 가는 경로는 유일해야합니다.

윈도우의 디렉토리 구조입니다.

## 용어 정리

* 노드 : 정보

* 링크 : 노드의 연결관계

* 루트 노드 : 최상위 노드

* 리프 노드 : 최하위 노드

* 인터널 노드 : 리프 노드가 아닌 모든 노드

* 서브트리 : 트리의 부분집합

* 패쓰 : 한 노드에서 다른 노드로 가는 경로

* 최소공통선조 : 두 노드의 공통적인 선조중 가장 레벨이 높은 선조노드

* 하위 노드 : 자신 아래로 연결된 노드

* 상위 노드 : 자신 위로 연결된 노드

* 조부모 노드 : 상위의 상위 노드

* 레벨 : 최상위에서 특정 노드로 가는 경로의 수

* 높이 : 가장 높은 레벨

## 이진트리

모든 인터널 노드가 두개 이하의 하위 노드를 갖는 트리입니다.

가장 쓰임새가 많은 트리입니다.

## 용도

parse tree : 수식

heap : 정렬

binary search tree : 검색

## 유형

full binary tree : 마지막 노드를 제외한 모든 레벨에 노드가 차있습니다.

complete binary tree : 모든 레벨에 노드가 다 차있습니다.

## full binary tree

레벨과 노드의 수 관계

레벨에 d일때 트리와 노드 갯수 n은 아래와 같습니다.
```
2^d-1 <= n <= 2^d - 1
```

## 구현

배열로 구현하면 full binary tree만 가능하며, 이진트리의 특징으로 인덱싱하게 됩니다.

링크드리스트로 구현하면 노드 클래스가 하나의 노드를 나타내며, 두 하위 노드를 가리키게 됩니다.

## 이진 탐색

트리순회(Tree Traversal)는 비선형구조에서 방문하는 방법이 필요해서 있습니다.

stack : pre-order,post-order, in-order

queue : level-order

* pre-order : 1. 최상위 방문 2. 왼쪽 서브트리 방문 3. 오른쪽 서브트리 방문

(재귀 호출하지만, stack으로 하면 재귀로 안해도 됩니다.)

* in-order : 1. 왼쪽 서브트리 방문 2. 최상위 방문 3. 오른쪽 서브트리 방문 

* post-order : 1. 왼똑 서브트리 방문 2. 오른쪽 서브트리 방문 3. 최상위 방문

* level-order : 위에서 아래로, 왼쪽에서 오른쪽으로 방문

## 수식 트리

개념 : 수식을 연산순서에 따라 트리로 구성한 것입니다.

최상위에는 연산자가 있고, 하위에 피연산자를 배치합니다.

먼저 계산해야할 것을 높은 레벨(낮은 위치)에 배치합니다.

## 후위표기에서 수식트리 구성

* 알고리즘

1. 피연산자는 노드를 만들어 스택에 푸시

1. 연산자는 노드를 생성하여 팝한 노드를 오른쪽 하위로 하고, 또 팝한 노드를 왼쪽 하위로 한다음 연산자 노드를 스택에 푸시합니다.

1. 스택에 마지막에 남은 노드가 최상위입니다.