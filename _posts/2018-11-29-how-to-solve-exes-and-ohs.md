---
layout: post
title: How to solve the Codewars's Exes and Ohs
---

Today I try to solve the algorithm problem of codewars.

## Description

Check to see if a string has the same amount of 'x's and 'o's. 
The method must return a boolean and be case insensitive. 
The string can contain any char.

## Examples

* XO("ooxx") -> true

* XO("xooxx") -> false

* XO("ooxXm") -> true : need to change it to lower case.

* XO("zpzpzpp") -> true

* XO("zzoo") -> false

## Code

* str.toLowerCase : returns lowercase string.

* split : returns array of strings computed by splitting.

* equals : returns true if the String are equal.

```java
public class XO {
  
  public static boolean getXO (String str) {
    int o = 0;
    int x = 0;
    String tmp = str.toLowerCase();
    String[] tmpArr = tmp.split("");
    for(String i : tmpArr){
      if(i.equals("o")){
        o++;
      }
      if(i.equals("x")){
        x++;
      }
    }
    return o==x;
  }
}
```