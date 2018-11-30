---
layout: post
title: How to solve the Codewars's The highest profit wins!
---

Today I try to solve the algorithm problem of codewars.

## Description

Ben has a very simple idea to make some profit: 
he buys something and sells it again. 
Of course, this wouldn't give him any profit at all if he was simply to buy and sell it at the same price. 
Instead, he's going to buy it for the lowest possible price and sell it at the highest.

## Examples

* MinMax.minMax(new int[]{1,2,3,4,5}) -> {1,5}

* MinMax.minMax(new int[]{2334454,5}) -> {5, 2334454}

* MinMax.minMax(new int[]{1}) -> {1, 1}

## Code

* return : {min value, max value}

```java
class MinMax {
    public static int[] minMax(int[] arr) {
        int min = arr[0];
        int max = arr[0];
        for(int i : arr){
            if(min > i){
                min = i;
            }
            else if(max < i){
                max = i;
            }
        }
        int[] result = {min,max};
        return result;
    }
}
```