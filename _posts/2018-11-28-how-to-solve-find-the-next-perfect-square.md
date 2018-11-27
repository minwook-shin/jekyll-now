---
layout: post
title: How to solve the Codewars's Find the next perfect square!
---

Today I try to solve the algorithm problem of codewars.

## Description

You might know some pretty large perfect squares. 
But what about the NEXT one?

Complete the findNextSquare method that finds the next integral perfect square after the one passed as a parameter. 
Recall that an integral perfect square is an integer n such that sqrt(n) is also an integer.

If the parameter is itself not a perfect square, than -1 should be returned. 
You may assume the parameter is positive.

## Examples

* findNextSquare(121) -> 144

* findNextSquare(625) -> 676

* findNextSquare(114) -> -1

## Code

not a perfect square : sq != Math.floor(Math.sqrt(sq)) * Math.floor(Math.sqrt(sq)).

next square : Math.sqrt(sq) + 1 * Math.sqrt(sq) + 1.

Math.round() : returns the closest long or int number.

```java
public class NumberFun {
    public static long findNextSquare(long sq) {
        if(sq != Math.floor(Math.sqrt(sq)) * Math.floor(Math.sqrt(sq))){
            return -1;
        }
        double tmp = Math.sqrt(sq);
        tmp++;
        return Math.round(tmp*tmp); 
    }
}
```