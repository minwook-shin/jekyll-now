---
layout: post
title: How to solve the Codewars's Shortest Word
---

Today I try to solve the algorithm problem of codewars.

## Description

Simple, given a string of words, return the length of the shortest word(s).

String will never be empty and you do not need to account for different data types.

## Example

* findShort("i want to travel the world writing code one day") -> 1

* findShort("Lets all go on holiday somewhere very cold") -> 2

* findShort("lets talk about Java the best language") -> 3

## Code

* split() : returns array of strings computed by splitting.

```java
import jav.util.Arrays;

public class Kata {
    public static int findShort(String s) {
        String[] arr = s.split(" ");
        int min = arr[0].length();
        for(String i : arr){
            if(min > i.length()){
                min = i.length();
            }
        }
        return min;
    }
}
```