---
layout: post
title: How to solve the Codewars's Sum of Numbers
---

Today I try to solve the algorithm problem of codewars.

## Description

Given two integers a and b, which can be positive or negative, find the sum of all the numbers between including them too and return it. 

If the two numbers are equal return a or b.

## Examples

* GetSum(1, 0) -> 1

* GetSum(1, 2) -> 3

* GetSum(0, 1) -> 1

* GetSum(1, 1) -> 1

* GetSum(-1, 0) -> -1

* GetSum(-1, 2) -> 2


## Code

* swap : ```int tmp = a; a = b; b = tmp;```


```java
public class Sum
{
    public int GetSum(int a, int b)
    {
        if(a > b) {
            int tmp = a;
            a = b;
            b = tmp;
        }
        int result = 0;
        for(int i = a; i <= b; i++) {
            result += i;
        }
        return result;
    }
}
```