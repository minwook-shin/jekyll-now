---
layout: post
title: How to solve the Codewars's Vowel Count
---

Today I try to solve the algorithm problem of codewars.

## Description

Return the number of vowels in the given string.

We will consider a, e, i, o, and u as vowels for this Kata.

The input string will only consist of lower case letters and/or spaces.

## Code

* split : returns array of strings computed by splitting.

* equals : returns true if the String are equal.

```java
public class Vowels {

  public static int getCount(String str) {
    int vowelsCount = 0;
    String[] arr = str.split("");
    for(String i : arr){
      if(i.equals("a")||i.equals("e")||i.equals("i")||i.equals("o")||i.equals("u")){
        vowelsCount++;
      }
    }
    return vowelsCount;
  }

}
```