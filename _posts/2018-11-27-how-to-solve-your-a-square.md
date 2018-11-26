---
layout: post
title: How to solve the Codewars's You're a square!
---

Today I try to solve the algorithm problem of codewars.

## Description

You like building blocks. You especially like building blocks that are squares. 
And what you even like more, is to arrange them into a square of square building blocks!

However, sometimes, you can't arrange them into a square. 
Instead, you end up with an ordinary rectangle! 
Those blasted things! 
If you just had a way to know, whether you're currently working in vain… 
Wait! That's it! You just have to check if your number of building blocks is a perfect square.

* perfect square : N = n^2

## Examples

* isSquare(-1) -> false

* isSquare(0) -> true

* isSquare(3) -> false

* isSquare(4) -> true

* isSquare(25) -> true  

* isSquare(26) -> false

## Code

* Math.floor() : return the largest integer that is less than or equal to the number.

* Math.sqrt() : return the correctly rounded square root of a double value.

```java
public class Square {    
    public static boolean isSquare(int n) {
        return n == Math.floor(Math.sqrt(n)) * Math.floor(Math.sqrt(n));
    }
}
```