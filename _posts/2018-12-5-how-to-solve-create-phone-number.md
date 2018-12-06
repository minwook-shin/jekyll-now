---
layout: post
title: How to solve the Codewars's Create Phone Number
---

Today I try to solve the algorithm problem of codewars.

## Description

Write a function that accepts an array of 10 integers (between 0 and 9), 
that returns a string of those numbers in the form of a phone number.

## Example

new int[] {1, 2, 3, 4, 5, 6, 7, 8, 9, 0}) -> (123) 456-7890

## Code

```java
public class Kata {
  public static String createPhoneNumber(int[] numbers) {
    String result = "";
    for (int i = 0; i < numbers.length; i++) {
        if (i == 0) 
            result += '(';
        else if (i == 3) 
            result += ") ";
        else if (i == 6) 
            result += '-';

        result += numbers[i];
    }
    return result;
  }
}
```